---
title: "Column/Drilled Shaft Capacity Part 2: Circular"
mathjax: true
layout: post
categories: engineering
---

Pretty fitting that we have our article on circular column capacity on pi day :) (March 14th). We're picking back up right where we left off from [Part 1 (rectangular column/drilled shaft capacity)][part_1] and are ready to approach calculting PM capacities for a circular cross-section. But first off, how are we going to find the area and the centroid of the compression block?



![circ_col](/testpreviewsite/assets/edd_pm/bridge columns.jpg){: width="600" }

## Assumptions
Here's a quick reminder om the assumptions listed in part 1. These are either required or allowed by AASHTO section 5.6.2.

* Strain compatibility - plane sections remain plane, reinforcement is fully developed and bonded, and strain is directly proportional to distance from the neutral axis.
* Maximum usable concrete compressive strain is 0.003.
* Elastic perfectly plastic steel reinforcement stress-strain relationship.
* Concrete tensile strength is neglected.
* Rectangular compressive stress distribution assumed for strength limit state for concrete (Whitney stress block).
* Concrete strength is less than or equal to 10 ksi.
* Reinforcing steel yield strength is less than or equal to 100 ksi.
* AASHTO compression-controlled vs. tension-controlled strain limits used to calculate phi factors.

In this article, we will begin including the compression reinforcement in our calculation.

Note on stress block

## Segment Area Derivation

## Segment Centroid Derivation

## Example Problem



### Summary Table

| Description | P (kip) | M (kip*ft) |
|-------------|---------|------------|
| compression | 793     | 0.0        |
| 0εsy        | 451     | 93.0       |
| 0.25εsy     | 366     | 113        |
| 0.5εsy      | 298     | 124        |
| 0.75εsy     | 241     | 131        |
| 1εsy        | 192     | 136        |
| 2εsy        | 115     | 121        |
| 3εsy        | 72.5    | 107        |
| 4εsy        | 45.5    | 96.3       |
| 6εsy        | 13.3    | 81.6       |
| 8εsy        | -5.2    | 72.2       |
| 10εsy       | -17.3   | 65.7       |
| tension     | -74.4   | 0.0        |

## Conclusion
Now we can make PM diagrams for rectangular beam-columns! I'll show a graph of the result below. Thanks for reading and I hope it's been helpful. In the next article we'll begin thinking about doing the same thing for a circular section.

![half_yield](/testpreviewsite/assets/edd_pm/rect_pm_result.jpg)


[part_1]: lucasbeattie.com/drilled-shaft-column-rectangular/