---
title: "Column/Drilled Shaft Capacity Part 1: Rectangular"
mathjax: true
layout: post
categories: engineering
---

This is the first of a type of article I'm calling "Engineering Deep Dive." In an engineering deep dive, I'm going to take a structural engineering problem which I found interesting to solve, and painstakingly walk through it step-by-step, showing as much math as I can manage. I assume the reader has a working knowledge of structural engineering concepts. So my non-engineer friends should read onwards at their own risk! 

I expect this first engineering deep dive topic to take about three articles, and it will cover the math behind creating a strength capacity calculator for rectangular and circular columns or drilled shafts, which are subjected to both axial load and bending moments (so we will generate a PM diagram). At the end of the series, an excel file that performs these calculations will be available for download.



![bridge_col](/testpreviewsite/assets/bridge columns.jpg){: width="600" }

The three articles will be organized like so.
* Part 1 - Nominal capacity curve for rectangular cross-sections
* Part 2 - Nominal capacity curve for circular cross-sections
* Part 3 - Phi factor application and sheet download

Let's jump into the first article!

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

![x_sect](/testpreviewsite/assets/cross section.svg)

## Axial-Only Capacities

## Balanced Condition
