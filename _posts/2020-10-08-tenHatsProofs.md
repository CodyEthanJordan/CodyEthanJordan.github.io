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

I think this may be the most important part in establishing the bounds of the riddle and the variants. Some of these bounds are totally subjective and a matter of taste, but for our purposes I'll establish the following:

> A mad wizard captures 10 people and presents to them a challenge. Each will be lined up facing forwards so that they can only see the people in front of them, and each will be given either a red or a blue hat. This means they can see the colors of the hats of everyone farther down the line, but not their own or anyone behind them. Then starting at the back of the line each must guess the color of their hat else be slain. The 10 prisoners will have time to agree upon a plan beforehand.

- before the challenge the prisoners have time to discuss a plan, this means
	- every prisoner knows how many prisoners there are total
	- the plan they agree upon is some computable function that they carry out during the challenge
	- the prisoners may generate local random numbers (maybe we'll get to quantum prisoners next time)
- during the challenge they can see the other prisoners in front of them, and therefore know
	- which position they are in line by counting
	- the color of each of the hats of those in front of them
- as each prisoner answers the are either killed by lightning bolt or survive, therefore
	- as each answer is given the other prisoners both know what the given answer is, and if it was correct or incorrect

In regards to the color of the hats there are a few variants concerning what the prisoners know about this
1. Traditional Riddle - there are two colors of hats, the prisoners know that there are only two and what these colors are. We can represent this by saying the hats are chosen from $\\{0,1\\}$
1. k-color - there are $k$ colors of hats, the prisoners know both k and what each of these colors are, represented by each hat being chosen from $\\{0,1,...k\\}$
1. k-color with unknown k - the prisoners know what the colors of the hats are, but not how many of these colors will be used in the challenge ahead of time, these are represented similarly by $\\{0,1,...k\\}$ but with the caveat that k is unknown and cannot be used in their discussion (creation of the computable function)
1. k-color with unknown colors - the key difference between this and the above is that the prisoners are not even sure what the total pool of colors the wizard has access to is, this is equivalent to the wizard being able to choose his hats from any element of the power set of $\mathbb{N}$. The additional challenge here is that not only do the prisoners not know how many colors there but cannot even be sure if any given color is in the set which the Wizard chooses the hats from

There are two variants considering what the wizard knows
1. Random - the wizard chooses some distribution of hats from the set of all possible arrangements at random
1. Adversarial - the wizard knows what the prisoner's plan is (has access to whatever computable function they use) and can choose the least advantageous arrangement of hats based on this

The added dynamic of some prisoners being colorblind, these variants are
1. No Colorblindness - every prisoner knows the color of all hats in front of them as described before
1. With Colorblindness - some number of prisoners will be able to count how many hats they see, but have no information about their color
	- Prisoners who are colorblind know that they are colorblind, and may choose to reveal this. This means anyone behind them in line will be able to know which of those they can see are unable to differentiate hats
		1. Random Order - this variant has the prisoners placed in random order
		1. Prisoners Choose Order - in this variant the prisoners can choose what order to line up in
		1. Adversarial Order - against an Adversarial wizard the wizard may choose the order based on any prisoners who reveal that they are colorblind.

And in terms of what we want to optimize there are a few ways to slice this
1. Maximize Expected Survivors - a solution will be considered better if it maximizes the expected number of survivors
1. Ensure Fairness - somehow ascribe to notions of "fairness" so that no one prisoner has to take a fall for the team
1. Iterated Game - if any prisoner dies the game is repeated the next day with the survivors, how can the expected number of survivors be maximized in this case?

With this model I'm curious how the ultimate game would go, the "k-color with unknown colors" "with colorblindness" against an "adversarial wizard". But before we get there I want to establish some basic bounds

## Basic Bounds

### There Are Only a Finite Number of Strategies

Although there are a countably infinite number of computable functions which the prisoners can agree upon most of these will be totally redundant and fall into a number of equivalence classes. Look at it this way: with two prisoners and two hat colors there are only so many ways that can go. After the first prisoner takes his guess the second prisoner knows either

`red and he was wrong`
`red and he was right`
`blue and he was wrong`
`blue and he was right`

If we write that out as a truth table then in each of those scenarios he can only make one binary choice, meaning that in total there are only 8 deterministic strategies which he could employ, no matter how much he thinks about it internally.

### You Should Never Do Worse than Guessing

At worst everyone in line can simply guess a color, giving them at least a $1/k$ chance if they know what the colors are. This is especially important against an adversarial wizard. If, for example, their plan was `everyone guess blue` then although no worse than guessing randomly against the random wizard an adversarial wizard can easily ensure everyone dies. 

What this means is that even the "worst" plans should still have at least some non-zero number of expected survivors.

## Trivial Proofs

### One Prisoner

#### One Prisoner k-Colors
Because one prisoner has no information whatsoever about his hat all plans are equivalent to guessing. Against an adversarial wizard any plan will have a 0% survival rate as this is equivalent to telling an evil wizard, "I'm going to guess blue tomorrow so....yea...?"

Otherwise picking a random number between $0$ and $k$ will give that prisoner a $1/k$ expected survival rate in the variant where colors are known.

#### One Prisoner k-Color with Unknown Colors

If the colors are unknown, meaning that the wizard can have any element of the power set inside of his closet, the prisoner both has no idea what hat he is wearing nor any idea even what distribution these hats are being drawn from, meaning that he is [almost surely](https://en.wikipedia.org/wiki/Almost_surely) going to die. I think its an interesting question to ask if there are really an infinite, or even uncountably infinite, number of colors, but for this riddle I'm sticking with considering colors to more or less be in some 1 to 1 correspondence with an indexing set, that there is some magical Pantone color book that the wizard orders hats from.

### Two Prisoners

The first step away from being totally trivial this is where things begin to be interesting. Something I want to consider is how the original riddle assigns a particular importance to the first prisoner, and then treats the rest of them as being more or less the same by virtue of induction. While true in the two-color original version I'm not so sure this will hold up as we progress.

#### Two Prisoners with k colors and a Random Wizard
TODO