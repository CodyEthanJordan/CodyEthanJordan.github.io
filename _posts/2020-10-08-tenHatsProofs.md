---
layout: post
title:  "Proofs for the Ten Hats Riddle"
categories: math
mathjax: true
---

In my [last post]({% post_url 2020-10-04-threeColorHats %}) I looked at how variants of the ten hats riddle can affect what the best strategy is to use. I want to take a step back and do some proofs, building towards an information-theoretic understanding of this riddle. The main thing I want to answer is

> Even if we analyze some particular strategy, how can we be certain that there isn't a better strategy the prisoners could have used?


If we have this in mind we can relate this to what exact effect an adversarial riddle-giver has on their chances of survival, and use the notion of how much information each participant has in order to put optimal bounds on this.