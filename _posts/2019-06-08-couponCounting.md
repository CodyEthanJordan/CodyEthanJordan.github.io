---
layout: post
title:  "Dice Rolling and Coupon Collecing"
categories: math
mathjax: true
---

When preparing for the [workshop on scraping screen data](techKnightsScreenScraping) I got distracted by trying to answer a probability question.

> Roll three 6 sided dice to generate a number between 3 and 18. How many rolls will it take on average in order to see every number (3,4,5...17,18) which can be generated? What does this distribution look like?


After looking around some I discovered that this is similar to the [coupon collecting](https://en.wikipedia.org/wiki/Coupon_collector%27s_problem) problem, although with a non-uniform distribution. As always Matthew Conroy's ("A Collection of Dice Problems")[https://www.madandmoonly.com/doctormatt/mathematics/dice1.pdf] is the go-to resource for any questions regarding well, dice.

I tried to work this out with [some simulation](https://github.com/CodyEthanJordan/TutorialNotebooks/blob/master/Dice%20Rolling%20and%20Coupon%20Counting.ipynb) which eventually showed me that the answer is "about 30 or so". 

![Plot](/assets/images/coupon/hist.png)

I think the way to go for a more definitive answer though will be to use the methods described in Dice Problems.
