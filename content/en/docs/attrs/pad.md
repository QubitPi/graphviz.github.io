---
defaults:
- default: 0.0555
  suffix: '(4 points)'
flags: []
minimums: []
title: pad
types:
- double
- point
used_by: G
description: Inches to extend the drawing area around the minimal area needed to draw the graph
---
If `pad` is a single double, both the x and y pad values are set
equal to the given value. This area is part of the
drawing and will be filled with the background color, if appropriate.

Normally, a small `pad` is used for aesthetic reasons, especially when
a background color is used, to avoid having nodes and edges abutting
the boundary of the drawn region.
