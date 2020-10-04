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

Take the prospective of the second prisoner in the line, Mr. @-sign, `X@XXXXXXXX`. Before the challenge starts each person could end up with one of 2 colors of hat, meaning that there are $2^{10}$ possible challenges which the wizard could choose to present. However once the day begins @ can look at the 8 prisoners in front of him and see `X@BBRRBRRB` so out of the $2^8$ possible ways that the 8 prisoners in front of him could be decked out he knows specifically which one of those situations he is in. Dividing this means that from the original $2^{10}$ challenges he knows that he must be in one of the remaining $2^{10} / 2^8 = 4$ of them.  

If at this moment in time he was immediately asked to guess he would have 4 possible scenarios to choose from. Since 2 of them involve him wearing a blue hat, and 2 of them involve him wearing a red hat, this means he would still have a 50/50 chance to get it correct.

However once the first prisoner takes a guess @ listens with trepidation, if he hears the sound of a lightning bolt he knows that the first prisoner was wrong, otherwise he knows he was right. In either case he now knows which of the remaining $4 / 2 = 2$ situations he is in. Something to note here is that this piece of information isn't all that useful to him, but is still important to account for theoretically. Also the reason that we are dividing each time is because each new clue he learns more or less cuts the possibilities into sections, and informs you which of those sections is "true" and which is "false". For more on this see essentially [all of information theory](https://en.wikipedia.org/wiki/Entropy_(information_theory)).

So with two possibilities in order to have absolute certainty of his own hat color he needs exactly 1 bit of information. This is where he thinks about the plan and what it was that the first prisoner said. Because there are two things which could be the case here, red or blue, this leaves him knowing that he is in $2 / 2 = 1$ situation in particular. That sort of analysis is how we can establish that there is enough information theoretically present in order for the second prisoner to figure out their hat color. Also because of what we noted before about the successive prisoners being able to figure out the hats of everyone before them by listening, this same analysis applies to everyone else in the line.


### Solving Three Colors

So what if there were three colors of hat?

> A mad wizard captures 10 people and presents to them a challenge. Each will lined up facing forwards so that they can only see the people in front of them, and each will be given either a red, blue, or green hat. This means they can see the colors of the hats of everyone farther down the line, but not their own or anyone behind them. Then starting at the back of the line each must guess the color of their hat else be slain. The 10 prisoners will have time to agree upon a plan beforehand. What is their best plan and their chances of survival?


To solve this one lets generalize the idea of counting if there an odd or even number of blue hats to instead use modular arithmetic. So in the two color variant say the following is agreed upon

> Blue = 0
> 
> Red = 1
>
> First prisoner calculates X = (sum of all visible hats) mod 2, then says the color for X
>
> Each successive prisoner then has to solve H + (sum of all other hats) = X mod 2, where H is the color of their hat

For three colors we can come up with a strategy which is similar, create some X such that everyone can solve H + (sum of all other hats) = X mod 3. If we can show that this is always solvable we can show that the prisoners can do pretty well even with three colors of hat.

In order to do this lets look at an example, the prisoners agree that

> Blue = 0
>
> Red = 1
> 
> Green = 2

The first prisoner calculates $X = \sum_{i=2}^N H_i \mod 3$ and then announces $X$ as his guess. The next prisoner has to solve for his own hat $H_2$ using $H_2 + \sum_{i=3}^N H_i = X \mod 3$ correctly in order to survive. Because they can see all of the other hats and know X from the first prisoner's guess this has a unique solution. Similarly down the line $\forall n > 3: H_n = X - \sum_{i \ne n} H_i \mod 3$. 

From an information theory standpoint the same argument as above applies, except replacing 2 with 3 everywhere. Narrowing down $3^{10}$ possibilities with a trit of information is the same as the binary case. In general this is also why most information theory uses binary by default, nothing is particularly gained by using a non-binary system because it is already expressive enough to capture the essence of the problem.

With that now things become even harder.


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


### Colorblind

Some chance of error

### N people, k colors

This is a direct generalization. What strategy can be used and what are the expected survival rates for N participants in a situation where there are k colors of hats?

> A mad wizard captures N people and presents to them a challenge. Each will lined up facing forwards so that they can only see the people in front of them, and each will be given one of k colors of hat. This means they can see the colors of the hats of everyone farther down the line, but not their own or anyone behind them. Then starting at the back of the line each must guess the color of their hat else be slain. The N prisoners will have time to agree upon a plan beforehand.

### Repeated games

Consider a variant where if anyone dies then the survivors are put back into the dungeon and are forced to play the game again the next day, and so on until either everyone is dead or they complete the challenge with everyone surviving. What are the expected number of survivors in this case.

> A mad wizard captures N people and presents to them a challenge. Each will lined up facing forwards so that they can only see the people in front of them, and each will be given one of k colors of hat. This means they can see the colors of the hats of everyone farther down the line, but not their own or anyone behind them. Then starting at the back of the line each must guess the color of their hat else be slain, and if anyone is killed the survivors will be forced to play the same game the next day. The N prisoners will have time to agree upon a plan beforehand. What is the best plan they can come up with and how many survivors will make it on average? How do these values change if the wizard is able to listen in on their plan each night?

### N people, k colors, and without knowing k

Here is a pernicious one I thought of as well. What happens if the prisoners don't know how many colors of hats there are? 

> A mad wizard captures N people and presents to them a challenge. Each will lined up facing forwards so that they can only see the people in front of them, and each will be given a hat of some color. This means they can see the colors of the hats of everyone farther down the line, but not their own or anyone behind them. Then starting at the back of the line each must guess the color of their hat else be slain. The N prisoners will have time to agree upon a plan beforehand, but will have to do so without knowing how many colors of hats the wizard intends to use. Additionally should anyone guess a color of hat which no one is wearing, everyone is slain.


I think in this scenario the first prisoner is totally out of luck. Without knowing what his own hat looks like or even what distribution hats are pulled from all he can do is guess a color at random. His chances of survival are basicaly 0, and more the domain of philosophy than mathematics. The real challenge though is can that prisoner do anything to help everyone else.


## The Ultimate Challenge: N people, k colors, the Wizard is Listening and Some of You Are Colorblind

Lets examine the most twisted version I could come up with.