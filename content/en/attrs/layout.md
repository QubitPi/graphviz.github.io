---
defaults:
- '""'
flags: []
minimums: []
name: layout
types:
- string
used_by: G
---
Specifies the name of the layout algorithm to use, such as `dot` or `neato`.

Normally, graphs should be kept independent of a type of layout. In some
cases, however, it can be convenient to embed the type of layout desired
within the graph.

For example, a graph containing position information from a layout might want
to record what the associated layout algorithm was.

This attribute takes precedence over the [`-K` flag](command.html#minusK) or
the actual command name used.