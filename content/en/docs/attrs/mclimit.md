---
defaults:
- '1.0'
flags:
- dot
minimums: []
title: mclimit
types:
- double
used_by: G
description: Scale factor for mincross (mc) edge crossing minimiser parameters
---
Multiplicative scale factor used to alter the `MinQuit` (default = 8)
and `MaxIter` (default = 24) parameters used during crossing
minimization.

These correspond to the number of tries without improvement before quitting
and the maximum number of iterations in each pass.
