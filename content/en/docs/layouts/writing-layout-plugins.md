---
title: Writing Layout Plugins
aliases:
  - /doc/addingLayout.txt
  - /docs/writing-layout-plugins/
description: How to write a custom layout engine.
---
To create a new layout plugin called `xxx`, you first need
to provide two functions: `xxx_layout` and `xxx_cleanup`. The
semantics of these are described below.

## Layout

```
void xxx_layout(Agraph_t * g)
```

Initialize the graph.

- If the algorithm will use the common edge routing code, it should
  call `setEdgeType (g, ...);`.

- For each node, call `common_init_node` and `gv_nodesize`.

-   If the algorithm will use `spline_edges()` to route the edges, the
    node coordinates need to be stored in `ND_pos`, so this should be
    allocated here. This, and the two calls mentioned above, are all
    handled by a call to `neato_init_node()`.

- For each edge, call `common_init_edge`.

- The algorithm should allocate whatever other data structures it
  needs. This can involve fields in the `A*info_t` fields. In addition,
  each of these fields contains a `void* alg;` subfield that the algorithm
  can use the store additional data.  Once we move to cgraph, this will all be
  replaced with algorithm specific records.

- Layout the graph. When finished, each node should have its coordinates
  stored in points in `ND_coord_i(n)`, each edge should have its layout
  described in `ED_spl(e)`. 
  (N.B. As of version 2.21, `ND_coord_i` has been replaced by `ND_coord`,
  which are now floating point coordinates.)

To add edges, there are 3 functions available:

1.  `spline_edges1 (Agraph_t*, int edgeType)`
    Assumes the node coordinates are stored in `ND_coord_i`, and that
    `GD_bb` is set. For each edge, this function constructs the appropriate 
    data and stores it in `ED_spl`.
2.  `spline_edges0 (Agraph_t*)`
    Assumes the node coordinates are stored in `ND_pos`, and that
    `GD_bb` is set. This function uses the ratio attribute if set, 
    copies the values in `ND_pos` to `ND_coord_i` (converting from 
    inches to points); and calls spline_edges1 using the edge type
    specified by `setEdgeType()`.
3.  `spline_edges (Agraph_t*)`
    Assumes the node coordinates are stored in `ND_pos`. This
    function calculates the bounding box of g and stores it in `GD_bb`,
    then calls `spline_edges0()`.

If the algorithm only works with connected components, the code can
use the pack library to get components, lay them out individually, and
pack them together based on user specifications. A typical schema is
given below. One can look at the code for [`twopi`](/docs/layouts/twopi/), [`circo`](/docs/layouts/circo/), [`neato`](/docs/layouts/neato/) or [`fdp`](/docs/layouts/fdp/)
for more detailed examples.

```c
Agraph_t **ccs;
Agraph_t *sg;
Agnode_t *c = NULL;
int ncc;
int i;

ccs = ccomps(g, &ncc, 0);
if (ncc == 1) {
    /* layout nodes of g */
    adjustNodes(g);  /* if you need to remove overlaps */
    spline_edges(g); /* generic edge routing code */

} else {
    pack_info pinfo;
    pack_mode pmode = getPackMode(g, l_node);

    for (i = 0; i < ncc; i++) {
        sg = ccs[i];
        /* layout sg */
        adjustNodes(sg);  /* if you need to remove overlaps */
    }
    spline_edges(g);  /* generic edge routing */

    /* initialize packing info, e.g. */
    pinfo.margin = getPack(g, CL_OFFSET, CL_OFFSET);
    pinfo.doSplines = 1;
    pinfo.mode = pmode;
    pinfo.fixed = 0;
    packSubgraphs(ncc, ccs, g, &pinfo);
}
for (i = 0; i < ncc; i++) {
    agdelete(g, ccs[i]);
}

free(ccs);
```

Be careful in laying of subgraphs if you rely on attributes that have
only been set in the root graph. With connected components, edges can
be added with each component, before packing (as above) or after the
components have been packed (see circo).

It is good to check for trivial cases where the graph has 0 or 1 nodes,
or no edges.

At the end of `xxx_layout`, call

```c
dotneato_postprocess(g);
```

The following template will work in most cases, ignoring the problems of
handling disconnected graphs and removing node overlaps:

```c
static void
xxx_init_node(node_t * n)
{
  neato_init_node(n);
  /* add algorithm-specific data, if desired */
}

static void
xxx_init_edge(edge_t * e)
{
  common_init_edge(e);
  /* add algorithm-specific data, if desired */
}

static void
xxx_init_node_edge(graph_t * g)
{
  node_t *n;
  edge_t *e;

  for (n = agfstnode(g); n; n = agnxtnode(g, n)) {
      xxx_init_node(n);
  }
  for (n = agfstnode(g); n; n = agnxtnode(g, n)) {
      for (e = agfstout(g, n); e; e = agnxtout(g, e)){          
          xxx_init_edge(e);
      }
  }
}

void
xxx_layout (Agraph_t* g)
{
  xxx_init_node_edge(g);
  /* Set ND_pos(n) for each node n */
  spline_edges(g);
  dotneato_postprocess(g);
}  
```

## Cleanup

```c
void xxx_cleanup(Agraph_t * g)
```

Free up any resources allocated in the layout.

Finish with calls to `gv_cleanup_node` and `gv_cleanup_edge` for
each node and edge. This cleans up splines labels, `ND_pos`, shapes
and 0's out the `A*info_t`, so these have to occur last, but could be
part of explicit `xxx_cleanup_node` and `xxx_cleanup_edge`, if desired.

At the end, you should do:

```c
if (g != g->root) memset(&(g->u), 0, sizeof(Agraphinfo_t));
```

This is necessary for the graph to be laid out again, as the layout
code assumes this structure is clean.

`libgvc` does a final cleanup to the root graph, freeing any drawing,
freeing its label, and zeroing out `Agraphinfo_t` of the root graph.

The following template will work in most cases:

```c
static void xxx_cleanup_graph(Agraph_t * g)
{
  /* Free any algorithm-specific data attached to the graph */
  if (g != g->root) memset(&(g->u), 0, sizeof(Agraphinfo_t));
}

static void xxx_cleanup_edge (Agedge_t* e)
{
  /* Free any algorithm-specific data attached to the edge */
  gv_cleanup_edge(e);
}

static void xxx_cleanup_node (Agnode_t* n)
{
  /* Free any algorithm-specific data attached to the node */
  gv_cleanup_node(e);
}

void xxx_cleanup(Agraph_t * g)
{
  Agnode_t *n;
  Agedge_t *e;

  for (n = agfstnode(g); n; n = agnxtnode(g, n)) {
      for (e = agfstout(g, n); e; e = agnxtout(g, e)) {
          xxx_cleanup_edge(e);
      }
      xxx_cleanup_node(n);
  }
  xxx_cleanup_graph(g);
}   
```

Most layouts use auxiliary routines similar to `neato`, so
the entry points can be added in `plugin/neato_layout`.

Add to `gvlayout_neato_layout.c`:

```c
gvlayout_engine_t xxxgen_engine = {
    xxx_layout,
    xxx_cleanup,
};
```

and the line

```c
{LAYOUT_XXX, "xxx", 0, &xxxgen_engine, &neatogen_features},
```

to `gvlayout_neato_types` and a new emum `LAYOUT_XXX` to `layout_type` in that file.

The above allows the new layout to piggyback on top of the `neato`
plugin, but requires rebuilding the plugin. In general, a user
can (and probably should) build a layout plugin totally separately. 

To do this, after writing `xxx_layout` and `xxx_cleanup`, it is necessary to:

1. Add the types and data structures:

   ```c
   typedef enum { LAYOUT_XXX } layout_type;

   static gvlayout_features_t xxxgen_features = {
       0
   };
   gvlayout_engine_t xxxgen_engine = {
       xxx_layout,
       xxx_cleanup,
   };
   static gvplugin_installed_t gvlayout_xxx_types[] = {
       {LAYOUT_XXX, "xxx", 0, &xxxgen_engine, &xxxgen_features},
       {0, NULL, 0, NULL, NULL}
   };
   static gvplugin_api_t apis[] = {
       {API_layout, &gvlayout_xxx_types},
       {(api_t)0, 0},
   };
   gvplugin_library_t gvplugin_xxx_layout_LTX_library = { "xxx_layout", apis };
   ```

2. Combine all of this into a dynamic library whose name contains the 
   string `gvplugin_` and install the library in the same directory as the 
   other Graphviz plugins. For example, on Linux systems, the dot layout 
   plugin is in the library `libgvplugin_dot_layout.so`.

3. Run `dot -c` to regenerate the config file.

NOTES:
  - Additional layouts can be added as extra lines in `gvlayout_xxx_types`.
  - Obviously, most of the names and strings can be arbitrary. One
  constraint is that external identifier for the `gvplugin_library_t`
  type must end in `_LTX_library`. In addition, the string `xxx` in
  each entry of `gvlayout_xxx_types` is the name used to identify the
  layout algorithm, so needs to be distinct from any other layout name.
  - The features of a layout algorithm are currently limited to a 
  flag of bits, and the only flag supported is `LAYOUT_USES_RANKDIR`,
  which enables the layout to the [`rankdir`](/docs/attrs/rankdir/) attribute.

Changes need to be made to any applications that
statically know about layout algorithms.

## Automake Configuration

If you want to integrate your code into the Graphviz software
and use its build system, follow the instructions below. 
You can certainly build and install your plugin using your own
build software.

0. Put your software in `lib/xxxgen`, and added the hooks describe above
into `gvlayout_neato_layout.c`
1. In `lib/xxxgen`, provide a `Makefile.am` (based on a simple example
like `lib/fdpgen/Makefile.am`)
3. In `lib/Makefile.am`, add `xxxgen` to `SUBDIRS`
2. In `configure.ac`, add `lib/xxxgen/Makefile` to `AC_CONFIG_FILES`.
4. In `lib/plugin/neato_layout/Makefile.am`, insert
	`$(top_builddir)/lib/xxxgen/libxxxgen_C.la`
	in `libgvplugin_neato_layout_C_la_LIBADD`.
5. Remember to run `autogen.sh` because on its own `configure` can guess wrong.

This also assumes you have a good version of the various automake tools
on your system.
