---
layout: null
permalink: /doc/attrs1.html
---
{::nomarkdown}
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML//EN">
<!--
    This is a generated document.  Do not edit.
-->
<HTML VERSION="2.0">
<HEAD>
<TITLE>Testing - Node, Edge and Graph Attributes</TITLE>
</HEAD>
<BODY BGCOLOR=white>
<A NAME="top"></A>
<H1 align=CENTER>Node, Edge and Graph Attributes</H1>
<HR>
The table below describes the attributes used by various Graphviz tools.
The table gives the name of the attribute, the graph components (node,
edge, etc.) which use the attribute and the type of the attribute
(strings representing legal values of that type). Where applicable, the table
also gives a default value for the attribute, a minimum allowed setting
for numeric attributes, and certain restrictions on the use of the attribute.
<P>
Note that attribute names are case-sensitive. 
This is usually true for attribute values as well, unless noted.
<P>
All Graphviz attributes are specified by name-value pairs. Thus, to
set the fillcolor of a node <TT>abc</TT>, one would use
<TABLE>
<TR><TD><TT>abc [fillcolor = red]</TT></TR>
</TABLE>
Similarly, to set the arrowhead style of an edge <TT>abc -> def</TT>,
one would use
<TABLE>
<TR><TD><TT>abc -> def [arrowhead = diamond]</TT></TR>
</TABLE>
Further details concerning the setting of attributes can be found
in the description of the
<A HREF=lang.html>DOT language.</A>
<P>
At present, most device-independent units are either inches or
<A NAME="points"></A>
<A HREF="http://en.wikipedia.org/wiki/Point_(typography)">points</A>,
which we take as 72 points per inch.
<P>
<A NAME=h:undir_note><STRONG>Note:</STRONG></A> Some attributes, such as
<A HREF=#d:dir>dir</A> or <A HREF=#d:arrowtail>arrowtail</A>, are
ambiguous when used in
<A HREF=lang.html>DOT</A>
with an undirected graph since the head and tail of an edge are meaningless.
As a convention, the first time an undirected edge appears, the
<A HREF=lang.html>DOT</A>
parser will assign the left node as the tail node and the right node as
the head. For example, the edge <TT>A -- B</TT> will have tail <TT>A</TT>
and head <TT>B</TT>. It is the user's responsibility to handle such
edges consistently. If the edge appears later, in the format
<TABLE>
<TR><TD><TT>B -- A [taillabel = "tail"]</TT></TR>
</TABLE>
the drawing will attach the tail label to node <TT>A</TT>.
To avoid possible confusion when such attributes are required, the user
is encouraged to use a directed graph.
If it is important to make the graph appear undirected, this can be
done using the <A HREF=#d:dir>dir</A>, <A HREF=#d:arrowtail>arrowtail</A>
or <A HREF=#d:arrowhead>arrowhead</A> attributes.
<P>
The tools accept standard C representations for <EM>int</EM> and
<EM>double</EM> types.
For the <A NAME=k:bool><EM>bool</EM></A> type, TRUE values are
represented by "true" or "yes" (case-insensitive)
and any non-zero integer, and FALSE values by "false" or "no" (case-insensitive)
and zero.
In addition, there are a variety of specialized types such as
<EM>arrowType</EM>, <EM>color</EM>,
<EM>point</EM> and <EM>rankdir</EM>. Legal values for these types are given
at the end.
<P>
In the <A NAME=h:uses><STRONG>Used By</STRONG></A> field, the
characters E, N, G, S and C
represent edges, nodes, the root graph, subgraphs
and cluster subgraphs, respectively.
This field indicates which graph component uses the attribute.
<P>
In the <STRONG>Notes</STRONG> field, an annotation of <em>write only</em> 
indicates that the attribute is used for output, and is not used or read by any
of the layout programs.
<HR ALIGN=CENTER WIDTH="70%" SIZE=3>

<TABLE ALIGN=CENTER>
<TR><TH>Name</TH><TH><A HREF=#h:uses>Used By</A></TH><TH>Type</TH><TH ALIGN=CENTER>Default</TH><TH>Minimum</TH><TH>Notes</TH></TR>
 <TR><TD><A NAME=a:Damping HREF=#d:Damping>Damping</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">0.99</TD><TD>0.0</TD><TD>neato only</TD> </TR>
 <TR><TD><A NAME=a:K HREF=#d:K>K</A>
</TD><TD>GC</TD><TD>double</TD><TD ALIGN="CENTER">0.3</TD><TD>0</TD><TD>sfdp, fdp only</TD> </TR>
 <TR><TD><A NAME=a:URL HREF=#d:URL>URL</A>
</TD><TD>ENGC</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">&#60;none&#62;</TD><TD></TD><TD>svg, postscript, map only</TD> </TR>
 <TR><TD><A NAME=a:_background HREF=#d:_background>_background</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">&#60;none&#62;</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:area HREF=#d:area>area</A>
</TD><TD>NC</TD><TD>double</TD><TD ALIGN="CENTER">1.0</TD><TD>&#62;0</TD><TD>patchwork only</TD> </TR>
 <TR><TD><A NAME=a:arrowhead HREF=#d:arrowhead>arrowhead</A>
</TD><TD>E</TD><TD><A HREF=#k:arrowType>arrowType</A>
</TD><TD ALIGN="CENTER">normal</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:arrowsize HREF=#d:arrowsize>arrowsize</A>
</TD><TD>E</TD><TD>double</TD><TD ALIGN="CENTER">1.0</TD><TD>0.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:arrowtail HREF=#d:arrowtail>arrowtail</A>
</TD><TD>E</TD><TD><A HREF=#k:arrowType>arrowType</A>
</TD><TD ALIGN="CENTER">normal</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:bb HREF=#d:bb>bb</A>
</TD><TD>G</TD><TD><A HREF=#k:rect>rect</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>write only</TD> </TR>
 <TR><TD><A NAME=a:bgcolor HREF=#d:bgcolor>bgcolor</A>
</TD><TD>GC</TD><TD><A HREF=#k:color>color</A>
<BR><A HREF=#k:colorList>colorList</A>
</TD><TD ALIGN="CENTER">&#60;none&#62;</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:center HREF=#d:center>center</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:charset HREF=#d:charset>charset</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">"UTF-8"</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:clusterrank HREF=#d:clusterrank>clusterrank</A>
</TD><TD>G</TD><TD><A HREF=#k:clusterMode>clusterMode</A>
</TD><TD ALIGN="CENTER">local</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:color HREF=#d:color>color</A>
</TD><TD>ENC</TD><TD><A HREF=#k:color>color</A>
<BR><A HREF=#k:colorList>colorList</A>
</TD><TD ALIGN="CENTER">black</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:colorscheme HREF=#d:colorscheme>colorscheme</A>
</TD><TD>ENCG</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:comment HREF=#d:comment>comment</A>
</TD><TD>ENG</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:compound HREF=#d:compound>compound</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:concentrate HREF=#d:concentrate>concentrate</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:constraint HREF=#d:constraint>constraint</A>
</TD><TD>E</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">true</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:decorate HREF=#d:decorate>decorate</A>
</TD><TD>E</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:defaultdist HREF=#d:defaultdist>defaultdist</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">1+(avg. len)*sqrt(|V|)</TD><TD>epsilon</TD><TD>neato only</TD> </TR>
 <TR><TD><A NAME=a:dim HREF=#d:dim>dim</A>
</TD><TD>G</TD><TD>int</TD><TD ALIGN="CENTER">2</TD><TD>2</TD><TD>sfdp, fdp, neato only</TD> </TR>
 <TR><TD><A NAME=a:dimen HREF=#d:dimen>dimen</A>
</TD><TD>G</TD><TD>int</TD><TD ALIGN="CENTER">2</TD><TD>2</TD><TD>sfdp, fdp, neato only</TD> </TR>
 <TR><TD><A NAME=a:dir HREF=#d:dir>dir</A>
</TD><TD>E</TD><TD><A HREF=#k:dirType>dirType</A>
</TD><TD ALIGN="CENTER">forward(directed)<BR>none(undirected)</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:diredgeconstraints HREF=#d:diredgeconstraints>diredgeconstraints</A>
</TD><TD>G</TD><TD>string<BR><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD>neato only</TD> </TR>
 <TR><TD><A NAME=a:distortion HREF=#d:distortion>distortion</A>
</TD><TD>N</TD><TD>double</TD><TD ALIGN="CENTER">0.0</TD><TD>-100.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:dpi HREF=#d:dpi>dpi</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">96.0<BR>0.0</TD><TD></TD><TD>svg, bitmap output only</TD> </TR>
 <TR><TD><A NAME=a:edgeURL HREF=#d:edgeURL>edgeURL</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:edgehref HREF=#d:edgehref>edgehref</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:edgetarget HREF=#d:edgetarget>edgetarget</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">&#60;none&#62;</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:edgetooltip HREF=#d:edgetooltip>edgetooltip</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, cmap only</TD> </TR>
 <TR><TD><A NAME=a:epsilon HREF=#d:epsilon>epsilon</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">.0001 * # nodes(mode == KK)<BR>.0001(mode == major)</TD><TD></TD><TD>neato only</TD> </TR>
 <TR><TD><A NAME=a:esep HREF=#d:esep>esep</A>
</TD><TD>G</TD><TD><A HREF=#k:addDouble>addDouble</A>
<BR><A HREF=#k:addPoint>addPoint</A>
</TD><TD ALIGN="CENTER">+3</TD><TD></TD><TD>not dot</TD> </TR>
 <TR><TD><A NAME=a:fillcolor HREF=#d:fillcolor>fillcolor</A>
</TD><TD>NEC</TD><TD><A HREF=#k:color>color</A>
<BR><A HREF=#k:colorList>colorList</A>
</TD><TD ALIGN="CENTER">lightgrey(nodes)<BR>black(clusters)</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:fixedsize HREF=#d:fixedsize>fixedsize</A>
</TD><TD>N</TD><TD><A HREF=#k:bool>bool</A>
<BR>string</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:fontcolor HREF=#d:fontcolor>fontcolor</A>
</TD><TD>ENGC</TD><TD><A HREF=#k:color>color</A>
</TD><TD ALIGN="CENTER">black</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:fontname HREF=#d:fontname>fontname</A>
</TD><TD>ENGC</TD><TD>string</TD><TD ALIGN="CENTER">"Times-Roman"</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:fontnames HREF=#d:fontnames>fontnames</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg only</TD> </TR>
 <TR><TD><A NAME=a:fontpath HREF=#d:fontpath>fontpath</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">system-dependent</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:fontsize HREF=#d:fontsize>fontsize</A>
</TD><TD>ENGC</TD><TD>double</TD><TD ALIGN="CENTER">14.0</TD><TD>1.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:forcelabels HREF=#d:forcelabels>forcelabels</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">true</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:gradientangle HREF=#d:gradientangle>gradientangle</A>
</TD><TD>NCG</TD><TD>int</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:group HREF=#d:group>group</A>
</TD><TD>N</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:headURL HREF=#d:headURL>headURL</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:head_lp HREF=#d:head_lp>head_lp</A>
</TD><TD>E</TD><TD><A HREF=#k:point>point</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>write only</TD> </TR>
 <TR><TD><A NAME=a:headclip HREF=#d:headclip>headclip</A>
</TD><TD>E</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">true</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:headhref HREF=#d:headhref>headhref</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:headlabel HREF=#d:headlabel>headlabel</A>
</TD><TD>E</TD><TD><A HREF=#k:lblString>lblString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:headport HREF=#d:headport>headport</A>
</TD><TD>E</TD><TD><A HREF=#k:portPos>portPos</A>
</TD><TD ALIGN="CENTER">center</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:headtarget HREF=#d:headtarget>headtarget</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">&#60;none&#62;</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:headtooltip HREF=#d:headtooltip>headtooltip</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, cmap only</TD> </TR>
 <TR><TD><A NAME=a:height HREF=#d:height>height</A>
</TD><TD>N</TD><TD>double</TD><TD ALIGN="CENTER">0.5</TD><TD>0.02</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:href HREF=#d:href>href</A>
</TD><TD>GCNE</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, postscript, map only</TD> </TR>
 <TR><TD><A NAME=a:id HREF=#d:id>id</A>
</TD><TD>GCNE</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, postscript, map only</TD> </TR>
 <TR><TD><A NAME=a:image HREF=#d:image>image</A>
</TD><TD>N</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:imagepath HREF=#d:imagepath>imagepath</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:imagepos HREF=#d:imagepos>imagepos</A>
</TD><TD>N</TD><TD>string</TD><TD ALIGN="CENTER">"mc"</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:imagescale HREF=#d:imagescale>imagescale</A>
</TD><TD>N</TD><TD><A HREF=#k:bool>bool</A>
<BR>string</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:inputscale HREF=#d:inputscale>inputscale</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">&#60;none&#62;</TD><TD></TD><TD>fdp, neato only</TD> </TR>
 <TR><TD><A NAME=a:label HREF=#d:label>label</A>
</TD><TD>ENGC</TD><TD><A HREF=#k:lblString>lblString</A>
</TD><TD ALIGN="CENTER">"&#92;N" (nodes)<BR>"" (otherwise)</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:labelURL HREF=#d:labelURL>labelURL</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:label_scheme HREF=#d:label_scheme>label_scheme</A>
</TD><TD>G</TD><TD>int</TD><TD ALIGN="CENTER">0</TD><TD>0</TD><TD>sfdp only</TD> </TR>
 <TR><TD><A NAME=a:labelangle HREF=#d:labelangle>labelangle</A>
</TD><TD>E</TD><TD>double</TD><TD ALIGN="CENTER">-25.0</TD><TD>-180.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:labeldistance HREF=#d:labeldistance>labeldistance</A>
</TD><TD>E</TD><TD>double</TD><TD ALIGN="CENTER">1.0</TD><TD>0.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:labelfloat HREF=#d:labelfloat>labelfloat</A>
</TD><TD>E</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:labelfontcolor HREF=#d:labelfontcolor>labelfontcolor</A>
</TD><TD>E</TD><TD><A HREF=#k:color>color</A>
</TD><TD ALIGN="CENTER">black</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:labelfontname HREF=#d:labelfontname>labelfontname</A>
</TD><TD>E</TD><TD>string</TD><TD ALIGN="CENTER">"Times-Roman"</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:labelfontsize HREF=#d:labelfontsize>labelfontsize</A>
</TD><TD>E</TD><TD>double</TD><TD ALIGN="CENTER">14.0</TD><TD>1.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:labelhref HREF=#d:labelhref>labelhref</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:labeljust HREF=#d:labeljust>labeljust</A>
</TD><TD>GC</TD><TD>string</TD><TD ALIGN="CENTER">"c"</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:labelloc HREF=#d:labelloc>labelloc</A>
</TD><TD>NGC</TD><TD>string</TD><TD ALIGN="CENTER">"t"(clusters)<BR>"b"(root graphs)<BR>"c"(nodes)</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:labeltarget HREF=#d:labeltarget>labeltarget</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">&#60;none&#62;</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:labeltooltip HREF=#d:labeltooltip>labeltooltip</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, cmap only</TD> </TR>
 <TR><TD><A NAME=a:landscape HREF=#d:landscape>landscape</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:layer HREF=#d:layer>layer</A>
</TD><TD>ENC</TD><TD><A HREF=#k:layerRange>layerRange</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:layerlistsep HREF=#d:layerlistsep>layerlistsep</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">","</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:layers HREF=#d:layers>layers</A>
</TD><TD>G</TD><TD><A HREF=#k:layerList>layerList</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:layerselect HREF=#d:layerselect>layerselect</A>
</TD><TD>G</TD><TD><A HREF=#k:layerRange>layerRange</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:layersep HREF=#d:layersep>layersep</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">" :&#92;t"</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:layout HREF=#d:layout>layout</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:len HREF=#d:len>len</A>
</TD><TD>E</TD><TD>double</TD><TD ALIGN="CENTER">1.0(neato)<BR>0.3(fdp)</TD><TD></TD><TD>fdp, neato only</TD> </TR>
 <TR><TD><A NAME=a:levels HREF=#d:levels>levels</A>
</TD><TD>G</TD><TD>int</TD><TD ALIGN="CENTER">MAXINT</TD><TD>0.0</TD><TD>sfdp only</TD> </TR>
 <TR><TD><A NAME=a:levelsgap HREF=#d:levelsgap>levelsgap</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">0.0</TD><TD></TD><TD>neato only</TD> </TR>
 <TR><TD><A NAME=a:lhead HREF=#d:lhead>lhead</A>
</TD><TD>E</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:lheight HREF=#d:lheight>lheight</A>
</TD><TD>GC</TD><TD>double</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>write only</TD> </TR>
 <TR><TD><A NAME=a:lp HREF=#d:lp>lp</A>
</TD><TD>EGC</TD><TD><A HREF=#k:point>point</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>write only</TD> </TR>
 <TR><TD><A NAME=a:ltail HREF=#d:ltail>ltail</A>
</TD><TD>E</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:lwidth HREF=#d:lwidth>lwidth</A>
</TD><TD>GC</TD><TD>double</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>write only</TD> </TR>
 <TR><TD><A NAME=a:margin HREF=#d:margin>margin</A>
</TD><TD>NCG</TD><TD>double<BR><A HREF=#k:point>point</A>
</TD><TD ALIGN="CENTER">&#60;device-dependent&#62;</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:maxiter HREF=#d:maxiter>maxiter</A>
</TD><TD>G</TD><TD>int</TD><TD ALIGN="CENTER">100 &#42; # nodes(mode == KK)<BR>200(mode == major)<BR>600(fdp)</TD><TD></TD><TD>fdp, neato only</TD> </TR>
 <TR><TD><A NAME=a:mclimit HREF=#d:mclimit>mclimit</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">1.0</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:mindist HREF=#d:mindist>mindist</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">1.0</TD><TD>0.0</TD><TD>circo only</TD> </TR>
 <TR><TD><A NAME=a:minlen HREF=#d:minlen>minlen</A>
</TD><TD>E</TD><TD>int</TD><TD ALIGN="CENTER">1</TD><TD>0</TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:mode HREF=#d:mode>mode</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">major</TD><TD></TD><TD>neato only</TD> </TR>
 <TR><TD><A NAME=a:model HREF=#d:model>model</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">shortpath</TD><TD></TD><TD>neato only</TD> </TR>
 <TR><TD><A NAME=a:mosek HREF=#d:mosek>mosek</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD>neato only</TD> </TR>
 <TR><TD><A NAME=a:newrank HREF=#d:newrank>newrank</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:nodesep HREF=#d:nodesep>nodesep</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">0.25</TD><TD>0.02</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:nojustify HREF=#d:nojustify>nojustify</A>
</TD><TD>GCNE</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:normalize HREF=#d:normalize>normalize</A>
</TD><TD>G</TD><TD>double<BR><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD>not dot</TD> </TR>
 <TR><TD><A NAME=a:notranslate HREF=#d:notranslate>notranslate</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD>neato only</TD> </TR>
 <TR><TD><A NAME=a:nslimit HREF=#d:nslimit>nslimit</A>
<BR><A NAME=a:nslimit1 HREF=#d:nslimit1>nslimit1</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:ordering HREF=#d:ordering>ordering</A>
</TD><TD>GN</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:orientation HREF=#d:orientation>orientation</A>
</TD><TD>N</TD><TD>double</TD><TD ALIGN="CENTER">0.0</TD><TD>360.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=aa:orientation HREF=#dd:orientation>orientation</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:outputorder HREF=#d:outputorder>outputorder</A>
</TD><TD>G</TD><TD><A HREF=#k:outputMode>outputMode</A>
</TD><TD ALIGN="CENTER">breadthfirst</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:overlap HREF=#d:overlap>overlap</A>
</TD><TD>G</TD><TD>string<BR><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">true</TD><TD></TD><TD>not dot</TD> </TR>
 <TR><TD><A NAME=a:overlap_scaling HREF=#d:overlap_scaling>overlap_scaling</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">-4</TD><TD>-1.0e10</TD><TD>prism only</TD> </TR>
 <TR><TD><A NAME=a:overlap_shrink HREF=#d:overlap_shrink>overlap_shrink</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">true</TD><TD></TD><TD>prism only</TD> </TR>
 <TR><TD><A NAME=a:pack HREF=#d:pack>pack</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
<BR>int</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:packmode HREF=#d:packmode>packmode</A>
</TD><TD>G</TD><TD><A HREF=#k:packMode>packMode</A>
</TD><TD ALIGN="CENTER">node</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:pad HREF=#d:pad>pad</A>
</TD><TD>G</TD><TD>double<BR><A HREF=#k:point>point</A>
</TD><TD ALIGN="CENTER">0.0555 (4 points)</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:page HREF=#d:page>page</A>
</TD><TD>G</TD><TD>double<BR><A HREF=#k:point>point</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:pagedir HREF=#d:pagedir>pagedir</A>
</TD><TD>G</TD><TD><A HREF=#k:pagedir>pagedir</A>
</TD><TD ALIGN="CENTER">BL</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:pencolor HREF=#d:pencolor>pencolor</A>
</TD><TD>C</TD><TD><A HREF=#k:color>color</A>
</TD><TD ALIGN="CENTER">black</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:penwidth HREF=#d:penwidth>penwidth</A>
</TD><TD>CNE</TD><TD>double</TD><TD ALIGN="CENTER">1.0</TD><TD>0.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:peripheries HREF=#d:peripheries>peripheries</A>
</TD><TD>NC</TD><TD>int</TD><TD ALIGN="CENTER">shape default(nodes)<BR>1(clusters)</TD><TD>0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:pin HREF=#d:pin>pin</A>
</TD><TD>N</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD>fdp, neato only</TD> </TR>
 <TR><TD><A NAME=a:pos HREF=#d:pos>pos</A>
</TD><TD>EN</TD><TD><A HREF=#k:point>point</A>
<BR><A HREF=#k:splineType>splineType</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:quadtree HREF=#d:quadtree>quadtree</A>
</TD><TD>G</TD><TD><A HREF=#k:quadType>quadType</A>
<BR><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">normal</TD><TD></TD><TD>sfdp only</TD> </TR>
 <TR><TD><A NAME=a:quantum HREF=#d:quantum>quantum</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">0.0</TD><TD>0.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:rank HREF=#d:rank>rank</A>
</TD><TD>S</TD><TD><A HREF=#k:rankType>rankType</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:rankdir HREF=#d:rankdir>rankdir</A>
</TD><TD>G</TD><TD><A HREF=#k:rankdir>rankdir</A>
</TD><TD ALIGN="CENTER">TB</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:ranksep HREF=#d:ranksep>ranksep</A>
</TD><TD>G</TD><TD>double<BR><A HREF=#k:doubleList>doubleList</A>
</TD><TD ALIGN="CENTER">0.5(dot)<BR>1.0(twopi)</TD><TD>0.02</TD><TD>twopi, dot only</TD> </TR>
 <TR><TD><A NAME=a:ratio HREF=#d:ratio>ratio</A>
</TD><TD>G</TD><TD>double<BR>string</TD><TD ALIGN="CENTER"></TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:rects HREF=#d:rects>rects</A>
</TD><TD>N</TD><TD><A HREF=#k:rect>rect</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>write only</TD> </TR>
 <TR><TD><A NAME=a:regular HREF=#d:regular>regular</A>
</TD><TD>N</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">false</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:remincross HREF=#d:remincross>remincross</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">true</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:repulsiveforce HREF=#d:repulsiveforce>repulsiveforce</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">1.0</TD><TD>0.0</TD><TD>sfdp only</TD> </TR>
 <TR><TD><A NAME=a:resolution HREF=#d:resolution>resolution</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">96.0<BR>0.0</TD><TD></TD><TD>svg, bitmap output only</TD> </TR>
 <TR><TD><A NAME=a:root HREF=#d:root>root</A>
</TD><TD>GN</TD><TD>string<BR><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">&#60;none&#62;(graphs)<BR>false(nodes)</TD><TD></TD><TD>circo, twopi only</TD> </TR>
 <TR><TD><A NAME=a:rotate HREF=#d:rotate>rotate</A>
</TD><TD>G</TD><TD>int</TD><TD ALIGN="CENTER">0</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:rotation HREF=#d:rotation>rotation</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">0</TD><TD></TD><TD>sfdp only</TD> </TR>
 <TR><TD><A NAME=a:samehead HREF=#d:samehead>samehead</A>
</TD><TD>E</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:sametail HREF=#d:sametail>sametail</A>
</TD><TD>E</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:samplepoints HREF=#d:samplepoints>samplepoints</A>
</TD><TD>N</TD><TD>int</TD><TD ALIGN="CENTER">8(output)<BR>20(overlap and image maps)</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:scale HREF=#d:scale>scale</A>
</TD><TD>G</TD><TD>double<BR><A HREF=#k:point>point</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>not dot</TD> </TR>
 <TR><TD><A NAME=a:searchsize HREF=#d:searchsize>searchsize</A>
</TD><TD>G</TD><TD>int</TD><TD ALIGN="CENTER">30</TD><TD></TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:sep HREF=#d:sep>sep</A>
</TD><TD>G</TD><TD><A HREF=#k:addDouble>addDouble</A>
<BR><A HREF=#k:addPoint>addPoint</A>
</TD><TD ALIGN="CENTER">+4</TD><TD></TD><TD>not dot</TD> </TR>
 <TR><TD><A NAME=a:shape HREF=#d:shape>shape</A>
</TD><TD>N</TD><TD><A HREF=#k:shape>shape</A>
</TD><TD ALIGN="CENTER">ellipse</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:shapefile HREF=#d:shapefile>shapefile</A>
</TD><TD>N</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:showboxes HREF=#d:showboxes>showboxes</A>
</TD><TD>ENG</TD><TD>int</TD><TD ALIGN="CENTER">0</TD><TD>0</TD><TD>dot only</TD> </TR>
 <TR><TD><A NAME=a:sides HREF=#d:sides>sides</A>
</TD><TD>N</TD><TD>int</TD><TD ALIGN="CENTER">4</TD><TD>0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:size HREF=#d:size>size</A>
</TD><TD>G</TD><TD>double<BR><A HREF=#k:point>point</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:skew HREF=#d:skew>skew</A>
</TD><TD>N</TD><TD>double</TD><TD ALIGN="CENTER">0.0</TD><TD>-100.0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:smoothing HREF=#d:smoothing>smoothing</A>
</TD><TD>G</TD><TD><A HREF=#k:smoothType>smoothType</A>
</TD><TD ALIGN="CENTER">"none"</TD><TD></TD><TD>sfdp only</TD> </TR>
 <TR><TD><A NAME=a:sortv HREF=#d:sortv>sortv</A>
</TD><TD>GCN</TD><TD>int</TD><TD ALIGN="CENTER">0</TD><TD>0</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:splines HREF=#d:splines>splines</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
<BR>string</TD><TD ALIGN="CENTER"></TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:start HREF=#d:start>start</A>
</TD><TD>G</TD><TD><A HREF=#k:startType>startType</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>fdp, neato only</TD> </TR>
 <TR><TD><A NAME=a:style HREF=#d:style>style</A>
</TD><TD>ENCG</TD><TD><A HREF=#k:style>style</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:stylesheet HREF=#d:stylesheet>stylesheet</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg only</TD> </TR>
 <TR><TD><A NAME=a:tailURL HREF=#d:tailURL>tailURL</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:tail_lp HREF=#d:tail_lp>tail_lp</A>
</TD><TD>E</TD><TD><A HREF=#k:point>point</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>write only</TD> </TR>
 <TR><TD><A NAME=a:tailclip HREF=#d:tailclip>tailclip</A>
</TD><TD>E</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER">true</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:tailhref HREF=#d:tailhref>tailhref</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:taillabel HREF=#d:taillabel>taillabel</A>
</TD><TD>E</TD><TD><A HREF=#k:lblString>lblString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:tailport HREF=#d:tailport>tailport</A>
</TD><TD>E</TD><TD><A HREF=#k:portPos>portPos</A>
</TD><TD ALIGN="CENTER">center</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:tailtarget HREF=#d:tailtarget>tailtarget</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">&#60;none&#62;</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:tailtooltip HREF=#d:tailtooltip>tailtooltip</A>
</TD><TD>E</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, cmap only</TD> </TR>
 <TR><TD><A NAME=a:target HREF=#d:target>target</A>
</TD><TD>ENGC</TD><TD><A HREF=#k:escString>escString</A>
<BR>string</TD><TD ALIGN="CENTER">&#60;none&#62;</TD><TD></TD><TD>svg, map only</TD> </TR>
 <TR><TD><A NAME=a:tooltip HREF=#d:tooltip>tooltip</A>
</TD><TD>NEC</TD><TD><A HREF=#k:escString>escString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD>svg, cmap only</TD> </TR>
 <TR><TD><A NAME=a:truecolor HREF=#d:truecolor>truecolor</A>
</TD><TD>G</TD><TD><A HREF=#k:bool>bool</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>bitmap output only</TD> </TR>
 <TR><TD><A NAME=a:vertices HREF=#d:vertices>vertices</A>
</TD><TD>N</TD><TD><A HREF=#k:pointList>pointList</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>write only</TD> </TR>
 <TR><TD><A NAME=a:viewport HREF=#d:viewport>viewport</A>
</TD><TD>G</TD><TD><A HREF=#k:viewPort>viewPort</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:voro_margin HREF=#d:voro_margin>voro_margin</A>
</TD><TD>G</TD><TD>double</TD><TD ALIGN="CENTER">0.05</TD><TD>0.0</TD><TD>not dot</TD> </TR>
 <TR><TD><A NAME=a:weight HREF=#d:weight>weight</A>
</TD><TD>E</TD><TD>int<BR>double</TD><TD ALIGN="CENTER">1</TD><TD>0(dot,twopi)<BR>1(neato,fdp)</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:width HREF=#d:width>width</A>
</TD><TD>N</TD><TD>double</TD><TD ALIGN="CENTER">0.75</TD><TD>0.01</TD><TD></TD> </TR>
 <TR><TD><A NAME=a:xdotversion HREF=#d:xdotversion>xdotversion</A>
</TD><TD>G</TD><TD>string</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>xdot only</TD> </TR>
 <TR><TD><A NAME=a:xlabel HREF=#d:xlabel>xlabel</A>
</TD><TD>EN</TD><TD><A HREF=#k:lblString>lblString</A>
</TD><TD ALIGN="CENTER">""</TD><TD></TD><TD></TD> </TR>
 <TR><TD><A NAME=a:xlp HREF=#d:xlp>xlp</A>
</TD><TD>NE</TD><TD><A HREF=#k:point>point</A>
</TD><TD ALIGN="CENTER"></TD><TD></TD><TD>write only</TD> </TR>
 <TR><TD><A NAME=a:z HREF=#d:z>z</A>
</TD><TD>N</TD><TD>double</TD><TD ALIGN="CENTER">0.0</TD><TD>-MAXFLOAT<BR>-1000</TD><TD></TD> </TR>
</TABLE>
<HR>
<H1>Attribute Descriptions</H1>
<DL>
<DT><A NAME=d:Damping HREF=#a:Damping><STRONG>Damping</STRONG></A>
<DD>  Factor damping force motions. On each iteration, a nodes movement
  is limited to this factor of its potential motion. By being less than
  1.0, the system tends to ``cool'', thereby preventing cycling.

<DT><A NAME=d:K HREF=#a:K><STRONG>K</STRONG></A>
<DD>  Spring constant used in virtual physical model. It roughly corresponds
  to an ideal edge length (in inches), in that increasing K tends to
  increase the distance between nodes.
  Note that the edge attribute <A HREF=#d:len>len</A> can be used to
  override this value for adjacent nodes.

<DT><A NAME=d:URL HREF=#a:URL><STRONG>URL</STRONG></A>
<DD>  Hyperlinks incorporated into device-dependent output.
  At present, used in ps2, cmap, i*map and svg formats.
  For all these formats, URLs can be attached to nodes, edges and
  clusters. URL attributes can also be attached to the root graph in ps2,
  cmap and i*map formats. This serves as the base URL for relative URLs in the
  former, and as the default image map file in the latter.
  <P>
  For svg, cmapx and imap output, the active area for a node is its
  visible image.
  For example, an unfilled
  node with no drawn boundary will only be active on its label.
  For other output, the active area is its bounding box.
  The active area for a cluster is its bounding box.
  For edges, the active areas are small circles where the edge contacts its head
  and tail nodes. In addition, for svg, cmapx and imap, the active area
  includes a thin polygon approximating the edge. The circles may
  overlap the related node, and the edge URL dominates.
  If the edge has a label, this will also be active.
  Finally, if the edge has a head or tail label, this will also be active.
  <P>
  Note that, for edges, the attributes <A HREF=#d:headURL>headURL</A>,
  <A HREF=#d:tailURL>tailURL</A>, <A HREF=#d:labelURL>labelURL</A> and
  <A HREF=#d:edgeURL>edgeURL</A> allow control of various parts of an
  edge.
  Also note that, if active areas of two edges overlap, it is unspecified
  which area dominates.

<DT><A NAME=d:_background HREF=#a:_background><STRONG>_background</STRONG></A>
<DD>  A string in the <A HREF=output.html#d:xdot>xdot format</A> specifying an arbitrary background.  
  During rendering, the canvas is first filled as described in the
  <A href=#d:bgcolor>bgcolor attribute</A>. 
  Then, if <b>_background</b> is defined, the graphics
  operations described in the string are performed on the canvas.

<DT><A NAME=d:area HREF=#a:area><STRONG>area</STRONG></A>
<DD>  Indicates the preferred area for a node or empty cluster when laid out by patchwork.

<DT><A NAME=d:arrowhead HREF=#a:arrowhead><STRONG>arrowhead</STRONG></A>
<DD>  Style of arrowhead on the head node of an edge.
  This will only appear if the <A HREF=#d:dir>dir</A> attribute
  is "forward" or "both".
  See the <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:arrowsize HREF=#a:arrowsize><STRONG>arrowsize</STRONG></A>
<DD>  Multiplicative scale factor for arrowheads.

<DT><A NAME=d:arrowtail HREF=#a:arrowtail><STRONG>arrowtail</STRONG></A>
<DD>  Style of arrowhead on the tail node of an edge.
  This will only appear if the <A HREF=#d:dir>dir</A> attribute
  is "back" or "both".
  See the <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:bb HREF=#a:bb><STRONG>bb</STRONG></A>
<DD>  Bounding box of drawing in points.

<DT><A NAME=d:bgcolor HREF=#a:bgcolor><STRONG>bgcolor</STRONG></A>
<DD>  When attached to the root graph, this color is used as the background for
  entire canvas. When a cluster attribute, it is used as the initial
  background for the cluster. If a cluster has a filled
  <A HREF=#d:style>style</A>, the
  cluster's <A HREF=#d:fillcolor>fillcolor</A> will overlay the
  background color.
  <P>
  If the value is a <A HREF=#k:colorList>colorList</A>, a gradient fill is
  used. By default, this is a linear fill; setting <TT>style=radial</TT> will
  cause a radial fill. At present, only two colors are used. If the second
  color (after a colon) is missing, the default color is used for it.
  See also the <A HREF=#d:gradientangle>gradientangle</A> attribute
  for setting the gradient angle. 
  <P>
  For certain output formats, such as PostScript, no fill is done for
  the root graph unless
  <b>bgcolor</b> is explicitly set. For bitmap formats, however, 
  the bits need to be
  initialized to something, so the canvas is filled with white by default.
  This means that if the bitmap output is included in some other
  document, all of the bits within the bitmap's bounding box will be
  set, overwriting whatever color or graphics were already on the page.
  If this effect is not desired, and you only want to set bits explicitly
  assigned in drawing the graph, set <B>bgcolor</B>="transparent".

<DT><A NAME=d:center HREF=#a:center><STRONG>center</STRONG></A>
<DD>  If true, the drawing is centered in the output canvas.

<DT><A NAME=d:charset HREF=#a:charset><STRONG>charset</STRONG></A>
<DD>  Specifies the character encoding used when interpreting string input
  as a text label. The default value is <TT>"UTF-8"</TT>.
  The other legal value is <TT>"iso-8859-1"</TT> or,
  equivalently,
  <TT>"Latin1"</TT>. The <B>charset</B> attribute is case-insensitive.
  Note that if the character encoding used in the input does not
  match the <B>charset</B> value, the resulting output may be very strange.

<DT><A NAME=d:clusterrank HREF=#a:clusterrank><STRONG>clusterrank</STRONG></A>
<DD>  Mode used for handling clusters. If <B>clusterrank</B> is "local", a
  subgraph whose name begins with "cluster" is given special treatment.
  The subgraph is laid out separately, and then integrated as a unit into
  its parent graph, with a bounding rectangle drawn about it.
  If the cluster has a <A HREF=#d:label>label</A> parameter, this label
  is displayed within the rectangle.
  Note also that there can be clusters within clusters.
  At present, the modes "global" and "none"
  appear to be identical, both turning off the special cluster processing.

<DT><A NAME=d:color HREF=#a:color><STRONG>color</STRONG></A>
<DD>  Basic drawing color for graphics, not text. For the latter, use the
  <A HREF=#d:fontcolor>fontcolor</A> attribute.
  <P>
  For edges, the value
  can either be a single color or a <A HREF=#k:colorList>colorList</A>.
  In the latter case, if colorList has no fractions,
  the edge is drawn using parallel splines or lines,
  one for each color in the list, in the order given.
  The head arrow, if any, is drawn using the first color in the list,
  and the tail arrow, if any, the second color. This supports the common
  case of drawing opposing edges, but using parallel splines instead of
  separately routed multiedges. 
  If any fraction is used, the colors are drawn in series, with each color
  being given roughly its specified fraction of the edge.
  For example, the graph
  yields<BR>
  <IMG SRC="colorlist.gif">

<DT><A NAME=d:colorscheme HREF=#a:colorscheme><STRONG>colorscheme</STRONG></A>
<DD>  This attribute specifies a color scheme namespace. If defined, it specifies
  the context for interpreting color names. In particular, if a
  <A HREF=#k:color>color</A> value has form <TT>"xxx"</TT> or <TT>"//xxx"</TT>,
  then the
  color <TT>xxx</TT> will be evaluated according to the current color scheme.
  If no color scheme is set, the standard X11 naming is used.
  For example, if <TT>colorscheme=bugn9</TT>, then <TT>color=7</TT>
  is interpreted as <TT>"/bugn9/7"</TT>.

<DT><A NAME=d:comment HREF=#a:comment><STRONG>comment</STRONG></A>
<DD>  Comments are inserted into output. Device-dependent

<DT><A NAME=d:compound HREF=#a:compound><STRONG>compound</STRONG></A>
<DD>  If true, allow edges between clusters. (See <A HREF=#d:lhead>lhead</A>
  and <A HREF=#d:ltail>ltail</A> below.)

<DT><A NAME=d:concentrate HREF=#a:concentrate><STRONG>concentrate</STRONG></A>
<DD>  If true, use edge concentrators.
  This merges multiedges into a single edge and causes partially parallel
  edges to share part of their paths. The latter feature is not yet available
  outside of dot.

<DT><A NAME=d:constraint HREF=#a:constraint><STRONG>constraint</STRONG></A>
<DD>  If false, the edge is not used in ranking the nodes. For example,
  in the graph
  the edge <CODE>b -> c</CODE> does not add a constraint during rank
  assignment, so the only constraints are that a be above b and c,
  yielding the graph:<BR>
  <IMG SRC="constraint.gif">

<DT><A NAME=d:decorate HREF=#a:decorate><STRONG>decorate</STRONG></A>
<DD>  If true, attach edge label to edge by a 2-segment
  polyline, underlining the label, then going to the closest point of spline.

<DT><A NAME=d:defaultdist HREF=#a:defaultdist><STRONG>defaultdist</STRONG></A>
<DD>  This specifies the distance between nodes in separate connected
  components. If set too small, connected components may overlap.
  Only applicable if <A HREF=#d:pack>pack</A>=false.

<DT><A NAME=d:dim HREF=#a:dim><STRONG>dim</STRONG></A>
<DD>  Set the number of dimensions used for the layout. The maximum value
  allowed is 10.

<DT><A NAME=d:dimen HREF=#a:dimen><STRONG>dimen</STRONG></A>
<DD>  Set the number of dimensions used for rendering. 
  The maximum value allowed is 10.
  If both <TT>dimen</TT> and <TT>dim</TT> are set, the latter specifies
  the dimension used for layout, and the former for rendering.
  If only <TT>dimen</TT> is set, this is used for both layout and rendering
  dimensions.
  <P>
  Note that, at present, all aspects of rendering are 2D. This includes
  the shape and size of nodes, overlap removal, and edge routing. Thus,
  for <TT>dimen &gt; 2</TT>, the only valid information is the <TT>pos</TT>
  attribute of the nodes.
  All other coordinates will be 2D and, at best, will reflect a projection
  of a higher-dimensional point onto the plane.

<DT><A NAME=d:dir HREF=#a:dir><STRONG>dir</STRONG></A>
<DD>  Set edge type for drawing arrowheads. This indicates which ends of the
  edge should be decorated with an arrowhead. The actual style of the
  arrowhead can be specified using the <A HREF=#d:arrowhead>arrowhead</A>
  and <A HREF=#d:arrowtail>arrowtail</A> attributes.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:diredgeconstraints HREF=#a:diredgeconstraints><STRONG>diredgeconstraints</STRONG></A>
<DD>  Only valid when <A HREF=#d:mode>mode</A>="ipsep".
  If true, constraints are generated for each edge in the largest (heuristic)
  directed acyclic subgraph such that the edge must point downwards.
  If "hier", generates level constraints similar to those used with
  <A HREF=#d:mode>mode</A>="hier". The main difference is that, in the latter
  case, only these constraints are involved, so a faster solver can be used.

<DT><A NAME=d:distortion HREF=#a:distortion><STRONG>distortion</STRONG></A>
<DD>  Distortion factor for <A HREF=#d:shape><B>shape</B></A>=polygon.
  Positive values cause top part to
  be larger than bottom; negative values do the opposite.

<DT><A NAME=d:dpi HREF=#a:dpi><STRONG>dpi</STRONG></A>
<DD>  This specifies the expected number of pixels per inch on a display device.
  For bitmap output, this guarantees that text rendering will be
  done more accurately, both in size and in placement. For SVG output,
  it is used to guarantee that the dimensions in the output correspond to
  the correct number of points or inches.

<DT><A NAME=d:edgeURL HREF=#a:edgeURL><STRONG>edgeURL</STRONG></A>
<DD>  If <B>edgeURL</B> is defined, this is the link used for the non-label
  parts of an edge. This value overrides any <A HREF=#d:URL>URL</A>
  defined for the edge.
  Also, this value is used near the head or tail node unless overridden
  by a <A HREF=#d:headURL>headURL</A> or <A HREF=#d:tailURL>tailURL</A> value,
  respectively.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:edgehref HREF=#a:edgehref><STRONG>edgehref</STRONG></A>
<DD>  Synonym for <A HREF=#d:edgeURL>edgeURL</A>.

<DT><A NAME=d:edgetarget HREF=#a:edgetarget><STRONG>edgetarget</STRONG></A>
<DD>  If the edge has a <A HREF=#d:URL>URL</A> or <A HREF=#d:edgeURL>edgeURL</A>
  attribute, this attribute determines which window of the
  browser is used
  for the URL attached to the non-label part of the edge.
  Setting it to "_graphviz" will open a new window if it
  doesn't already exist, or reuse it if it does.
  If undefined, the value of the <A HREF=#d:target>target</A> is used.

<DT><A NAME=d:edgetooltip HREF=#a:edgetooltip><STRONG>edgetooltip</STRONG></A>
<DD>  Tooltip annotation attached to the non-label part of an edge.
  This is used only if the edge has a <A HREF=#d:URL>URL</A>
  or <A HREF=#d:edgeURL>edgeURL</A> attribute.

<DT><A NAME=d:epsilon HREF=#a:epsilon><STRONG>epsilon</STRONG></A>
<DD>  Terminating condition. If the length squared of all energy gradients are
  < <B>epsilon</B>, the algorithm stops.

<DT><A NAME=d:esep HREF=#a:esep><STRONG>esep</STRONG></A>
<DD>  Margin used around polygons for purposes of spline edge routing.
  The interpretation is the same as given for <A HREF=#d:sep>sep</A>.
  This should normally be strictly less than <A HREF=#d:sep>sep</A>.

<DT><A NAME=d:fillcolor HREF=#a:fillcolor><STRONG>fillcolor</STRONG></A>
<DD>  Color used to fill the background of a node or cluster
  assuming <A HREF=#d:style>style</A>=filled, or a filled arrowhead.
  If <B>fillcolor</B> is not defined, <A HREF=#d:color>color</A> is
  used. (For clusters, if <B>color</B> is not defined,
  <A HREF=#d:bgcolor>bgcolor</A> is used.) If this is not defined,
  the default is used, except for
  <A HREF=#d:shape><B>shape</B></A>=point or when the output
  format is MIF,
  which use black by default.
  <P>
  If the value is a <A HREF=#k:colorList>colorList</A>, a gradient fill is
  used. By default, this is a linear fill; setting <TT>style=radial</TT> will
  cause a radial fill. At present, only two colors are used. If the second
  color (after a colon) is missing, the default color is used for it.
  See also the <A HREF=#d:gradientangle>gradientangle</A> attribute
  for setting the gradient angle. 
  <P>
  Note that a cluster inherits the root graph's attributes if defined.
  Thus, if the root graph has defined a <B>fillcolor</B>, this will override a
  <B>color</B> or <B>bgcolor</B> attribute set for the cluster.

<DT><A NAME=d:fixedsize HREF=#a:fixedsize><STRONG>fixedsize</STRONG></A>
<DD>  If <tt>false</tt>, the size of a node is determined by smallest width and height
  needed to contain its label and image, if any, with a margin specified by
  the <A HREF=#d:margin><TT>margin</TT></A> attribute. The width
  and height must also be at least as large as the sizes specified by the
  <A HREF=#d:width><TT>width</TT></A> and
  <A HREF=#d:height><TT>height</TT></A> attributes, which specify
  the minimum values for these parameters. 
  <P>
  If <tt>true</tt>, the node size is specified by the values of the
  <A HREF=#d:width><TT>width</TT></A>
  and <A HREF=#d:height><TT>height</TT></A> attributes only
  and is not expanded to contain the text label.
  There will be a warning if the label (with margin)
  cannot fit within these limits.
  <P>
  If the <A HREF=attrs.html#d:fixedsize><TT>fixedsize</TT></A> attribute is set 
  to <tt>shape</tt>, the <A HREF=#d:width><TT>width</TT></A> and
  <A HREF=#d:height><TT>height</TT></A> attributes also determine the size
  of the node shape, but the label can be much larger. Both the label and
  shape sizes are used when avoiding node overlap, but all edges to the
  node ignore the label and only contact the node shape. No warning is given
  if the label is too large.

<DT><A NAME=d:fontcolor HREF=#a:fontcolor><STRONG>fontcolor</STRONG></A>
<DD>  Color used for text.

<DT><A NAME=d:fontname HREF=#a:fontname><STRONG>fontname</STRONG></A>
<DD>  Font used for text. This very much depends on the output format and, for
  non-bitmap output such as PostScript or SVG, the availability of the font
  when the graph is displayed or printed. As such, it is best to rely on
  font faces that are generally available, such as Times-Roman, Helvetica or
  Courier.
  <P>
  How font names are resolved also depends on the underlying library that handles
  font name resolution.
  If Graphviz was built using the
  <A HREF=http://pdx.freedesktop.org/~fontconfig/fontconfig-user.html>fontconfig library</A>, 
  the latter library will be used to search for the font. 
  See the commands <B>fc-list</B>, <B>fc-match</B> and the other fontconfig commands for how
  names are resolved and which fonts are available.
  Other systems may provide their own font package, such as Quartz for OS X.
  <P>
  Note that various font attributes, such as weight and slant, can be built into the
  font name. Unfortunately, the syntax varies depending on which font system is dominant. 
  Thus, using <TT>fontname="times bold italic"</TT> will produce a bold, slanted Times font 
  using Pango, the usual main font library. Alternatively,  
  <TT>fontname="times:italic"</TT> will produce a slanted
  Times font from fontconfig, while <TT>fontname="times-bold"</TT> will resolve to a bold
  Times using Quartz. You will need
  to ascertain which package is used by your Graphviz system and refer to the relevant
  documentation.
  <P>
  If Graphviz is not built with a high-level font library, <TT>fontname</TT> will be
  considered the name of a Type 1 or True Type font file.
  If you specify <TT>fontname=schlbk</TT>, the tool will look for a
  file named  <TT>schlbk.ttf</TT> or <TT>schlbk.pfa</TT> or <TT>schlbk.pfb</TT>
  in one of the directories specified by
  the <A HREF=#d:fontpath>fontpath</A> attribute.
  The lookup does support various aliases for the common fonts.

<DT><A NAME=d:fontnames HREF=#a:fontnames><STRONG>fontnames</STRONG></A>
<DD>  Allows user control of how basic fontnames are represented in SVG output.
  If <TT>fontnames</TT> is undefined or <TT>"svg"</TT>,
  the output will try to use known SVG fontnames. For example, the
  default font  <TT>"Times-Roman"</TT> will be mapped to the
  basic SVG font <TT>"serif"</TT>. This can be overridden by setting
  <TT>fontnames</TT> to  <TT>"ps"</TT> or  <TT>"gd"</TT>.
  In the former case, known PostScript font names such as
  <TT>"Times-Roman"</TT> will be used in the output.
  In the latter case, the fontconfig font conventions
  are used. Thus, <TT>"Times-Roman"</TT> would be treated as
  <TT>"Nimbus Roman No9 L"</TT>. These last two options are useful
  with SVG viewers that support these richer fontname spaces.

<DT><A NAME=d:fontpath HREF=#a:fontpath><STRONG>fontpath</STRONG></A>
<DD>  Directory list used by libgd to search for bitmap fonts if Graphviz
  was not built with the fontconfig library.
  If <B>fontpath</B> is not set, the environment
  variable <TT>DOTFONTPATH</TT> is checked.
  If that is not set, <TT>GDFONTPATH</TT> is checked.
  If not set, libgd uses its compiled-in font path.
  Note that fontpath is an attribute of the root graph.

<DT><A NAME=d:fontsize HREF=#a:fontsize><STRONG>fontsize</STRONG></A>
<DD>  Font size, <A HREF=#points>in points</A>, used for text.

<DT><A NAME=d:forcelabels HREF=#a:forcelabels><STRONG>forcelabels</STRONG></A>
<DD>  If true, all  <A HREF=#d:xlabel><B>xlabel</B></A> attributes are placed, even if there is some overlap with nodes
  or other labels.

<DT><A NAME=d:gradientangle HREF=#a:gradientangle><STRONG>gradientangle</STRONG></A>
<DD>  If a gradient fill is being used, this determines the angle of the fill. For linear fills, the colors transform
  along a line specified by the angle and the center of the object. For radial fills, a value of zero causes the
  colors to transform radially from the center; for non-zero values, the colors transform from a point near the
  object's periphery as specified by the value.
  <P>
  If unset, the default angle is 0.

<DT><A NAME=d:group HREF=#a:group><STRONG>group</STRONG></A>
<DD>  If the end points of an edge belong to the same group, i.e., have the
  same group attribute, parameters are set to avoid crossings and keep
  the edges straight.

<DT><A NAME=d:headURL HREF=#a:headURL><STRONG>headURL</STRONG></A>
<DD>  If <B>headURL</B> is defined, it is
  output as part of the head label of the edge.
  Also, this value is used near the head node, overriding any
  <A HREF=#d:URL>URL</A> value.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:head_lp HREF=#a:head_lp><STRONG>head_lp</STRONG></A>
<DD>  Position of an edge's head label, <A HREF=#points>in points</A>.
  The position indicates the center of the label.

<DT><A NAME=d:headclip HREF=#a:headclip><STRONG>headclip</STRONG></A>
<DD>  If true, the head of an edge is clipped to the boundary of the head node;
  otherwise, the end of the edge goes to the center of the node, or the
  center of a port, if applicable.

<DT><A NAME=d:headhref HREF=#a:headhref><STRONG>headhref</STRONG></A>
<DD>  Synonym for <A HREF=#d:headURL>headURL</A>.

<DT><A NAME=d:headlabel HREF=#a:headlabel><STRONG>headlabel</STRONG></A>
<DD>  Text label to be placed near head of edge.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:headport HREF=#a:headport><STRONG>headport</STRONG></A>
<DD>  Indicates where on the head node to attach the head of the edge.
  In the default case, the edge is aimed towards the center of the node,
  and then clipped at the node boundary.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:headtarget HREF=#a:headtarget><STRONG>headtarget</STRONG></A>
<DD>  If the edge has a <A HREF=#d:headURL>headURL</A>,
  this attribute determines which window of the
  browser is used
  for the URL. Setting it to "_graphviz" will open a new window if it
  doesn't already exist, or reuse it if it does.
  If undefined, the value of the <A HREF=#d:target>target</A> is used.

<DT><A NAME=d:headtooltip HREF=#a:headtooltip><STRONG>headtooltip</STRONG></A>
<DD>  Tooltip annotation attached to the head of an edge. This is used only
  if the edge has a <A HREF=#d:headURL>headURL</A> attribute.

<DT><A NAME=d:height HREF=#a:height><STRONG>height</STRONG></A>
<DD>  Height of node, in inches. This is taken as the initial, minimum height
  of the node. If <A HREF=#d:fixedsize><B>fixedsize</B></A> is true, this
  will be the final height of the node. Otherwise, if the node label
  requires more height to fit, the node's height will be increased to
  contain the label. Note also that, if the output format is dot, the
  value given to <B>height</B> will be the final value.
  <P>
  If the node shape is regular, the width and height are made identical.
  In this case, if either the width or the height is set explicitly,
  that value is used.
  In this case, if both the width or the height are set explicitly,
  the maximum of the two values is used.
  If neither is set explicitly, the minimum of the two default values
  is used.

<DT><A NAME=d:href HREF=#a:href><STRONG>href</STRONG></A>
<DD>  Synonym for <A HREF=#d:URL>URL</A>.

<DT><A NAME=d:id HREF=#a:id><STRONG>id</STRONG></A>
<DD>  Allows the graph author to provide an id for graph objects which is to be included in the output.
  Normal "&#92;N", "&#92;E", "&#92;G" substitutions are applied.
  If provided, it is the responsibility of the provider to keep
  its values sufficiently unique for its intended downstream use.
  Note, in particular, that "&#92;E" does not provide a unique id for multi-edges.
  If no id attribute is provided, then a unique internal id is used. However, 
  this value is unpredictable by the graph writer.
  An externally provided id is not used internally.
  <P>
  If the graph provides an id attribute, this will be used as a prefix for
  internally generated attributes. By making these distinct, the user
  can include multiple image maps in the same document.

<DT><A NAME=d:image HREF=#a:image><STRONG>image</STRONG></A>
<DD>  Gives the name of a file containing an image to be displayed inside
  a node. The image file must be in one of the recognized 
  <A HREF=output.html#d:image_fmts>formats</A>,
  typically JPEG, PNG, GIF, BMP, SVG or Postscript, and be able to be converted
  into the desired output format.
  <P>
  The file must contain the image size information. This is usually trivially
  true for the bitmap formats. For PostScript, the file must contain a
  line starting with <TT>%%BoundingBox: </TT> followed by four integers
  specifying the lower left x and y coordinates and the upper right x and y
  coordinates of the bounding box for the image, the coordinates being in
  points. An SVG image file must contain <TT>width</TT> and <TT>height</TT>
  attributes, typically as part of the <TT>svg</TT> element.
  The values for these should have the form of a floating point number,
  followed by optional units, e.g., <TT>width="76pt"</TT>. 
  Recognized units are <TT>in</TT>, <TT>px</TT>,
  <TT>pc</TT>, <TT>pt</TT>, <TT>cm</TT> and <TT>mm</TT> for inches, pixels,
  picas, points, centimeters and millimeters, respectively.
  The default unit is points.
  <P>
  Unlike with the <A HREF=#d:shapefile>shapefile</A> attribute,
  the image is treated as node
  content rather than the entire node. In particular, an image can
  be contained in a node of any shape, not just a rectangle.

<DT><A NAME=d:imagepath HREF=#a:imagepath><STRONG>imagepath</STRONG></A>
<DD>  Specifies a list of directories in which to look for image files as specified by the
  <a href="#d:image">image</a> attribute or using the <TT>IMG</TT> element in
  <a href="shapes.html#html">HTML-like labels</a>.
  The string should be a list of (absolute or relative) pathnames, each separated by
  a semicolon (for Windows) or a colon (all other OS). 
  The first directory in which a file of the given name is found will be used to
  load the image. If <tt>imagepath</tt> is not set, relative pathnames for the image
  file will be interpreted with respect to the current working directory.

<DT><A NAME=d:imagepos HREF=#a:imagepos><STRONG>imagepos</STRONG></A>
<DD>  Attribute controlling how an image is positioned within its containing node.  This
  only has an effect when the image is smaller than the containing node.  The
  default is to be centered both horizontally and vertically.  Valid values:
  <TABLE>
  <TR><TD>tl</TD><TD>Top Left</TD></TR>
  <TR><TD>tc</TD><TD>Top Centered</TD></TR>
  <TR><TD>tr</TD><TD>Top Right</TD></TR>
  <TR><TD>ml</TD><TD>Middle Left</TD></TR>
  <TR><TD>mc</TD><TD>Middle Centered <I>(the default)</I></TD></TR>
  <TR><TD>mr</TD><TD>Middle Right</TD></TR>
  <TR><TD>bl</TD><TD>Bottom Left</TD></TR>
  <TR><TD>bc</TD><TD>Bottom Centered</TD></TR>
  <TR><TD>br</TD><TD>Bottom Right</TD></TR>
  </TABLE>

<DT><A NAME=d:imagescale HREF=#a:imagescale><STRONG>imagescale</STRONG></A>
<DD>  Attribute controlling how an image fills its
  containing node. In general, the image is given its natural size,
  (cf. <A HREF=#d:dpi>dpi</A>),
  and the node size is made large enough to contain its image, its
  label, its margin, and its peripheries.
  Its width and height will also be at least as large as its
  minimum <A HREF=#d:width>width</A> and <A HREF=#d:height>height</A>.
  If, however, <TT>fixedsize=true</TT>,
  the width and height attributes specify the exact size of the node.
  <P>
  During rendering, in the default case (<TT>imagescale=false</TT>),
  the image retains its natural size.
  If <TT>imagescale=true</TT>,
  the image is uniformly scaled (i.e., its aspect ratio is
  preserved) to fit inside the node.
  At least one dimension of the image will be as large as possible
  given the size of the node.
  When <TT>imagescale=width</TT>,
  the width of the image is scaled to fill the node width.
  The corresponding property holds when <TT>imagescale=height</TT>.
  When <TT>imagescale=both</TT>,
  both the height and the width are scaled separately to fill the node.
  <P>
  In all cases, if a dimension of the image is larger than the
  corresponding dimension of the node, that dimension of the
  image is scaled down to fit the node. As with the case of
  expansion, if  <TT>imagescale=true</TT>, width and height are
  scaled uniformly.

<DT><A NAME=d:inputscale HREF=#a:inputscale><STRONG>inputscale</STRONG></A>
<DD>  For layout algorithms that support initial input positions (specified by the <A HREF=#d:pos><B>pos</B></A> attribute),
  this attribute can be used to appropriately scale the values. By default, fdp and neato interpret
  the x and y values of pos as being in inches. (<B>NOTE</B>: neato -n(2) treats the coordinates as
  being in points, being the unit used by the layout algorithms for the pos attribute.) Thus, if
  the graph has pos attributes in points, one should set <TT>inputscale=72</TT>.
  This can also be set on the command line using the <A HREF=command.html#minusK><TT>-s</TT> flag</A> flag.
  <P>
  If not set, no scaling is done and the units on input are treated as inches.
  A value of 0 is equivalent to <TT>inputscale=72</TT>.

<DT><A NAME=d:label HREF=#a:label><STRONG>label</STRONG></A>
<DD>  Text label attached to objects.
  If a node's <A HREF=#d:shape>shape</A> is record, then the label can
  have a <A HREF=shapes.html#record>special format</A>
  which describes the record layout.
  <P>
  Note that a node's default label is "&#92;N", so the node's name or ID becomes
  its label. Technically, a node's name can be an HTML string but this will not
  mean that the node's label will be interpreted as an <a href="shapes.html#html">HTML-like label</a>. This is
  because the node's actual label is an ordinary string, which will be replaced 
  by the raw bytes stored in the node's name.
  To get an HTML-like label, the label attribute value itself must be an HTML string.

<DT><A NAME=d:labelURL HREF=#a:labelURL><STRONG>labelURL</STRONG></A>
<DD>  If <B>labelURL</B> is defined, this is the link used for the label
  of an edge. This value overrides any <A HREF=#d:URL>URL</A>
  defined for the edge.

<DT><A NAME=d:label_scheme HREF=#a:label_scheme><STRONG>label_scheme</STRONG></A>
<DD>  The value indicates
  whether to treat a node whose name has the form |edgelabel|* as a special node representing an edge label. 
  The default (0) produces no effect.
  If the attribute is set to 1, sfdp uses a penalty-based method to make that kind of node close to the 
  center of its neighbor. With a value of 2, sfdp uses a penalty-based method to make that kind of node 
  close to the old center of its neighbor. Finally, a value of 3 invokes a two-step process of overlap 
  removal and straightening.

<DT><A NAME=d:labelangle HREF=#a:labelangle><STRONG>labelangle</STRONG></A>
<DD>  This, along with <A HREF=#d:labeldistance>labeldistance</A>, determine
  where the
  headlabel (taillabel) are placed with respect to the head (tail)
  in polar coordinates. The origin in the coordinate system is
  the point where the edge touches the node. The ray of 0 degrees
  goes from the origin back along the edge, parallel to the edge
  at the origin.
  <P>
  The angle, in degrees, specifies the rotation from the 0 degree ray,
  with positive angles moving counterclockwise and negative angles
  moving clockwise.

<DT><A NAME=d:labeldistance HREF=#a:labeldistance><STRONG>labeldistance</STRONG></A>
<DD>  Multiplicative scaling factor adjusting the distance that
  the headlabel(taillabel) is from the head(tail) node.
  The default distance is 10 points. See <A HREF=#d:labelangle>labelangle</A>
  for more details.

<DT><A NAME=d:labelfloat HREF=#a:labelfloat><STRONG>labelfloat</STRONG></A>
<DD>  If true, allows edge labels to be less constrained in position.
  In particular, it may appear on top of other edges.

<DT><A NAME=d:labelfontcolor HREF=#a:labelfontcolor><STRONG>labelfontcolor</STRONG></A>
<DD>  Color used for headlabel and taillabel.
  If not set, defaults to edge's fontcolor.

<DT><A NAME=d:labelfontname HREF=#a:labelfontname><STRONG>labelfontname</STRONG></A>
<DD>  Font used for headlabel and taillabel.
  If not set, defaults to edge's fontname.

<DT><A NAME=d:labelfontsize HREF=#a:labelfontsize><STRONG>labelfontsize</STRONG></A>
<DD>  Font size, <A HREF=#points>in points</A>, used for headlabel and taillabel.
  If not set, defaults to edge's fontsize.

<DT><A NAME=d:labelhref HREF=#a:labelhref><STRONG>labelhref</STRONG></A>
<DD>  Synonym for <A HREF=#d:labelURL>labelURL</A>.

<DT><A NAME=d:labeljust HREF=#a:labeljust><STRONG>labeljust</STRONG></A>
<DD>  Justification for cluster labels. If "r", the label
  is right-justified within bounding rectangle; if "l", left-justified;
  else the label is centered.
  Note that a subgraph inherits attributes from its parent. Thus, if
  the root graph sets <B>labeljust</B> to "l", the subgraph inherits
  this value.

<DT><A NAME=d:labelloc HREF=#a:labelloc><STRONG>labelloc</STRONG></A>
<DD>  Vertical placement of labels for nodes, root graphs and clusters.
  <P>
  For graphs and clusters, only "t" and "b" are allowed, corresponding
  to placement at the top and bottom, respectively.
  By default, root
  graph labels go on the bottom and cluster labels go on the top.
  Note that a subgraph inherits attributes from its parent. Thus, if
  the root graph sets <B>labelloc</B> to "b", the subgraph inherits
  this value.
  <P>
  For nodes, this attribute is used only when the height of the node
  is larger than the height of its label. 
  If <TT>labelloc</TT> is set to "t", "c", or "b", the label is aligned
  with the top, centered, or aligned with the bottom of the node, respectively.
  In the default case, the label is vertically centered.

<DT><A NAME=d:labeltarget HREF=#a:labeltarget><STRONG>labeltarget</STRONG></A>
<DD>  If the edge has a <A HREF=#d:URL>URL</A> or <A HREF=#d:labelURL>labelURL</A>
  attribute, this attribute determines which window of the
  browser is used
  for the URL attached to the label.
  Setting it to "_graphviz" will open a new window if it
  doesn't already exist, or reuse it if it does.
  If undefined, the value of the <A HREF=#d:target>target</A> is used.

<DT><A NAME=d:labeltooltip HREF=#a:labeltooltip><STRONG>labeltooltip</STRONG></A>
<DD>  Tooltip annotation attached to label of an edge.
  This is used only if the edge has a <A HREF=#d:URL>URL</A>
  or <A HREF=#d:labelURL>labelURL</A> attribute.

<DT><A NAME=d:landscape HREF=#a:landscape><STRONG>landscape</STRONG></A>
<DD>  If true, the graph is rendered in landscape mode. Synonymous with
  <A HREF=#d:rotate><TT>rotate=90</TT></A> or
  <A HREF=#d:orientation><TT>orientation=landscape</TT></A>.

<DT><A NAME=d:layer HREF=#a:layer><STRONG>layer</STRONG></A>
<DD>  Specifies layers in which the node, edge or cluster is present.

<DT><A NAME=d:layerlistsep HREF=#a:layerlistsep><STRONG>layerlistsep</STRONG></A>
<DD>  Specifies the separator characters used to split
  an attribute of type <A HREF=#k:layerRange>layerRange</A> into a list of ranges.

<DT><A NAME=d:layers HREF=#a:layers><STRONG>layers</STRONG></A>
<DD>  Specifies a linearly ordered list of layer names attached to the graph
  The graph is then output in separate layers. Only those components
  belonging to the current output layer appear. For more information,
  see the page <A HREF="../../../faq/#FaqOverlays">How to use drawing layers (overlays)</A>.

<DT><A NAME=d:layerselect HREF=#a:layerselect><STRONG>layerselect</STRONG></A>
<DD>  Selects a list of layers to be emitted.

<DT><A NAME=d:layersep HREF=#a:layersep><STRONG>layersep</STRONG></A>
<DD>  Specifies the separator characters used to split the
  <A HREF=#d:layers>layers</A> attribute into a list of layer names.

<DT><A NAME=d:layout HREF=#a:layout><STRONG>layout</STRONG></A>
<DD>  Specifies the name of the layout algorithm to use, such as "dot"
  or "neato". Normally, graphs should be kept independent of a type of
  layout. In some cases, however, it can be convenient to embed the type
  of layout desired within the graph. For example, a graph containing
  position information from a layout might want to record what the
  associated layout algorithm was.
  <P>
  This attribute takes precedence over 
  the <A HREF=command.html#minusK>-K flag</A> 
  or the actual command name used.

<DT><A NAME=d:len HREF=#a:len><STRONG>len</STRONG></A>
<DD>  Preferred edge length, in inches.

<DT><A NAME=d:levels HREF=#a:levels><STRONG>levels</STRONG></A>
<DD>  Number of levels allowed in the multilevel scheme.

<DT><A NAME=d:levelsgap HREF=#a:levelsgap><STRONG>levelsgap</STRONG></A>
<DD>  Specifies strictness of level constraints in neato
  when <TT><A HREF=#d:mode>mode</A>="ipsep" or "hier"</TT>.
  Larger positive values mean stricter constraints, which demand more
  separation between levels. On the other hand, negative values will relax
  the constraints by allowing some overlap between the levels.

<DT><A NAME=d:lhead HREF=#a:lhead><STRONG>lhead</STRONG></A>
<DD>  Logical head of an edge. When <A HREF=#d:compound><B>compound</B></A> is true,
  if <B>lhead</B> is defined and is the name of a cluster containing
  the real head,
  the edge is clipped to the boundary of the cluster.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:lheight HREF=#a:lheight><STRONG>lheight</STRONG></A>
<DD>  Height of graph or cluster label, in inches.

<DT><A NAME=d:lp HREF=#a:lp><STRONG>lp</STRONG></A>
<DD>  Label position, <A HREF=#points>in points</A>.
  The position indicates the center of the label.

<DT><A NAME=d:ltail HREF=#a:ltail><STRONG>ltail</STRONG></A>
<DD>  Logical tail of an edge. When <A HREF=#d:compound><B>compound</B></A> is true,
  if <B>ltail</B> is defined and is the name of a cluster
  containing the real tail,
  the edge is clipped to the boundary of the cluster.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:lwidth HREF=#a:lwidth><STRONG>lwidth</STRONG></A>
<DD>  Width of graph or cluster label, in inches.

<DT><A NAME=d:margin HREF=#a:margin><STRONG>margin</STRONG></A>
<DD>  For graphs, this sets x and y margins of canvas, in inches. If the margin
  is a single double, both margins are set equal to the given value.
  <P>
  Note that the margin is not part of the drawing but just empty space
  left around the drawing. It basically corresponds to a translation of
  drawing, as would be necessary to center a drawing on a page. Nothing
  is actually drawn in the margin. To actually extend the background of
  a drawing, see the <A HREF=#d:pad>pad</A> attribute.
  <P>
  For clusters, this specifies the space between the nodes in the cluster and
  the cluster bounding box. By default, this is 8 points.
  <P>
  For nodes, this attribute specifies space left around the node's label.
  By default, the value is <TT>0.11,0.055</TT>.

<DT><A NAME=d:maxiter HREF=#a:maxiter><STRONG>maxiter</STRONG></A>
<DD>  Sets the number of iterations used.

<DT><A NAME=d:mclimit HREF=#a:mclimit><STRONG>mclimit</STRONG></A>
<DD>  Multiplicative scale factor used to alter the MinQuit (default = 8)
  and MaxIter (default = 24) parameters used during crossing
  minimization. These correspond to the
  number of tries without improvement before quitting and the
  maximum number of iterations in each pass.

<DT><A NAME=d:mindist HREF=#a:mindist><STRONG>mindist</STRONG></A>
<DD>  Specifies the minimum separation between all nodes.

<DT><A NAME=d:minlen HREF=#a:minlen><STRONG>minlen</STRONG></A>
<DD>  Minimum edge length (rank difference between head and tail).

<DT><A NAME=d:mode HREF=#a:mode><STRONG>mode</STRONG></A>
<DD>  Technique for optimizing the layout. For neato, if <B>mode</B> is <TT>"major"</TT>,
  neato uses stress majorization. If <B>mode</B> is <TT>"KK"</TT>,
  neato uses a version of the gradient descent method. The only advantage
  to the latter technique is that it is sometimes appreciably faster for
  small (number of nodes < 100) graphs. A significant disadvantage is that
  it may cycle.
  <P>
  There are two experimental modes in neato, "hier", which adds a top-down
  directionality similar to the layout used in dot, and "ipsep", which
  allows the graph to specify minimum vertical and horizontal distances
  between nodes. (See the <A HREF=#d:sep>sep</A> attribute.)
  <P>
  For sfdp, the default <B>mode</B> is <TT>"spring"</TT>, which corresponds to using
  a spring-electrical model. Setting <B>mode</B> to <TT>"maxent"</TT> causes a similar
  model to be run but one that also takes into account edge lengths specified by the
  <TT>"len"</TT> attribute.

<DT><A NAME=d:model HREF=#a:model><STRONG>model</STRONG></A>
<DD>  This value specifies how the distance matrix is computed for the input
  graph. The distance matrix specifies the ideal distance between every
  pair of nodes. neato attemps to find a layout which best achieves
  these distances. By default, it uses the length of the shortest path,
  where the length of each edge is given by its <A HREF=#d:len>len</A>
  attribute. If <B>model</B> is <TT>"circuit"</TT>, neato uses the
  circuit resistance
  model to compute the distances. This tends to emphasize clusters. If
  <B>model</B> is <TT>"subset"</TT>, neato uses the subset model. This sets the
  edge length to be the number of nodes that are neighbors of exactly one
  of the end points, and then calculates the shortest paths. This helps
  to separate nodes with high degree.
  <P>
  For more control of distances, one can use <TT>model=mds</TT>. In this
  case, the <A HREF=#d:len>len</A> of an edge is used as the ideal distance
  between its vertices. A shortest path calculation is only used for
  pairs of nodes not connected by an edge. Thus, by supplying a complete
  graph, the input can specify all of the relevant distances.

<DT><A NAME=d:mosek HREF=#a:mosek><STRONG>mosek</STRONG></A>
<DD>  If Graphviz is built with MOSEK defined, mode=ipsep and mosek=true,
  the Mosek software (www.mosek.com) is use to solve the ipsep constraints.

<DT><A NAME=d:newrank HREF=#a:newrank><STRONG>newrank</STRONG></A>
<DD>  The original ranking algorithm in dot is recursive on clusters. This can produce fewer ranks
  and a more compact layout, but sometimes at the cost of a head node being place on a higher
  rank than the tail node. It also assumes that a node is not constrained in separate, 
  incompatible subgraphs. For example, a node cannot be in a cluster and also be constrained by
  <TT>rank=same</TT> with a node not in the cluster.
  <P>
  If <TT>newrank=true</TT>, the ranking algorithm does a single global ranking, ignoring clusters.
  This allows nodes to be subject to multiple constraints. Rank constraints will usually take
  precedence over edge constraints.

<DT><A NAME=d:nodesep HREF=#a:nodesep><STRONG>nodesep</STRONG></A>
<DD>  In dot, this specifies the minimum space between two adjacent nodes in the same rank, in inches.
  <P>
  For other layouts, this affects the spacing between loops on a single node, or multiedges between
  a pair of nodes.

<DT><A NAME=d:nojustify HREF=#a:nojustify><STRONG>nojustify</STRONG></A>
<DD>  By default, the justification of multi-line labels is done within the
  largest context that makes sense. Thus, in the label of a polygonal
  node, a left-justified line will align with the left side of the node
  (shifted by the prescribed <A HREF=#d:margin>margin</A>).
  In record nodes, left-justified
  line will line up with the left side of the enclosing column of fields.
  If <B>nojustify</B> is <TT>"true"</TT>, multi-line labels will be justified
  in the context of itself. For example, if the attribute is set,
  the first label line is long, and the second is shorter and left-justified,
  the second will align with the left-most character in the first line,
  regardless of  how large the node might be.

<DT><A NAME=d:normalize HREF=#a:normalize><STRONG>normalize</STRONG></A>
<DD>  If set, normalize coordinates of final
  layout so that the first point is at the origin, and then rotate the
  layout so that the angle of the first edge is specified by the value of <TT>normalize</TT> in degrees.
  If  <TT>normalize</TT> is not a number, it is evaluated as a  <TT>bool</TT>, with true
  corresponding to 0 degrees. <B>NOTE:</B> Since the attribute is evaluated first as a number,
  0 and 1 cannot be used for false and true.

<DT><A NAME=d:notranslate HREF=#a:notranslate><STRONG>notranslate</STRONG></A>
<DD>  By default, the final layout is translated so that the lower-left corner of the bounding box is
  at the origin. This can be annoying if some nodes are pinned or if the user runs <TT>neato -n</TT>. 
  To avoid this translation, set <TT>notranslate</TT> to true.

<DT><A NAME=d:nslimit HREF=#a:nslimit><STRONG>nslimit</STRONG></A>
,<DT><A NAME=d:nslimit1 HREF=#a:nslimit1><STRONG>nslimit1</STRONG></A>
<DD>  Used to set number of iterations in
  network simplex applications. <B>nslimit</B> is used in
  computing node x coordinates, <B>nslimit1</B> for ranking nodes.
  If defined, # iterations =  <B>nslimit(1)</B> * # nodes;
  otherwise,  # iterations = MAXINT.

<DT><A NAME=d:ordering HREF=#a:ordering><STRONG>ordering</STRONG></A>
<DD>  If the value of the attribute is "out", then
  the outedges of a node, that is, edges with the node as its tail node,
  must appear
  left-to-right in the same order in which they are defined in
  the input.
  If the value of the attribute is "in", then
  the inedges of a node must appear
  left-to-right in the same order in which they are defined in
  the input.
  If defined as a graph or subgraph attribute, the value is applied to all nodes
  in the graph or subgraph. Note that the graph attribute takes
  precedence over the node attribute.

<DT><A NAME=d:orientation HREF=#a:orientation><STRONG>orientation</STRONG></A>
<DD>  Angle, in degrees, used to rotate polygon node shapes. For any number of polygon sides, 0 degrees rotation results in a flat base.

<DT><A NAME=dd:orientation HREF=#aa:orientation><STRONG>orientation</STRONG></A>
<DD>  If "[lL]*", set graph orientation to landscape
  Used only if <A HREF=#d:rotate><B>rotate</B></A> is not defined.

<DT><A NAME=d:outputorder HREF=#a:outputorder><STRONG>outputorder</STRONG></A>
<DD>  Specify order in which nodes and edges are drawn.

<DT><A NAME=d:overlap HREF=#a:overlap><STRONG>overlap</STRONG></A>
<DD>  Determines if and how node overlaps should be removed. Nodes are first
  enlarged using the <A HREF=#d:sep><B>sep</B></A> attribute.
  If "true" , overlaps are retained.
  If the value is "scale", overlaps are removed by uniformly scaling in x and y.
  If the value converts to "false", and it is available, Prism, a proximity graph-based algorithm, is
  used to remove node overlaps.
  This can also be invoked explicitly with "overlap=prism".
  This technique starts with a
  small scaling up, controlled by the 
  <A HREF="#d:overlap_scaling"><TT>overlap_scaling</TT></A> attribute,
  which can remove a significant portion of the overlap.
  The prism option also accepts an optional non-negative integer suffix.
  This can be used to control the number of attempts made at overlap
  removal. By default, <TT>overlap="prism"</TT> is equivalent to
  <TT>overlap="prism1000"</TT>. Setting <TT>overlap="prism0"</TT>
  causes only the scaling phase to be run.
  <P>
  If Prism is not available, or the version of Graphviz is earlier than 2.28, "overlap=false"
  uses a Voronoi-based technique.
  This can always be invoked explicitly with "overlap=voronoi".
  <P>
  If the value is "scalexy", x and y are separately
  scaled to remove overlaps.
  <P>
  If the value is "compress", the layout will be scaled down as much as
  possible without introducing any overlaps, obviously assuming there are
  none to begin with.
  <P>
  <B>N.B.</B>The remaining allowed values of <TT>overlap</TT>
  correspond to algorithms which, at present, can produce bad aspect ratios.
  In addition, we deprecate the use of the "ortho*" and "portho*".
  <P>
  If the value is "vpsc", overlap removal is done as a
  quadratic optimization to minimize node displacement while removing
  node overlaps.
  <P>
  If the value is "orthoxy" or "orthoyx", overlaps
  are moved by optimizing two constraint problems, one for the x axis and
  one for the y. The suffix indicates which axis is processed first.
  If the value is "ortho", the technique is similar to "orthoxy" except a
  heuristic is used to reduce the bias between the two passes.
  If the value is "ortho_yx", the technique is the same as "ortho", except
  the roles of x and y are reversed.
  The values "portho", "porthoxy", "porthoxy", and "portho_yx" are similar
  to the previous four, except only pseudo-orthogonal ordering is
  enforced.
  <P>
  If the layout is done by neato with <A HREF=#d:mode>mode</A>="ipsep",
  then one can use <TT>overlap=ipsep</TT>.
  In this case, the overlap removal constraints are
  incorporated into the layout algorithm itself.
  N.B. At present, this only supports one level of clustering.
  <P>
  Except for fdp and sfdp, the layouts assume <TT>overlap="true"</TT> as the default.
  Fdp first uses a number of passes using a built-in, force-directed technique
  to try to remove overlaps. Thus, fdp accepts <B>overlap</B> with an integer
  prefix followed by a colon, specifying the number of tries. If there is
  no prefix, no initial tries will be performed. If there is nothing following
  a colon, none of the above methods will be attempted. By default, fdp
  uses <TT>overlap="9:prism"</TT>. Note that <TT>overlap="true"</TT>,
  <TT>overlap="0:true"</TT> and <TT>overlap="0:"</TT> all turn off all overlap
  removal.
  <P>
  By default, sfdp uses <TT>overlap="prism0"</TT>.
  <P>
  Except for the Voronoi and prism methods, all of these transforms preserve the
  orthogonal ordering of the original layout. That is, if the x coordinates
  of two nodes are originally the same, they will remain the same, and if
  the x coordinate of one node is originally less than the x coordinate of
  another, this relation will still hold in the transformed layout. The
  similar properties hold for the y coordinates.
  This is not quite true for the "porth*" cases. For these, orthogonal
  ordering is only preserved among nodes related by an edge.

<DT><A NAME=d:overlap_scaling HREF=#a:overlap_scaling><STRONG>overlap_scaling</STRONG></A>
<DD>  When <TT>overlap=prism</TT>, the layout is scaled by this factor, thereby
  removing a fair amount of node overlap, and making node overlap removal
  faster and better able to retain the graph's shape.
  <P>
  If <TT>overlap_scaling</TT> is negative, the layout is scaled by
  <TT>-1*overlap_scaling</TT> times the average label size.
  If <TT>overlap_scaling</TT> is positive, the layout is scaled by
  <TT>overlap_scaling</TT>.
  If <TT>overlap_scaling</TT> is zero, no scaling is done.

<DT><A NAME=d:overlap_shrink HREF=#a:overlap_shrink><STRONG>overlap_shrink</STRONG></A>
<DD>  If true, the overlap removal algorithm will perform a compression pass to reduce the
  size of the layout.

<DT><A NAME=d:pack HREF=#a:pack><STRONG>pack</STRONG></A>
<DD>  This is true if the value of pack is "true" (case-insensitive) or a
  non-negative integer. If true, each connected component of the graph is
  laid out separately, and then the graphs are packed together.
  If pack has an integral value, this is used as the size,
  in <A HREF=#points>points</A>, of
  a margin around each part; otherwise, a default margin of 8 is used.
  If pack is interpreted as false, the entire graph is laid out together.
  The granularity and method of packing is influenced by the
  <A HREF=#d:packmode>packmode</A> attribute.
  <P>
  For layouts which always do packing, such a twopi, the <B>pack</B>
  attribute is just used to set the margin.

<DT><A NAME=d:packmode HREF=#a:packmode><STRONG>packmode</STRONG></A>
<DD>  This indicates how connected components should be packed
  (cf. <A HREF=#k:packMode>packMode</A>). Note that defining
  <B>packmode</B> will automatically turn on packing as though one had
  set <B>pack=true</B>.

<DT><A NAME=d:pad HREF=#a:pad><STRONG>pad</STRONG></A>
<DD>  The pad attribute specifies how much, in inches, to extend the
  drawing area around the minimal area needed to draw the graph.
  If the pad is a single double, both the x and y pad values are set
  equal to the given value. This area is part of the
  drawing and will be filled with the background color, if appropriate.
  <P>
  Normally, a small pad is used for aesthetic reasons, especially when
  a background color is used, to avoid having nodes and edges abutting
  the boundary of the drawn region.

<DT><A NAME=d:page HREF=#a:page><STRONG>page</STRONG></A>
<DD>  Width and height of output pages, in inches. If only a single value
  is given, this is used for both the width and height.
  <P>
  If this is set and is
  smaller than the size of the layout, a rectangular array of pages of
  the specified page size is overlaid on the layout, with origins
  aligned in the lower-left corner, thereby partitioning the layout
  into pages. The pages are then produced one at a time, in
  <A HREF=#d:pagedir>pagedir</A> order.
  <P>
  At present, this only works for PostScript output. For other types of
  output, one should use another tool to split the output into multiple
  output files. Or use the <A HREF=#d:viewport>viewport</A> to generate
  multiple files.

<DT><A NAME=d:pagedir HREF=#a:pagedir><STRONG>pagedir</STRONG></A>
<DD>  If the <A HREF=#d:page>page</A> attribute is set and applicable,
  this attribute specifies the order in which the pages are emitted.
  This is limited to one of the 8 row or column major orders.

<DT><A NAME=d:pencolor HREF=#a:pencolor><STRONG>pencolor</STRONG></A>
<DD>  Color used to draw the bounding box around a cluster.
  If <B>pencolor</B> is not defined, <A HREF=#d:color><B>color</B></A> is
  used. If this is not defined, <A HREF=#d:bgcolor>bgcolor</A> is used.
  If this is not defined, the default is used.
  <P>
  Note that a cluster inherits the root graph's attributes if defined.
  Thus, if the root graph has defined a <B>pencolor</B>, this will override a
  <B>color</B> or <B>bgcolor</B> attribute set for the cluster.

<DT><A NAME=d:penwidth HREF=#a:penwidth><STRONG>penwidth</STRONG></A>
<DD>  Specifies the width of the pen, in points, used to draw lines and curves,
  including the boundaries of edges and clusters. The value is inherited
  by subclusters.
  It has no effect on text.
  <P>
  Previous to 31 January 2008, the effect of <TT>penwidth=<I>W</I></TT>
  was achieved by including <TT>setlinewidth(<I>W</I>)</TT>
  as part of a <A HREF=#d:style><TT>style</TT></A> specification.
  If both are used, <TT>penwidth</TT> will be used.

<DT><A NAME=d:peripheries HREF=#a:peripheries><STRONG>peripheries</STRONG></A>
<DD>  Set number of peripheries used in polygonal shapes and cluster
  boundaries. Note that
  <A HREF=shapes.html#epsf>user-defined shapes</A> are treated as a
  form of box shape, so the default
  peripheries value is 1 and the user-defined shape will be drawn in
  a bounding rectangle. Setting <TT>peripheries=0</TT> will turn this off.
  Also, 1 is the maximum peripheries value for clusters.

<DT><A NAME=d:pin HREF=#a:pin><STRONG>pin</STRONG></A>
<DD>  If true and the node has a pos attribute on input, neato or fdp prevents the
  node from moving from the input position. This property can also be specified
  in the pos attribute itself (cf. the <A HREF=#k:point>point</A> type).
  <P>
  <B>Note:</B> Due to an artifact of the implementation, 
  previous to 27 Feb 2014, final coordinates
  are translated to the origin. Thus, if you look at the output coordinates
  given in the (x)dot or plain format, pinned nodes will not have the same
  output coordinates as were given on input. If this is important, a
  simple workaround is to maintain the coordinates of a pinned node. The vector
  difference between the old and new coordinates will give the translation,
  which can then be subtracted from all of the appropriate coordinates.
  <P>
  After 27 Feb 2014, this translation can be avoided in neato by setting the 
  <A HREF="#d:notranslate">notranslate</A> to TRUE. However, if the graph
  specifies <A HREF="#d:overlap">node overlap removal</A> or a change in 
  <A HREF="#d:ratio">aspect ratio</A>, node coordinates may still change. 

<DT><A NAME=d:pos HREF=#a:pos><STRONG>pos</STRONG></A>
<DD>  Position of node, or spline control points.
  For nodes, the position indicates the center of the node.
  On output, the coordinates are in <A HREF=#points>points</A>.
  <P>
  In neato and fdp, pos can be used to set the initial position of a node.
  By default, the coordinates are assumed to be in inches. However, the
  <A HREF=command.html#d:s>-s</A> command line flag can be used to specify
  different units. As the output coordinates are in points, 
  feeding the output of a graph laid out by a Graphviz program into
  neato or fdp will almost always require the -s flag.
  <P>
  When the <A HREF=command.html#d:n>-n</A> command line flag is used with
  neato, it is assumed the positions have been set by one of the layout
  programs, and are therefore in points. Thus, <TT>neato -n</TT> can accept
  input correctly without requiring a <TT>-s</TT> flag and, in fact,
  ignores any such flag.

<DT><A NAME=d:quadtree HREF=#a:quadtree><STRONG>quadtree</STRONG></A>
<DD>  Quadtree scheme to use.
  <P>
  A TRUE bool value corresponds to "normal";
  a FALSE bool value corresponds to "none".
  As a slight exception to the normal interpretation of bool,
  a value of "2" corresponds to "fast".

<DT><A NAME=d:quantum HREF=#a:quantum><STRONG>quantum</STRONG></A>
<DD>  If <B>quantum</B> > 0.0, node label dimensions
  will be rounded to integral multiples of the quantum.

<DT><A NAME=d:rank HREF=#a:rank><STRONG>rank</STRONG></A>
<DD>  Rank constraints on the nodes in a subgraph.
  If <B>rank</B>="same", all nodes are placed on the same rank.
  If <B>rank</B>="min", all nodes are placed on the minimum rank.
  If <B>rank</B>="source", all nodes are placed on the minimum rank, and
  the only nodes on the minimum rank belong to some subgraph whose
  rank attribute is "source" or "min".
  Analogous criteria hold for <B>rank</B>="max" and <B>rank</B>="sink".
  (Note: the
  minimum rank is topmost or leftmost, and the maximum rank is bottommost
  or rightmost.)

<DT><A NAME=d:rankdir HREF=#a:rankdir><STRONG>rankdir</STRONG></A>
<DD>  Sets direction of graph layout. For example, if <B>rankdir</B>="LR",
  and barring cycles, an edge <CODE>T -> H;</CODE> will go
  from left to right. By default, graphs are laid out from top to bottom.
  <P>
  This attribute also has a side-effect in determining how record nodes
  are interpreted. See <A HREF="shapes.html#record">record shapes</A>.

<DT><A NAME=d:ranksep HREF=#a:ranksep><STRONG>ranksep</STRONG></A>
<DD>  In dot, this gives the desired rank separation, in inches. This is
  the minimum vertical distance between the bottom of the nodes in one
  rank and the tops of nodes in the next. If the value
  contains "equally", the centers of all ranks are spaced equally apart.
  Note that both
  settings are possible, e.g., ranksep = "1.2 equally".
  <P>
  In twopi, this attribute specifies the radial separation of concentric circles.
  For twopi, <TT>ranksep</TT> can also be a list of doubles. The first double specifies
  the radius of the inner circle; the second double specifies the increase in
  radius from the first circle to the second; etc. If there are more circles than
  numbers, the last number is used as the increment for the remainder.

<DT><A NAME=d:ratio HREF=#a:ratio><STRONG>ratio</STRONG></A>
<DD>  Sets the aspect ratio (drawing height/drawing width) for the drawing.
  Note that this is adjusted before
  the <A HREF=#d:size><B>size</B></A> attribute constraints are enforced.
  In addition, the calculations usually ignore the node sizes, so the
  final drawing size may only approximate what is desired.
  <P>
  If <B>ratio</B> is numeric, it is taken as the desired aspect ratio.
  Then, if the actual aspect ratio is less than the desired ratio,
  the drawing height is scaled up to achieve the
  desired ratio; if the actual ratio is greater than that desired ratio,
  the drawing width is scaled up.
  <P>
  If <B>ratio</B> = "fill" and the <A HREF=#d:size><B>size</B></A>
  attribute is set, node positions are scaled, separately in both x
  and y, so that the final drawing exactly fills the specified size.
  If both <A HREF=#d:size><B>size</B></A> values exceed the width
  and height of the drawing, then both coordinate values of each
  node are scaled up accordingly. However, if either size dimension
  is smaller than the corresponding dimension in the drawing, one
  dimension is scaled up so that the final drawing has the same aspect
  ratio as specified by <A HREF=#d:size><B>size</B></A>. 
  Then, when rendered, the layout will be
  scaled down uniformly in both dimensions to fit the given
  <A HREF=#d:size><B>size</B></A>, which may cause nodes and text
  to shrink as well. This may not be what the user
  wants, but it avoids the hard problem of how to reposition the
  nodes in an acceptable fashion to reduce the drawing size.
  <P>
  If <B>ratio</B> = "compress" and the <A HREF=#d:size><B>size</B></A>
  attribute is set, dot attempts to compress the initial layout to fit
  in the given size. This achieves a tighter packing of nodes but
  reduces the balance and symmetry. This feature only works in dot.
  <P>
  If <B>ratio</B> = "expand", the <A HREF=#d:size><B>size</B></A>
  attribute is set, and both the width and the height of the graph are
  less than the value in  <A HREF=#d:size><B>size</B></A>, node positions are scaled
  uniformly until at least
  one dimension fits <A HREF=#d:size><B>size</B></A> exactly.
  Note that this is distinct from using <A HREF=#d:size><B>size</B></A> as the
  desired size, as here the drawing is expanded before edges are generated and
  all node and text sizes remain unchanged.
  <P>
  If <B>ratio</B> = "auto", the <A HREF=#d:page><B>page</B></A>
  attribute is set and the graph cannot be drawn on a single page,
  then <A HREF=#d:size><B>size</B></A> is set to an ``ideal'' value.
  In particular, the size in a given dimension will be the smallest integral
  multiple of the page size in that dimension which is at least half the
  current size. The two dimensions are then scaled independently to the
  new size. This feature only works in dot.

<DT><A NAME=d:rects HREF=#a:rects><STRONG>rects</STRONG></A>
<DD>  Rectangles for fields of records, <A HREF=#points>in points</A>.

<DT><A NAME=d:regular HREF=#a:regular><STRONG>regular</STRONG></A>
<DD>  If true, force polygon to be regular, i.e., the vertices of the
  polygon will lie on a circle whose center is the center of the node.

<DT><A NAME=d:remincross HREF=#a:remincross><STRONG>remincross</STRONG></A>
<DD>  If true and there are multiple clusters, run crossing
  minimization a second time.

<DT><A NAME=d:repulsiveforce HREF=#a:repulsiveforce><STRONG>repulsiveforce</STRONG></A>
<DD>  The power of the repulsive force used in an extended Fruchterman-Reingold 
  force directed model. Values larger than 1 tend to reduce 
  the warping effect at the expense of less clustering.

<DT><A NAME=d:resolution HREF=#a:resolution><STRONG>resolution</STRONG></A>
<DD>  This is a synonym for the <A HREF=#d:dpi>dpi</A> attribute.

<DT><A NAME=d:root HREF=#a:root><STRONG>root</STRONG></A>
<DD>  This specifies nodes to be used as the center of the
  layout and the root of the generated spanning tree. As a graph attribute,
  this gives the name of the node. As a node attribute, it
  specifies that the node should be used as a central node. In twopi,
  this will actually be the central node. In circo, the block containing
  the node will be central in the drawing of its connected component.
  If not defined,
  twopi will pick a most central node, and circo will pick a random node.
  <P>
  If the root attribute is defined as the empty string, twopi will reset it
  to name of the node picked as the root node.
  <P>
  For twopi, it is possible to have multiple roots, presumably one for each
  component. If more than one node in a component is marked as the root, twopi
  will pick one.

<DT><A NAME=d:rotate HREF=#a:rotate><STRONG>rotate</STRONG></A>
<DD>  If 90, set drawing orientation to landscape.

<DT><A NAME=d:rotation HREF=#a:rotation><STRONG>rotation</STRONG></A>
<DD>  Causes the final layout to be rotated counter-clockwise by the specified number of degrees.

<DT><A NAME=d:samehead HREF=#a:samehead><STRONG>samehead</STRONG></A>
<DD>  Edges with the same head and the same <B>samehead</B> value are aimed
  at the same point on the head. This has no effect on loops.
  Each node can have at most 5 unique samehead values.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:sametail HREF=#a:sametail><STRONG>sametail</STRONG></A>
<DD>  Edges with the same tail and the same <B>sametail</B> value are aimed
  at the same point on the tail. This has no effect on loops.
  Each node can have at most 5 unique sametail values.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:samplepoints HREF=#a:samplepoints><STRONG>samplepoints</STRONG></A>
<DD>  If the input graph defines the <A HREF=#d:vertices><B>vertices</B></A>
  attribute, and output is dot or xdot, this gives
  the number of points used for a node whose shape is a circle or ellipse.
  It plays the same role in neato, when adjusting the layout to avoid
  overlapping nodes, and in image maps.

<DT><A NAME=d:scale HREF=#a:scale><STRONG>scale</STRONG></A>
<DD>  If set, after the initial layout, the layout is scaled by the given factors.
  If only a single number is given, this is used for both factors.

<DT><A NAME=d:searchsize HREF=#a:searchsize><STRONG>searchsize</STRONG></A>
<DD>  During network simplex, maximum number of edges with negative cut values
  to search when looking for one with minimum cut value.

<DT><A NAME=d:sep HREF=#a:sep><STRONG>sep</STRONG></A>
<DD>  Specifies margin to leave around nodes when removing node overlap.
  This guarantees a minimal non-zero distance between nodes.
  <P>
  If the attribute begins with a plus sign '+', an additive margin is
  specified. That is, "+w,h" causes the node's bounding box to be increased 
  by w
  points on the left and right sides, and by h points on the top and bottom.
  Without a plus sign, the node is scaled by 1 + w in the x coordinate
  and 1 + h in the y coordinate.
  <P>
  If only a single number is given, this is used for both dimensions.
  <P>
  If unset but <A HREF=#d:esep>esep</A> is defined, the <tt>sep</tt> values
  will be set to the <tt>esep</tt> values divided by <tt>0.8</tt>. 
  If <tt>esep</tt> is unset, the default value is used.

<DT><A NAME=d:shape HREF=#a:shape><STRONG>shape</STRONG></A>
<DD>  Set the shape of a node.

<DT><A NAME=d:shapefile HREF=#a:shapefile><STRONG>shapefile</STRONG></A>
<DD>  (Deprecated) If defined, shapefile specifies a file containing user-supplied node content.
  The <A HREF=#d:shape><B>shape</B></A> of the node is set to box.
  The image in the shapefile must be
  rectangular. The image formats supported as well as the precise semantics of
  how the file is used depends on the
  <A HREF="output.html">output format</A>.  For further details, see
  <A HREF=output.html#d:image_fmts>Image Formats</A> and
  <A HREF="../../../faq/#ext_image">External PostScript files</A>.
  <P>
  There is one exception to this usage.
  If <B>shape</B> is set to "epsf", shapefile gives
  a filename containing a definition of the node in PostScript.
  The graphics defined must be contain all of the
  node content, including any desired boundaries.
  For further details, see
  <A HREF="../../../faq/#ext_ps_file">
  External PostScript files</A>.

<DT><A NAME=d:showboxes HREF=#a:showboxes><STRONG>showboxes</STRONG></A>
<DD>  Print guide boxes in PostScript at the beginning of
  routesplines if 1, or at the end if 2. (Debugging)

<DT><A NAME=d:sides HREF=#a:sides><STRONG>sides</STRONG></A>
<DD>  Number of sides if <A HREF=#d:shape><B>shape</B></A>=polygon.

<DT><A NAME=d:size HREF=#a:size><STRONG>size</STRONG></A>
<DD>  Maximum width and height of drawing, in inches.
  If only a single number is given, this is used for both the width
  and the height.
  <P>
  If defined and the drawing is larger than the given size, 
  the drawing is uniformly
  scaled down so that it fits within the given size.
  <P>
  If <TT>size</TT> ends in an exclamation point (<TT>!</TT>),
  then it is taken to be
  the desired size. In this case, if both dimensions of the drawing are
  less than <TT>size</TT>, the drawing is scaled up uniformly until at
  least one dimension equals its dimension in <TT>size</TT>.
  <P>
  Note that there is some interaction between the <B>size</B> and
  <A HREF=#d:ratio><B>ratio</B></A> attributes.

<DT><A NAME=d:skew HREF=#a:skew><STRONG>skew</STRONG></A>
<DD>  Skew factor for <A HREF=#d:shape><B>shape</B></A>=polygon. Positive values
  skew top of polygon to right; negative to left.

<DT><A NAME=d:smoothing HREF=#a:smoothing><STRONG>smoothing</STRONG></A>
<DD>  Specifies a post-processing step used to smooth out an uneven distribution 
  of nodes.

<DT><A NAME=d:sortv HREF=#a:sortv><STRONG>sortv</STRONG></A>
<DD>  If <A HREF="#d:packmode">packmode</A> indicates an array packing, 
  this attribute specifies an
  insertion order among the components, with smaller values inserted first.

<DT><A NAME=d:splines HREF=#a:splines><STRONG>splines</STRONG></A>
<DD>  Controls how, and if, edges are represented. If true, edges are drawn as
  splines routed around nodes; if false, edges are drawn as line segments.
  If set to <tt>none</tt> or "", no edges are drawn at all.
  <P>
  (1 March 2007) The values <TT>line</TT> and <TT>spline</TT> can be
  used as synonyms for <TT>false</TT> and <TT>true</TT>, respectively.
  In addition, the value <TT>polyline</TT> specifies that edges should be
  drawn as polylines.
  <P>
  (28 Sep 2010) The value <TT>ortho</TT> specifies edges should be
  routed as polylines of axis-aligned segments. Currently, the routing
  does not handle ports or, in dot, edge labels.
  <P>
  (25 Sep 2012) The value <TT>curved</TT> specifies edges should be
  drawn as curved arcs.
  <P>
  <TABLE>
  <TR>
       <TD><IMG WIDTH="200" VSPACE="10" HSPACE="10" SRC="spline_none.png">
      <TD><IMG WIDTH="200" VSPACE="10" HSPACE="10" SRC="spline_line.png">
  </TR>
  <TR>
      <TD ALIGN="center">splines=none<BR>splines=""
      <TD ALIGN="center">splines=line<BR>splines=false
  </TR>
  <TR>
      <TD><IMG WIDTH="200" VSPACE="10" HSPACE="10" SRC="spline_polyline.png">
      <TD><IMG WIDTH="200" VSPACE="10" HSPACE="10" SRC="spline_curved.png">
  </TR>
  <TR>
      <TD ALIGN="center">splines=polyline
      <TD ALIGN="center">splines=curved
  </TR>
  <TR>
      <TD><IMG WIDTH="200" VSPACE="10" HSPACE="10" SRC="spline_ortho.png">
      <TD><IMG WIDTH="200" VSPACE="10" HSPACE="10" SRC="spline_spline.png">
  </TR>
  <TR>
      <TD ALIGN="center">splines=ortho
      <TD ALIGN="center">splines=spline<BR>splines=true
  </TR>
  </TABLE>
  
  <P>
  By default, the attribute is unset. How this is interpreted depends on
  the layout. For dot, the default is to draw edges as splines. For all
  other layouts, the default is to draw edges as line segments. Note that
  for these latter layouts, if <TT>splines="true"</TT>, this
  requires non-overlapping nodes (cf. <A HREF=#d:overlap><B>overlap</B></A>).
  If fdp is used for layout and <TT>splines="compound"</TT>, then the edges are
  drawn to avoid clusters as well as nodes.

<DT><A NAME=d:start HREF=#a:start><STRONG>start</STRONG></A>
<DD>  Parameter used to determine the initial layout of nodes. If unset, the
  nodes are randomly placed in a unit square with
  the same seed is always used for the random number generator, so the
  initial placement is repeatable.

<DT><A NAME=d:style HREF=#a:style><STRONG>style</STRONG></A>
<DD>  Set style information for components of the graph. For cluster subgraphs, if <TT>style="filled"</TT>, the
  cluster box's background is filled.
  <P>
  If the default style attribute has been set for a component, an individual component can use
  <TT>style=""</TT> to revert to the normal default. For example, if the graph has
  <P>
  <TT>edge [style="invis"]</TT>
  <P>
  making all edges invisible, a specific edge can overrride this via:
  <P>
  <TT>a -> b [style=""]</TT>
  <P>
  Of course, the component can also explicitly set its <TT>style</TT> attribute to the desired value.

<DT><A NAME=d:stylesheet HREF=#a:stylesheet><STRONG>stylesheet</STRONG></A>
<DD>  A URL or pathname specifying an XML style sheet, used in SVG output.

<DT><A NAME=d:tailURL HREF=#a:tailURL><STRONG>tailURL</STRONG></A>
<DD>  If <B>tailURL</B> is defined, it is
  output as part of the tail label of the edge.
  Also, this value is used near the tail node, overriding any
  <A HREF=#d:URL>URL</A> value.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:tail_lp HREF=#a:tail_lp><STRONG>tail_lp</STRONG></A>
<DD>  Position of an edge's tail label, <A HREF=#points>in points</A>.
  The position indicates the center of the label.

<DT><A NAME=d:tailclip HREF=#a:tailclip><STRONG>tailclip</STRONG></A>
<DD>  If true, the tail of an edge is clipped to the boundary of the tail node;
  otherwise, the end of the edge goes to the center of the node, or the
  center of a port, if applicable.

<DT><A NAME=d:tailhref HREF=#a:tailhref><STRONG>tailhref</STRONG></A>
<DD>  Synonym for <A HREF=#d:tailURL>tailURL</A>.

<DT><A NAME=d:taillabel HREF=#a:taillabel><STRONG>taillabel</STRONG></A>
<DD>  Text label to be placed near tail of edge.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:tailport HREF=#a:tailport><STRONG>tailport</STRONG></A>
<DD>  Indicates where on the tail node to attach the tail of the edge.
  See <A HREF=#h:undir_note>limitation</A>.

<DT><A NAME=d:tailtarget HREF=#a:tailtarget><STRONG>tailtarget</STRONG></A>
<DD>  If the edge has a <A HREF=#d:tailURL>tailURL</A>,
  this attribute determines which window of the
  browser is used
  for the URL. Setting it to "_graphviz" will open a new window if it
  doesn't already exist, or reuse it if it does.
  If undefined, the value of the <A HREF=#d:target>target</A> is used.

<DT><A NAME=d:tailtooltip HREF=#a:tailtooltip><STRONG>tailtooltip</STRONG></A>
<DD>  Tooltip annotation attached to the tail of an edge. This is used only
  if the edge has a <A HREF=#d:tailURL>tailURL</A> attribute.

<DT><A NAME=d:target HREF=#a:target><STRONG>target</STRONG></A>
<DD>  If the object has a URL, this attribute determines which window
  of the browser is used for the URL.
  See <A HREF="http://www.w3.org/TR/html401/present/frames.html#adef-target">W3C documentation</A>.

<DT><A NAME=d:tooltip HREF=#a:tooltip><STRONG>tooltip</STRONG></A>
<DD>  Tooltip annotation attached to the node or edge. If unset, Graphviz
  will use the object's <A HREF=#d:label>label</A> if defined.
  Note that if the label is a record specification or an HTML-like
  label, the resulting tooltip may be unhelpful. In this case, if
  tooltips will be generated, the user should set a <TT>tooltip</TT>
  attribute explicitly.

<DT><A NAME=d:truecolor HREF=#a:truecolor><STRONG>truecolor</STRONG></A>
<DD>  If set explicitly to true or false, the value determines whether or not
  internal bitmap rendering relies on a truecolor color model or uses
  a color palette.
  If the attribute is unset, truecolor is not used
  unless there is a <A HREF=#d:shapefile>shapefile</A> property
  for some node in the graph.
  The output model will use the input model when possible.
  <P>
  Use of color palettes results in less memory usage during creation of the
  bitmaps and smaller output files.
  <P>
  Usually, the only time it is necessary to specify the truecolor model
  is if the graph uses more than 256 colors.
  However, if one uses <A HREF=#d:bgcolor>bgcolor</A>=transparent with
  a color palette, font
  antialiasing can show up as a fuzzy white area around characters.
  Using <B>truecolor</B>=true avoids this problem.

<DT><A NAME=d:vertices HREF=#a:vertices><STRONG>vertices</STRONG></A>
<DD>  If the input graph defines this attribute, the node is polygonal,
  and output is dot or xdot, this attribute provides the
  coordinates of the vertices of the node's polygon, in inches.
  If the node is an ellipse or circle, the
  <A HREF=#d:samplepoints>samplepoints</A> attribute affects
  the output.

<DT><A NAME=d:viewport HREF=#a:viewport><STRONG>viewport</STRONG></A>
<DD>  Clipping window on final drawing. Note that this attribute supersedes any
  <A HREF="#d:size">size</A> attribute. The width and height of the viewport specify
  precisely the final size of the output. 

<DT><A NAME=d:voro_margin HREF=#a:voro_margin><STRONG>voro_margin</STRONG></A>
<DD>  Factor to scale up drawing to allow margin for expansion in
  Voronoi technique. dim' = (1+2*margin)*dim.

<DT><A NAME=d:weight HREF=#a:weight><STRONG>weight</STRONG></A>
<DD>  Weight of edge. In dot, the heavier the weight, the shorter,
  straighter and more vertical the edge is.
  <B>N.B.</B> Weights in dot must be integers.
  For twopi, a weight of 0 indicates the edge should not be used in constructing a
  spanning tree from the root.
  For other layouts, a larger weight encourages the layout to 
  make the edge length closer to that specified by the 
  <A HREF=#d:len>len</A> attribute.

<DT><A NAME=d:width HREF=#a:width><STRONG>width</STRONG></A>
<DD>  Width of node, in inches. This is taken as the initial, minimum width
  of the node. If <A HREF=#d:fixedsize><B>fixedsize</B></A> is true, this
  will be the final width of the node. Otherwise, if the node label
  requires more width to fit, the node's width will be increased to
  contain the label. Note also that, if the output format is dot, the
  value given to <B>width</B> will be the final value.
  <P>
  If the node shape is regular, the width and height are made identical.
  In this case, if either the width or the height is set explicitly,
  that value is used.
  In this case, if both the width or the height are set explicitly,
  the maximum of the two values is used.
  If neither is set explicitly, the minimum of the two default values
  is used.

<DT><A NAME=d:xdotversion HREF=#a:xdotversion><STRONG>xdotversion</STRONG></A>
<DD>  For xdot output, if this attribute is set, this determines the version of xdot used in output.
  If not set, the attribute will be set to the xdot version used for output.

<DT><A NAME=d:xlabel HREF=#a:xlabel><STRONG>xlabel</STRONG></A>
<DD>  External label for a node or edge. For nodes, the label will be placed outside of the
  node but near it. For edges, the label will be placed near the center of the edge.
  This can be useful in dot to avoid the occasional problem when the use of edge labels
  distorts the layout. For other layouts, the xlabel attribute can be viewed as a synonym
  for the <A HREF=#d:label><B>label</B></A> attribute.
  <P>
  These labels are added after all nodes and edges have been placed. The labels will be placed
  so that they do not overlap any node or label. This means it may not be possible to place all
  of them. To force placing all of them, use the  <A HREF=#d:forcelabels><B>forcelabels</B></A> attribute.

<DT><A NAME=d:xlp HREF=#a:xlp><STRONG>xlp</STRONG></A>
<DD>  Position of an exterior label, <A HREF=#points>in points</A>.
  The position indicates the center of the label.

<DT><A NAME=d:z HREF=#a:z><STRONG>z</STRONG></A>
<DD>  <B>Deprecated:</B>Use <A HREF=#d:pos><B>pos</B></A> attribute, along
  with <A HREF=#d:dimen><B>dimen</B></A> and/or <A HREF=#d:dim><B>dim</B></A>
  to specify dimensions.
  <P>
  Provides z coordinate value for 3D layouts and displays. If the
  graph has <A HREF=#d:dim><B>dim</B></A> set to 3 (or more),
  neato will use a node's <B>z</B> value
  for the z coordinate of its initial position if
  its <A HREF=#d:pos><B>pos</B></A> attribute is also defined.
  <P>
  Even if no <B>z</B> values are specified in the input, it is necessary to
  declare a <B>z</B> attribute for nodes, e.g, using <TT>node[z=""]</TT>
  in order to get z values on output.
  Thus, setting <TT>dim=3</TT> but not declaring <B>z</B> will
  cause <TT>neato -Tvrml</TT> to
  layout the graph in 3D but project the layout onto the xy-plane
  for the rendering. If the <B>z</B> attribute is declared, the final rendering
  will be in 3D.

</DL>
<HR>
<H1>Attribute Type Descriptions</H1>
The following list gives the legal strings corresponding to values of
the given types.
The syntax for describing legal type strings is a mixture of literal strings,
stdio encodings (e.g., <TT>%f</TT> for a double), and regular expressions.
For regular expressions, <TT>(...)*</TT> indicates 0 or more copies of the expression
enclosed in the parentheses,  <TT>(...)+</TT> indicates 1 or more, and
<TT>(...)?</TT> denotes 0 or 1 copy.
<DL>
<DT><A NAME=k:addDouble><STRONG>addDouble</STRONG></A>
<DD><P>A double with an optional prefix '+'.

<DT><A NAME=k:addPoint><STRONG>addPoint</STRONG></A>
<DD><P>A <A HREF="#k:point">point</A> with an optional prefix '+'.

<DT><A NAME=k:arrowType><STRONG>arrowType</STRONG></A>
<DD><TABLE>
    <TR><TD>"normal"<TD><IMG SRC="a_normal.gif">
        <TD>"inv"<TD><IMG SRC="a_inv.gif"></TR>
    <TR><TD>"dot"<TD><IMG SRC="a_dot.gif">
        <TD>"invdot"<TD><IMG SRC="a_invdot.gif"></TR>
    <TR><TD>"odot"<TD><IMG SRC="a_odot.gif">
        <TD>"invodot"<TD><IMG SRC="a_invodot.gif"></TR>
    <TR><TD>"none"<TD><IMG SRC="a_none.gif">
        <TD>"tee"<TD><IMG SRC="a_tee.gif"></TR>
    <TR><TD>"empty"<TD><IMG SRC="a_empty.gif">
        <TD>"invempty"<TD><IMG SRC="a_invempty.gif"></TR>
    <TR><TD>"diamond"<TD><IMG SRC="a_diamond.gif">
        <TD>"odiamond"<TD><IMG SRC="a_odiamond.gif"></TR>
    <TR><TD>"ediamond"<TD><IMG SRC="a_ediamond.gif">
        <TD>"crow"<TD><IMG SRC="a_crow.gif"></TR>
    <TR><TD>"box"<TD><IMG SRC="a_box.gif">
        <TD>"obox"<TD><IMG SRC="a_obox.gif"></TR>
    <TR><TD>"open"<TD><IMG SRC="a_open.gif">
        <TD>"halfopen"<TD><IMG SRC="a_halfopen.gif"></TR>
    <TR><TD>"vee"<TD><IMG SRC="a_open.gif">
        <TD>"circle"<TD><IMG SRC="a_circle.gif"></TR>
  </TABLE>
  <P>
  These are the basic set of backward-compatible arrow shapes. In addition,
  there is a grammar of <A HREF=arrows.html>arrow shapes</A>
  which can be used to describe a collection of 2,313,441 arrow combinations of the 
  39 variations of the primitive set of 10 arrows. The basic arrows shown
  above contain all of the primitive shapes
  (<TT>box</TT>, <TT>crow</TT>, <TT>circle</TT>, <TT>diamond</TT>,
  <TT>dot</TT>, <TT>inv</TT>, <TT>none</tt>,
  <TT>normal</tt>, <TT>tee</TT>, <TT>vee</TT>)
  plus ones that can be derived from the grammar
  (<TT>odot</TT>, <TT>invdot</TT>, <TT>invodot</TT>,
  <TT>obox</TT>, <TT>odiamond</TT>)
  plus some supported as special cases for backward-compatibility
  (<TT>ediamond</TT>, <TT>open</TT>, <TT>halfopen</TT>,
  <TT>empty</TT>, <TT>invempty</TT>).

<DT><A NAME=k:clusterMode><STRONG>clusterMode</STRONG></A>
<DD>"local","global","none"

<DT><A NAME=k:color><STRONG>color</STRONG></A>
<DD>Colors can be specified using one of four formats.
         <TABLE><TR><TD>"#%2x%2x%2x"<TD>Red-Green-Blue (RGB)</TR>
         <TR><TD>"#%2x%2x%2x%2x"<TD>Red-Green-Blue-Alpha (RGBA)</TR>
         <TR><TD>"H[,&#160;]+S[,&#160;]+V"<TD>Hue-Saturation-Value (HSV) 0.0 <= H,S,V <= 1.0</TR>
         <TR><TD>string<TD><A HREF=colors.html>color name</A></TR></TABLE>
   The specification for the RGB and RGBA formats are the format strings used by
   <TT>sscanf</TT> to scan the color value. Thus, these values have the form
   "#RGB" or "#RGBA", where R, G, B, and A each consist of 2 hexadecimal
   digits, and can be separated by whitespace. HSV colors have the form of 3
   numbers between 0 and 1, separated by whitespace or commas.
  <P>
  String-valued color specifications are case-insensitive and interpreted
  in the context of the current color scheme, as specified by the
  <A HREF=#d:colorscheme>colorscheme</A> attribute. If this is undefined,
  the X11 naming scheme will be used.
  An initial <TT>"/"</TT> character can be used to override the use of
  the <TT>colorscheme</TT> attribute. In particular, a single initial
  <TT>"/"</TT> will cause the string to be evaluated using the default
  X11 naming. If the color value has the form <TT>"/ssss/yyyy"</TT>,
  the name <TT>yyyy</TT> is interpreted using the schema <TT>ssss</TT>.
  If the color scheme name is empty, i.e., the color has the
  form <TT>"//yyyy"</TT>, the <TT>colorscheme</TT> attribute is used.
  Thus, the forms <TT>"yyyy"</TT> and <TT>"//yyyy"</TT> are
  equivalent.
  <P>At present, Graphviz recognizes the default color scheme <TT>X11</TT>,
  and the <A HREF="colors.html#brewer">Brewer color schemes</A> (cf. <A HREF="http://www.personal.psu.edu/faculty/c/a/cab38/ColorBrewer/ColorBrewer_intro.html">ColorBrewer</A>). Please note that Brewer
  color schemes are covered by this <A HREF=colors.html#brewer_license>license</A>.
  <P>
  Examples:<BR>
    <TABLE border=1>
      <TR><TH>Color<TH>RGB<TH>HSV<TH>String</TR>
      <TR><TD align=center bgcolor=#ffffff>White<TD>"#ffffff"<TD>"0.000 0.000 1.000"<TD>"white"</TR>
      <TR><TD align=center bgcolor=#000000><font color=white>Black</font><TD>"#000000"<TD>"0.000 0.000 0.000"<TD>"black"</TR>
      <TR><TD align=center bgcolor=#ff0000>Red<TD>"#ff0000"<TD>"0.000 1.000 1.000"<TD>"red"</TR>
      <TR><TD align=center bgcolor=#40e0d0>Turquoise<TD>"#40e0d0"<TD>"0.482 0.714 0.878"<TD>"turquoise"</TR>
      <TR><TD align=center bgcolor=#a0522d>Sienna<TD>"#a0522d"<TD>"0.051 0.718 0.627"<TD>"sienna"</TR>
    </TABLE>
  <P>
   The string value <TT>transparent</TT> can be used to indicate no color.
   This is only available in the output formats
   ps, svg, fig, vmrl, and the bitmap formats. It can be used whenever a
   color is needed but is most useful with
   the <A HREF=#d:bgcolor>bgcolor</A> attribute.
   Usually, the same effect can be achieved by setting
   <A HREF=#d:style>style</A> to <TT>invis</TT>.

<DT><A NAME=k:colorList><STRONG>colorList</STRONG></A>
<DD>A colon-separated list of weighted color values: <I>WC</I>(:<I>WC</I>)*
  where each <I>WC</I> has the form <I>C(;F)?</I> with C a <A HREF=#k:color>color</A> value
  and the optional <I>F</I> a floating-point number, 0 &le; <I>F</I> &le; 1. The sum of the 
  floating-point numbers in a <TT>colorList</TT> must sum to at most 1.
  <P>
  <b>NOTE:</b> Gradient fills, described below, are currently only available via CAIRO or SVG rendering.
  <P>
  If the colorList value specifies multiple colors, with no weights, and a filled style is specified,
  a linear gradient fill is done using the first two colors.
  If weights are present, a degenerate linear gradient fill is done. This essentially does a fill using
  two colors, with the weights specifying how much of region is filled with each color. 
  If the <A HREF=#a:style>style</A> attribute contains the value <tt>radial</tt>, then
  a radial gradient fill is done. These fills work with any shape. 
  <P>
  For certain shapes, the <A HREF=#a:style>style</A> attribute can be set
  to do fills using more than 2 colors. See the <A HREF=#k:style>style</A> type for more information.
  <P>
  The following table shows some variations of the <TT>yellow:blue</TT> color list depending on the
  <A HREF=#a:style>style</A> and <A HREF=#a:gradientangle>gradientangle</A> attributes.
    <TABLE border=1>
      <TR><TH>Gradient angle<TH><tt>style=filled</tt><TH><tt>style=filled<br>fillcolor=yellow;0.3:blue</tt><TH><tt>style=radial</tt></TR>
      <TR><TD align=center>0<TD><IMG SRC="g_lin0.png"><TD ALIGN="CENTER"><IMG SRC="g_wlin0.png"><TD><IMG SRC="g_rad0.png"></TR>
      <TR><TD align=center>45<TD><IMG SRC="g_lin45.png"><TD ALIGN="CENTER"><IMG SRC="g_wlin45.png"><TD><IMG SRC="g_rad45.png"></TR>
      <TR><TD align=center>90<TD><IMG SRC="g_lin90.png"><TD ALIGN="CENTER"><IMG SRC="g_wlin90.png"><TD><IMG SRC="g_rad90.png"></TR>
      <TR><TD align=center>180<TD><IMG SRC="g_lin180.png"><TD ALIGN="CENTER"><IMG SRC="g_wlin180.png"><TD><IMG SRC="g_rad180.png"></TR>
      <TR><TD align=center>270<TD><IMG SRC="g_lin270.png"><TD ALIGN="CENTER"><IMG SRC="g_wlin270.png"><TD><IMG SRC="g_rad270.png"></TR>
      <TR><TD align=center>360<TD><IMG SRC="g_lin360.png"><TD ALIGN="CENTER"><IMG SRC="g_wlin360.png"><TD><IMG SRC="g_rad360.png"></TR>
    </TABLE>

<DT><A NAME=k:dirType><STRONG>dirType</STRONG></A>
<DD>For an edge <CODE>T -> H;</CODE>
    <TABLE>
    <TR><TD>"forward"<TD><IMG SRC="forward.gif">
        <TD>"back"<TD><IMG SRC="back.gif"></TR>
    <TR><TD>"both"<TD><IMG SRC="both.gif">
        <TD>"none"<TD><IMG SRC="nohead.gif"></TR>
    </TABLE>
  That is, a glyph is drawn at the head end of an edge if and only
  if dirType is "forward" or "both";
  a glyph is drawn at the tail end of an edge if and only
  if dirType is "back" or "both";
  <P>
  For undirected edges <CODE>T -- H;</CODE>, one of the nodes, usually
  the righthand one, is treated as the head for the purpose of
  interpreting "forward" and "back".

<DT><A NAME=k:doubleList><STRONG>doubleList</STRONG></A>
<DD>A colon-separated list of doubles: "<I>%f</I>(:<I>%f</I>)*"
   where each <I>%f</I> is a double.

<DT><A NAME=k:escString><STRONG>escString</STRONG></A>
<DD>A string allowing escape sequences which are replaced according
  to the context.
  For node attributes, the substring "&#92;N" is replaced by the name of the node,
  and the substring "&#92;G" by the name of the graph.
  For graph or cluster attributes, the substring "&#92;G" is replaced by the
  name of the graph or cluster.
  For edge attributes, the substring "&#92;E" is replaced by the name of the edge,
  the substring "&#92;G" is replaced by the name of the graph or cluster,
  and the substrings "&#92;T" and "&#92;H" by the names of
  the tail and head nodes, respectively.
  The name of an edge is the string formed from the name of the
  tail node, the appropriate edge operator ("--" or "->") and the name of the
  head node.
  In all cases, the substring "&#92;L" is replaced by the object's label attribute.
  <P>
  In addition, if the associated attribute is
  <A HREF=#a:label>label</A>,
  <A HREF=#a:headlabel>headlabel</A> or <A HREF=#a:taillabel>taillabel</A>,
  the escape sequences "&#92;n", "&#92;l" and "&#92;r"
  divide the label into lines, centered, left-justified, and right-justified,
  respectively.
  <P>
  Obviously, one can use "&#92;&#92;" to get a single backslash. A backslash appearing before any
  character not listed above is ignored.

<DT><A NAME=k:layerList><STRONG>layerList</STRONG></A>
<DD>list of strings separated by characters from the
  <A HREF=#a:layersep>layersep</A> attribute (by default, colons,
  tabs or spaces), defining <A HREF=#a:layer>layer</A>
  names and implicitly numbered 1,2,...

<DT><A NAME=k:layerRange><STRONG>layerRange</STRONG></A>
<DD>specifies a list of layers defined by the <A HREF=#a:layers>layers</A> attribute.
  It consists of a list of layer intervals separated by any collection of characters from
  the <A HREF=#a:layerlistsep>layerlistsep</A> attribute.
  Each layer interval is specified as either a
  layerId or a layerId<B>s</B>layerId<BR>, where layerId = "all",
  a decimal integer or a <A HREF=#a:layer>layer</A> name.
  (An integer i corresponds to layer i, layers being numbered from 1.)
  The string <B>s</B> consists of 1 or more separator characters specified
  by the <A HREF=#a:layersep>layersep</A> attribute.
  <P>
  Thus, assuming the default values for <A HREF=#a:layersep>layersep</A>
  and <A HREF=#a:layerlistsep>layerlistsep</A>, if <TT>layers="a:b:c:d:e:f:g:h"</TT>, the
  layerRange string <TT>layers="a:b,d,f:all"</TT> would denote the layers
  <TT>a b d f g h"</TT>.

<DT><A NAME=k:lblString><STRONG>lblString</STRONG></A>
<DD>an <A HREF=#k:escString>escString</A>
  or an <A HREF=shapes.html#html>HTML label</A>.

<DT><A NAME=k:outputMode><STRONG>outputMode</STRONG></A>
<DD>"breadthfirst","nodesfirst","edgesfirst"
  These specify the order in which nodes and edges are drawn in concrete
  output. The default "breadthfirst" is the simplest, but when the graph
  layout does not avoid edge-node overlap, this mode will sometimes have
  edges drawn over nodes and sometimes on top of nodes. If the mode
  "nodesfirst" is chosen, all nodes are drawn first, followed by the
  edges. This guarantees an edge-node overlap will not be mistaken for
  an edge ending at a node. On the other hand, usually for aesthetic
  reasons, it may be desirable that all edges appear beneath nodes, even
  if the resulting drawing is ambiguous. This can be achieved by choosing
  "edgesfirst".

<DT><A NAME=k:packMode><STRONG>packMode</STRONG></A>
<DD>"node", "clust" , "graph" , "array(_<I>flags</I>)?(%d)?"
  <P>
  The modes "node", "clust" or "graph"
  specify that the components should be packed together tightly, using
  the specified granularity.
  A value of "node" causes
  packing at the node and edge level, with no overlapping of these objects.
  This produces a layout with the least area, but it also allows interleaving,
  where a node of one component may lie between two nodes in another
  component. A value of "graph" does a packing using the bounding box of the
  component. Thus, there will be a rectangular region around a component
  free of elements of any other component.
  A value of "clust" guarantees that top-level clusters are kept intact.
  What effect a value has also depends on the layout algorithm. For
  example, neato does not support clusters, so a value of "clust" will
  have the same effect as the default "node" value.
  <P>
  The mode "array(_<I>flag</I>)?(%d)?"
  indicates that the components should be packed at the 
  graph level into an array of graphs. By default, the components
  are in row-major order, with the number of columns roughly the
  square root of the number of components. If the optional flags
  contains 'c', then column-major order is used. Finally, if the
  optional integer suffix is used, this specifies the number of 
  columns for row-major or the number of rows for column-major.
  Thus, the mode "array_c4" indicates array packing, with 4 rows,
  starting in the upper left and going down the first column, then
  down the second column, etc., until all components are used.
  <P>
  If a graph is smaller than the array cell it occupies, it is centered by default.
  The optional flags may contain 't', 'b', 'l', or 'r', indicating that the graphs
  should be aligned along the top, bottom, left or right, respectively.
  <P>
  If the optional flags contains 'u', this causes the insertion
  order of elements in the array to be determined by user-supplied
  values. Each component can specify its sort value by a 
  non-negative integer using the <A HREF="#d:sortv">sortv</A> attribute. 
  Components are
  inserted in order, starting with the one with the smallest
  sort value. If no sort value is specified, zero is used.

<DT><A NAME=k:pagedir><STRONG>pagedir</STRONG></A>
<DD>"BL", "BR", "TL", "TR", "RB", "RT", "LB", "LT".
  These specify the 8 row or column major orders for traversing a
  rectangular array, the first character corresponding to the major
  order and the second to the minor order. Thus, for "BL", the
  major order is from bottom to top, and the minor order is from left
  to right. This means the bottom row is traversed first, from left
  to right, then the next row up, from left to right, and so on,
  until the topmost row is traversed.

<DT><A NAME=k:point><STRONG>point</STRONG></A>
<DD>"%f,%f('!')?" representing the point (x,y). The
  optional '!' indicates the
  node position should not change (input-only).
  <P>
  If <A HREF=#d:dim>dim</A> is 3, <B>point</B> may also have
  the format "%f,%f,%f('!')?" to represent the point (x,y,z).

<DT><A NAME=k:pointList><STRONG>pointList</STRONG></A>
<DD>A list of points, separated by spaces.

<DT><A NAME=k:portPos><STRONG>portPos</STRONG></A>
<DD>modifier indicating where on a node an edge should be aimed.
  It has the form <TT><I>portname</I>(:<I>compass_point</I>)?</TT>
  or <TT><I>compass_point</I></TT>.
  If the first form is used, the corresponding node must either have
  <A HREF=shapes.html#record>record</A> shape with one of its fields
  having the given <I>portname</I>,
  or have an <A HREF=shapes.html#html>HTML-like label</A>, one of
  whose components has a <TT>PORT</TT> attribute set to <I>portname</I>.
  <P>
  If a compass point is used, it must have the form
  <TT>"n","ne","e","se","s","sw","w","nw","c","_"</TT>. This modifies the edge
  placement to aim for the corresponding compass point on the port or,
  in the second form where no <I>portname</I> is supplied, on the node
  itself. The compass point "c" specifies the center of the node or port.
  The compass point "_" specifies that an appropriate side of the port
  adjacent to the exterior of the node should be used, if such exists.
  Otherwise, the center is used.
  If no compass point is used with a portname, the default value is "_".
  <P>
  <P>
  This attribute can be attached to an edge using the
  <A HREF=#d:headport>headport</A> and
  <A HREF=#d:tailport>tailport</A> attributes, or as part of the
  edge description as in
  <CENTER>
  <TT>node1:port1 -> node2:port5:nw;</TT>
  </CENTER>
  <P>
  Note that it is legal to have a portname the same as one of
  the compass points. In this case, this reference will be resolved to
  the port. Thus, if node <TT>A</TT> has a port <TT>w</TT>, then
  <TT>headport=w</TT> will refer to the port and not the compass point.
  At present, in this case, there is no way to specify that the compass
  point should be used.

<DT><A NAME=k:quadType><STRONG>quadType</STRONG></A>
<DD>"normal", "fast", "none". 
  <P>
  Using "fast" gives about a 2-4 times overall speedup compared with "normal", 
  though layout quality can suffer a little. 

<DT><A NAME=k:rankType><STRONG>rankType</STRONG></A>
<DD>"same", "min", "source", "max", "sink"

<DT><A NAME=k:rankdir><STRONG>rankdir</STRONG></A>
<DD>"TB", "LR", "BT", "RL", corresponding to directed graphs drawn
  from top to bottom, from left to right, from bottom to top, and from
  right to left, respectively.

<DT><A NAME=k:rect><STRONG>rect</STRONG></A>
<DD>"%f,%f,%f,%f"  The rectangle llx,lly,urx,ury gives the coordinates, in
   points, of the lower-left corner (llx,lly) and the upper-right corner
   (urx,ury).

<DT><A NAME=k:shape><STRONG>shape</STRONG></A>
<DD>A string specifying the <A HREF=shapes.html>shape</A> of a node.
  There are three
  main types of shapes :
  <A HREF=shapes.html#polygon>polygon-based</A>,
  <A HREF=shapes.html#record>record-based</A> and
  <A HREF=shapes.html#epsf>user-defined</A>.
  The record-based shape has largely been superseded and greatly generalized
  by <A HREF=shapes.html#html>HTML-like labels</A>. 
  That is, instead of using <TT>shape=record</TT>, one might
  consider using <TT>shape=none</TT> and an HTML-like label.

<DT><A NAME=k:smoothType><STRONG>smoothType</STRONG></A>
<DD>Values are "none", "avg_dist", "graph_dist", "power_dist", "rng", 
  "spring" and "triangle".

<DT><A NAME=k:splineType><STRONG>splineType</STRONG></A>
<DD>spline ( ';' spline )*<BR>
  <TABLE>
   <TR><TD ALIGN=right>where spline<TD>=<TD>(endp)? (startp)? point (triple)+</TR>
   <TR><TD ALIGN=right>and triple<TD>=<TD>point point point</TR>
   <TR><TD ALIGN=right>and endp<TD>=<TD>"e,%f,%f"</TR>
   <TR><TD ALIGN=right>and startp<TD>=<TD>"s,%f,%f"</TR>
  </TABLE>
  If a spline has points p<SUB>1</SUB> p<SUB>2</SUB> p<SUB>3</SUB> ... p<SUB>n</SUB>, (n = 1 (mod 3)), the points
   correspond to the control points of a cubic B-spline from p<SUB>1</SUB> to p<SUB>n</SUB>. If startp
   is given, it touches one node of the edge, and the arrowhead
   goes from p<SUB>1</SUB> to startp. If startp is not given, p<SUB>1</SUB> touches a node.
   Similarly for p<SUB>n</SUB>  and endp.

<DT><A NAME=k:startType><STRONG>startType</STRONG></A>
<DD>has the syntax <TT>(<I>style</I>)?(<I>seed</I>)?</TT>.
  <P>
  If <I>style</I> is present, it must be one of the strings <TT>"regular"</TT>,
  <TT>"self"</TT>, or <TT>"random"</TT>. In the first case, the nodes are
  placed regularly about a circle. In the second case,
  an abbreviated version of neato is run to obtain the initial layout.
  In the last case, the nodes are placed randomly in a unit square.
  <P>
  If <I>seed</I> is present, it specifies a seed for the random number
  generator. If <I>seed</I> is a positive number, this is used as the
  seed. If it is anything else,
  the current time, and possibly the process id, is used to pick a seed,
  thereby making the choice more random. In this case, the seed value
  is stored in the graph.
  <P>
  If the value is just <TT>"random"</TT>, a time-based seed is chosen.
  <P>
  Note that input positions, specified by a node's
  <A HREF=#d:pos>pos</A>
  attribute, are only used when the style is <TT>"random"</TT>.

<DT><A NAME=k:style><STRONG>style</STRONG></A>
<DD>styleItem ( ',' styleItem )*<BR>
  <TABLE>
  <TR><TD ALIGN=right>where styleItem<TD>=<TD>name or name'('args')'</TR>
  <TR><TD ALIGN=right>and args<TD>=<TD>name ( ',' name )*</TR>
  </TABLE>
  and name can be any string of characters not containing a space, a left or
  right parenthesis, or a comma.
  Note that whitespace characters are ignored.
  <P>
  <B>NOTE:</B><EM>The styles <tt>tapered, striped</tt> and <tt>wedged</tt>
  are only available in release 2.30 and later.</EM>
  <P>
  At present, the recognized style names are
  "dashed", "dotted", "solid", "invis" and "bold" for nodes and edges,
  "tapered" for edges only,
  and "filled", "striped", "wedged", "diagonals" and "rounded" for nodes only.
  The styles "filled", "striped" and "rounded" are recognized for clusters.
  The style "radial" is recognized for nodes, clusters and graphs, and indicates a
  radial-style gradient fill if applicable.
  <P>
  The style "striped" causes the
  fill to be done as a set of vertical stripes. The colors are specified via a <A HREF=#k:colorList>colorList</A>, 
  the colors drawn from left to right in list order. Optional color weights can be specified to indicate the
  proportional widths of the bars. If the sum of the weights is less than 1, the remainder is divided evenly
  among the colors with no weight. <B>Note</B>: The style "striped" is only supported with clusters and
  rectangularly-shaped nodes.
  <P>
  The style "wedged" causes the
  fill to be done as a set of wedges. The colors are specified via a <A HREF=#k:colorList>colorList</A>, 
  with the colors drawn counter-clockwise starting at angle 0. Optional color weights are interpreted
  analogously to the striped case described above.
  <B>Note</B>: The style "wedged" is allowed only for elliptically-shaped nodes.
  <P>
  The following tables illustrate some of the effects of the style settings. 
  Examples of tapered line styles are given below.
  Examples of linear and radial gradient fill can be seen under  <A HREF=#k:colorList>colorList</A>.
  <P>
    <TABLE border=1>
      <TR><TD align="center"><tt>solid</tt> <TD><IMG SRC="n_solid.png">
         <TD align="center"><tt>dashed</tt> <TD><IMG SRC="n_dashed.png">
         <TD align="center"><tt>dotted</tt> <TD><IMG SRC="n_dotted.png"> </TR>
      <TR><TD align="center"><tt>bold</tt> <TD><IMG SRC="n_bold.png">
         <TD align="center"><tt>rounded</tt> <TD><IMG SRC="n_rounded.png">
         <TD align="center"><tt>diagonals</tt> <TD><IMG SRC="n_diagonals.png"> </TR>
      <TR><TD align="center"><tt>filled</tt> <TD><IMG SRC="n_filled.png">
         <TD align="center"><tt>striped</tt> <TD><IMG SRC="n_striped.png">
         <TD align="center"><tt>wedged</tt> <TD><IMG SRC="n_wedged.png"></TR>
      <CAPTION>Basic style settings for nodes</CAPTION>
    </TABLE>
  <P>
    <TABLE border=1>
      <TR><TD align="center"><tt>solid</tt> <TD><IMG SRC="e_solid.png"> 
          <TD align="center"><tt>dashed</tt> <TD><IMG SRC="e_dashed.png"> </TR>
      <TR><TD align="center"><tt>dotted</tt> <TD><IMG SRC="e_dotted.png">
          <TD align="center"><tt>bold</tt> <TD><IMG SRC="e_bold.png"></TR> <TR>
      <CAPTION>Basic style settings for edges</CAPTION>
    </TABLE>
  <P>
    <TABLE border=1>
      <TR><TD align="center"><tt>solid</tt> <TD><IMG SRC="c_solid.png"> 
          <TD align="center"><tt>dashed</tt> <TD><IMG SRC="c_dashed.png">
          <TD align="center"><tt>dotted</tt> <TD><IMG SRC="c_dotted.png">
          <TD align="center"><tt>bold</tt> <TD><IMG SRC="c_bold.png"> </TR>
      <TR><TD align="center"><tt>rounded</tt> <TD><IMG SRC="c_rounded.png">
          <TD align="center"><tt>filled</tt> <TD><IMG SRC="c_filled.png">
          <TD align="center"><tt>striped</tt> <TD><IMG SRC="c_striped.png"></TR>
      <CAPTION>Basic style settings for clusters</CAPTION>
    </TABLE>
  <P>
  The effect of <tt>style=tapered</tt> depends on the <A HREF=#d:penwidth>penwidth</A>,
  <A HREF=#d:dir>dir</A>, <A HREF=#d:arrowhead>arrowhead</A> and <A HREF=#d:arrowtail>arrowtail</A> attributes.
  The edge starts with width <tt>penwidth</tt> and tapers to width 1, in points. The <tt>dir</tt> attribute
  determines whether the tapering goes from tail to head (<tt>dir=forward</tt>), from head to 
  tail (<tt>dir=forward</tt>), from the middle to both the head and tail (<tt>dir=both</tt>), or no
  tapering at all (<tt>dir=none</tt>). If the <tt>dir</tt> is not explicitly set, the default for the
  graph type is used (see <A HREF=#a:dir>dir</A>). Arrowheads and arrowtails are also drawn, based on the
  value of <tt>dir</tt>; to avoid this, set <tt>arrowhead</tt> and/or <TT>arrowtail</TT> to <TT>"none"</TT>.
  <P>
  <B>Note:</B> At present, the tapered style only allows a simple filled polygon.
  Additional styles such as <TT>dotted</TT> or <TT>dashed</TT>, or multiple colors
  supplied via a <A HREF=#k:colorList>colorList</A> are ignored.
  <P>
  The following table illustrates the <tt>style=tapered</tt> with <tt>penwidth=7</tt> and
  <tt>arrowtail=none</tt>.
    <TABLE border=1>
      <TR><TD><tt>dir</tt> &#92; <tt>arrowhead</tt><TD align="center"><tt>normal</tt><TD align="center"><tt>none</tt></TR>
      <TR><TD align="center"><tt>forward</tt> <TD><IMG SRC="normal_forward.png"> <TD><IMG SRC="none_forward.png"> </TR>
      <TR><TD align="center"><tt>back</tt> <TD><IMG SRC="normal_back.png"> <TD><IMG SRC="none_back.png"> </TR>
      <TR><TD align="center"><tt>both</tt> <TD><IMG SRC="normal_both.png"> <TD><IMG SRC="none_both.png"> </TR>
      <TR><TD align="center"><tt>none</tt> <TD><IMG SRC="normal_none.png"> <TD><IMG SRC="none_none.png"></TR>
    </TABLE>
  <P>
  Additional styles are available in
  device-dependent form. Style lists are passed to device drivers, which
  can use this to generate appropriate output.
  <P>
  The style attribute affects the basic appearance of nodes, edges and graphs, 
  but has no effect on any text used in labels. For this, use the <A HREF=#d:fontname><TT>fontname</TT></A>, <A HREF=#d:fontsize><TT>fontsize</TT></A> and <A HREF=#d:fontcolor><TT>fontcolor</TT></A>
  attributes, or the <TT>&lt;FONT&gt;</TT>, <TT>&lt;B&gt;</TT>, <TT>&lt;I&gt;</TT>, etc. 
  elements in <A HREF=shapes.html#html>HTML-like labels</A>.
  <P>
  The <TT>setlinewidth</TT> style value can be
  used for more control over the width of node borders and edges than is
  allowed by <TT>bold</TT>. This style value takes an argument, specifying the
  width of the line in <A HREF=#points>points</A>. For example, <TT>style="bold"</TT> is
  equivalent to <TT>style="setlinewidth(2)"</TT>.
  <B>The use of <TT>setlinewidth</TT> is deprecated; one should use the
  <A HREF=#d:penwidth><TT>penwidth</TT></A> attribute instead.</B>

<DT><A NAME=k:viewPort><STRONG>viewPort</STRONG></A>
<DD>"%lf,%lf,%lf,%lf,%lf" or  "%lf,%lf,%lf,'%s'"
  <P>
  The viewPort <TT>W,H,Z,x,y</TT> or <TT>W,H,Z,N</TT>
  specifies a viewport for the final image. The pair (W,H) gives the
  dimensions (width and height) of the final image, in
  <A HREF=#points>points</A>.
  The optional Z is the zoom factor, i.e., the image in the original layout will be
  W/Z by H/Z points in size. By default, Z is 1.
  The optional last part is either a pair (x,y) giving a position in the original layout of the
  graph, in
  <A HREF=#points>points</A>, of the center of the viewport, or the name N
  of a node whose center should used as the focus.
  By default, the focus is the center of the graph bounding box, i.e.,
  (bbx/2,bby/2), where "bbx,bby" is the
  value of the bounding box attribute <A HREF=#a:bb>bb</A>.
  <P>
  Sample values: <TT>50,50,.5,'2.8 BSD'</T> or <TT>100,100,2,450,300</TT>.
  The first will take the 100x100 point square centered on the node <TT>2.8 BSD</TT>
  and scale it down by 0.5, yielding a 50x50 point final image.

</DL>
<a class="twitter-timeline" href="https://twitter.com/search?q=graphviz" data-widget-id="932041383875153920">Tweets about graphviz</a> <script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+"://platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");</script>
</BODY>
</HTML>
{:/nomarkdown}