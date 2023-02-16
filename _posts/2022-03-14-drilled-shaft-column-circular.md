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

As stated in the assumptions we will be assuming a rectangular compressive stress distribution as outlined in AASHTO (based on Whitney stress block). This is pretty clearly allowed by AASHTO, but I was interested if the results would be as good as they are in the case of a rectangular cross-section. Multiplying the depth of the stress block by 0.85 seems like it might do something a little different when the compression area is a circular segment rather than a rectangle. 

We will proceed ahead with this assumption though, as integrating a parabolic or any other compressive stress distribution over the area of a circular segment, finding both the volume of the area and the centroid, is exceedingly difficult. I'm not positive that a closed-form solution is impossible, but I think it is. So it would require numerical integration, which is a lot less fun. We'll compare our results to SpColumn's results in Part 3, and see how the rectangular distribution assumption stacks up against a more precise one.

## Segment Area Derivation
So first we have to relate the depth of the assumed compression block to the area of said block. This requires creating a formula for the area of a circular segment based on its depth. To do so, I created the figures below.

![circ_seg_area](/testpreviewsite/assets/edd_pm/circular segment area_inv.jpg)

As can be seen in Figure 1a, we are seeking to calculate $$A_{segment}$$, using only the variables of segment depth, $$δ$$ and radius, $$R$$. We will begin by relating $$δ$$ to the associated interior angle $$\theta$$ as can be seen in Figure 1c.

$$\delta = R-Rcos(\theta)  (Eqn. 1)$$

Next we will relate the segment are to the sector area (the whole light blue slice of the pie) and the triangle area.

$$A_{segment}/2 = A_{sector}-A_{triangle}$$

And now we put that equation in terms of $$R$$ and $$\theta$$.

$$A_{sector} = \frac{\theta}{2\pi}{\pi}R^2 = frac{{\theta}R^2}{2}

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