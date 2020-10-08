---
layout: post
title:  "Proofs for the Ten Hats Riddle"
categories: math
mathjax: true
---

In my [last post]({% post_url 2020-10-04-threeColorHats %}) I looked at how variants of the ten hats riddle can affect what the best strategy is to use. I want to take a step back and do some proofs, building towards an information-theoretic understanding of this riddle. The main thing I want to answer is

> Even if we analyze some particular strategy, how can we be certain that there isn't a better strategy the prisoners could have used?


If we have this in mind we can relate this to what exact effect an adversarial riddle-giver has on their chances of survival, and use the notion of how much information each participant has in order to put optimal bounds on this.

## What Exactly Does Each Prisoner Know?

I think this may be the most impotant part in establishing the bounds of the riddle and the variants. Some of these bounds are totally subjective and a matter of taste, but for our purposes I'll establish the following:

> A mad wizard captures 10 people and presents to them a challenge. Each will be lined up facing forwards so that they can only see the people in front of them, and each will be given either a red or a blue hat. This means they can see the colors of the hats of everyone farther down the line, but not their own or anyone behind them. Then starting at the back of the line each must guess the color of their hat else be slain. The 10 prisoners will have time to agree upon a plan beforehand.

- before the challenge the prisoners have time to discuss a plan, this means
	- every prisoner knows how many prisoners there are total
	- the plan they agree upon is some computable function that they carry out during the challenge
- during the challenge they can see the other prisoners in front of them, and therefore know
	- which position they are in line by counting
	- the color of each of the hats of those in front of them
- as each prisoner answers the are either killed by lightning bolt or survive, therefore
	- as each answer is given the other prisoners both know what the answer is, and if it was correct or incorrect

In regards to the color of the hats there are a few variants concerning what the prisoners know about this
1. Traditional Riddle - there are two colors of hats, the prisoners know that there are only two and what these colors are. We can represent this by saying the hats are chosen from $\\{0,1\\}$
1. k-color - there are $k$ colors of hats, the prisoners know both k and what each of these colors are, represented by each hat being chosen from $\\{0,1,...k\\}$
