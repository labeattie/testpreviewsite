---
title: "Column/Drilled Shaft Capacity Part 1: Rectangular"
mathjax: true
layout: post
categories: engineering
---

This is the first of a type of article I'm calling "Engineering Deep Dive." In an engineering deep dive, I'm going to take a structural engineering problem which I found interesting to solve, and walk through it step-by-step, showing as much math as I can manage.

I expect this first engineering deep dive topic to take about three articles, and it will cover the math behind creating a strength capacity calculator for rectangular and circular columns or drilled shafts, which are subjected to both axial load and bending moments. This type of member is called a beam-column. At the end of the series, an excel file that performs these calculations will be available for download.



![bridge_col](/testpreviewsite/assets/edd_pm/bridge columns.jpg){: width="600" }

The three articles will be organized like so.
* Part 1 - Nominal capacity curve for rectangular cross-sections
* Part 2 - Nominal capacity curve for circular cross-sections
* Part 3 - Phi factor application and sheet download

## Background
Those who have been brave enough to read on probably already know this, but I'll give a quick background on reinforced concrete. Concrete is cheap and is extremely strong in compression (being squished), but it is very weak in tension (being pulled apart). This is why it's reinforced with steel reinforcing bars, which are strong in tension. These two types of loads which act longitudinally on the member are called axial loads. 

When subjected to bending (imagine breaking a stick over your knee), the member experiences a combination of compression and tension. Because of this, a reinforced concrete member can actually handle more bending if it also has a bit of extra compression loading on it. 

The capacity we will calculate will be in the form of a graph of a curve showing the points of theoretical failure at different combinations of axial loads. This is commonly called a PM diagram, as P is a variable commonly used to represent axial loads, and M is often used for bending moment loads.

From here on, I assume the reader has a working knowledge of structural engineering concepts. So my non-engineer friends should read onwards at their own risk! 

## Assumptions
I'm a bridge engineer, so I will make this calculator complaint with the AASHTO LRFD Bridge Design Specifications, 9th Edition. These concepts and the final result should match up reasonably well with the ACI code for my buildings-focused engineering friends. If you walk through these articles with me, doing the math for ACI factors and assumptions would be straightforward.

Here are some of the assumptions we will use in developing this calculator. These are either required or allowed by AASHTO section 5.6.2.

* Strain compatibility - plane sections remain plane, reinforcement is fully developed and bonded, and strain is directly proportional to distance from the neutral axis.
* Maximum usable concrete compressive strain is 0.003.
* Elastic perfectly plastic steel reinforcement stress-strain relationship.
* Concrete tensile strength is neglected.
* Reinforcement in compression is neglected.
* Rectangular compressive stress distribution assumed for strength limit state for concrete (Whitney stress block).
* Concrete strength is less than or equal to 10 ksi.
* Reinforcing steel yield strength is less than or equal to 100 ksi.
* AASHTO compression-controlled vs. tension-controlled strain limits used to calculate phi factors.

We will generate the math and equations needed both with generalized variables, and we will show the math with the following example cross section.

![x_sect](/testpreviewsite/assets/edd_pm/cross_section.svg)

With:
* f'c = 4 ksi
* f<sub>y</sub> = 60 ksi
* E<sub>s</sub> = 29,000 ksi

## Axial-Only Capacities
We'll start off with the easiest cases: pure compression and pure tension. We will do pure tension first, and I was tought to always draw out my cross-sectional strain, stress, and resultant force diagrams when doing any reinforced concrete analysis (thanks [Dr. Harik][harik]!), and while they probably aren't needed for these purely axial cases, I will provide them for completeness.

![tension](/testpreviewsite/assets/edd_pm/tension.svg)

As the concrete will be cracked in ultimate tension, the nominal strength of the section in tension is simply the tensile capacity of the rebar, which equals A<sub>s</sub>*f<sub>y</sub>. For our example cross section the calculation is as follows.

$$P_{nt} = (A_{s\_top}+A_{s\_bot})*f_y = (1.24in^2+1.24in^2)*60ksi = 149kips$$

For the full compression case, you could just neglect the reinforcment (and we will be ignoring compression reinforcement in all other cases), but I went ahead and included it because it's simple to do so. The maximum usable compression stress in concrete with f'c < 10 ksi is 0.85*f'c according to AASHTO.

![compression](/testpreviewsite/assets/edd_pm/compression.svg)

$$P_{nc} = 0.85*f'c*(A_g-A_s)+f_y*A_s = 0.85*4ksi*(12in*16in-2.48in^2)+2.48in^2*60ksi = 793kips$$

## Balanced Condition
Now we'll get more into the meat of the problem. Essentially when we make a PM diagram, we set the extreme concrete compression fiber to it's maximum value (we are using 0.003), as this is necessary for strength failure. We then vary the strain in the reinforcing steel, and back out what combination of axial load and moment gives us that failure condition.

We can do that for as many points as we deem necessary in order to construct a decent PM curve. I prefer to choose the steel strain values by select multiples of the steel strain at first yield (ε<sub>sy</sub>), which is equal to f<sub>y</sub>/E<sub>s</sub>. 

When the member fails at ε<sub>s</sub> = 1.0*ε<sub>sy</sub>, this failure condition is commonly known as the balanced failure point, because if the steel strain at failure is less than this value, the concrete fails before the steel yields (compression-controlled: a sudden failure), and if the steel strain is greater than this value, the steel will yield before the section fails (tension-controlled: a slow, observable failure). 

AASHTO actually sets a range of values to denote whether a section is tension or compression controlled, with an in-between zone, but we will go over that in the third article in this series.

When designing pure bending members, we want to be sure we are tension-controlled by making sure we don't use too much rebar, so that a failure would be slow and people would see it before anything collapsed. In beam-columns, this doesn't apply, as columns are usually compression-controlled by nature. However, the balanced condition gives us a great point to calculate for our PM diagram.

![balance](/testpreviewsite/assets/edd_pm/balance.svg)


[harik]: https://www.engr.uky.edu/directory/harik-issam