---
layout: post
title:  "Three Color Variant of Ten Hats Riddle"
categories: math, games
mathjax: true
---

> Can you solve the ten hats riddle if there are more than 2 colors of hats?

Continuing the long tradition of mathematicians and computer scientists fantasizing about being kidnapped by supranatural forces I was looking at the ten hats riddle the other day. If you haven't seen it before there is a version under [Induction puzzles on Wikipedia](https://en.wikipedia.org/wiki/Induction_puzzles#Ten-Hat_Variant) as well as a [fun animated version](https://www.youtube.com/watch?v=N5vJSNXPEwA) by Ted-Ed. Overall the riddle asks a group to create a strategy given the following situation

> A mad wizard captures 10 people and presents to them a challenge. Each will lined up facing forwards so that they can only see the people in front of them, and each will be given either a red or a blue hat. This means they can see the colors of the hats of everyone farther down the line, but not their own or anyone behind them. Then starting at the back of the line each must guess the color of their hat else be slain. The 10 prisoners will have time to agree upon a plan beforehand.

> What is the best strategy they can come up with to win this challenge?


Give that as a starting point, what could they do if instead the wizard's challenge had 3 colors of hat?


### Analyzing The Two-Color Answer

To figure this out lets see why the answer to the traditional problem works. Usually this is stated as 

> Whoever is at the back of the line counts the number of blue hats, saying "blue" if they see an even number and saying "red" if they see an odd number, meaning half the time they go free. The next person in line can see all of the hats in front of him and can therefore deduce the color of his own hat based on that information.

In essence the first person calculates the parity of the hats and reports this as their answer. Because this [parity bit](https://en.wikipedia.org/wiki/Parity_bit) is enough information to correct any 1 bit error they can figure out the color of their own hat with certainty. There are a number of key features to this answer

- the first prisoner cannot know anything about their own hat, and so will never have a chance of survival better than guessing
- their process involves the first prisoner calculating some function of all of the information which they can see in a way that captures some global property of everyone else's hats
- because each prisoner can hear the guesses (and outcome) of everyone before them, and see all of the hats after them, this means that no matter where they are in line every prisoner has perfect information about all hats other than their own (assuming two colors, we'll return to this later)

And to set the stage for later with a bit of information theory, lets ask, "why is hearing the first prisoner say blue or red enough to go on?" Another way to look at this is because there are two hat colors the first prisoner speaking gives everyone 1 bit (literally) of information. One way to think about this is to consider the total number of possible ways that the challenge could go down, and then consider how each prisoner is doing a process of elimination.

Take the prospective of the second prisoner in the line, Mr. @-sign, `X@XXXXXXXX`. Before the challenge starts  


### Solving Three Colors

## Additional Variants

Lets look at a few ways that the riddle could be expanded for fun.

### The Wizard Knows Your Plan

Lets say in this variant the evil wizard uses his scrying orb to listen in on your plan, and can use this information in order to choose the distribution of hats.

> A mad wizard captures 10 people and presents to them a challenge. Each will lined up facing forwards so that they can only see the people in front of them, and each will be given either a red or a blue hat. This means they can see the colors of the hats of everyone farther down the line, but not their own or anyone behind them. Then starting at the back of the line each must guess the color of their hat else be slain. The 10 prisoners will have time to agree upon a plan beforehand, however the wizard is listening in and will know this plan as well. Given that the wizard can choose the distribution of the hats the day of the challenge what is strategy that maximizes how many escape on average? How does this affect the person at the front of the line, and are there any alternative plans which counter the wizard's advantage?


So in general if they use the same plan as before the 9 prisoners at the end of the line still have the same 100% chance to guess correctly, however the first prisoner is dead. Because the wizard knows what scheme (deterministic computable function) he is going to use to make his guess, the wizard can simply choose the opposite color and guarantee his demise. In general whatever function the prisoners agree on will need to be deterministic because they won't have any way to communicate during the test and will need a solid plan in order to do better the chance.

The only alternative I can think of is that the first prisoner generates a random bit by simply guessing the day of, and the second prisoner does the parity check using this random bit. So specifically this would mean the plan is

> The first prisoner simply guesses either red or blue. The second prisoner then counts the number of blue hats, if there are an even number he guesses the same as the prisoner behind him, and if there an odd number guesses the opposite. Using this information each successive prisoner counts hats and then announces the color of their own hat.


In this scenario the first two prisoners would have a 50/50 chance of guessing correctly, meaning that on average 9 prisoners survive. This means that the expected value is the same as using the traditional plan even when the wizard listens in, but maybe you consider this more fair for the guy at the start of the line. 

- Is it provable that no plan can have an expected survival rate greater than 9 given a wizard who listens in?
- Is there any plan which gives all prisoners an equal chance to survive no matter their place in line? If so what? And if not, can you prove no such plan exists?


### N people, k colors

### Repeated games

### N people, k colors, and without knowing k