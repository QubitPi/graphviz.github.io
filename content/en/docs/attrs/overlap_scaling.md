---
defaults:
- '-4'
flags:
- prism
- neato
- sfdp
- fdp
- circo
- twopi
minimums:
- -1.0e10
title: overlap_scaling
types:
- double
used_by: G
description: Scale layout by factor, to reduce node overlap.
---
When <code>[overlap](/docs/attrs/overlap/)=prism</code>, the layout is scaled by this factor, thereby
removing a fair amount of node overlap, and making node overlap removal
faster and better able to retain the graph's shape.

* If `overlap_scaling` is negative, the layout is scaled by
`-1*overlap_scaling` times the average label size.

* If `overlap_scaling` is positive, the layout is scaled by
`overlap_scaling`.

* If `overlap_scaling` is zero, no scaling is done.
