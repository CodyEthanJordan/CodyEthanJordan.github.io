---
layout: post
title:  "GMTK 2020 Game Jam Post-Mortem"
categories: games, programming
---

Me and some friends made [Takes Two to Disco](https://codyethanjordan.itch.io/takes-two-to-disco) for the [GMTK 2020](https://itch.io/jam/gmtk-2020) game jam, with pretty good results for our first time working together.

![small-screenshot](/assets/images/takestwotodisco/takestwo.png)

The music came together really well and the experience is pretty chaotic. Looking at the comments a lot of them focused on how difficult the game is. I wouldn't know, I haven't been able to beat it.


> This is pretty Fun and Difficult.


> Nice idea, love the music, at first, is kind of hard, but when you figure it out it's great.

Of course there are always detractors 

> ...really nice idea, but it's not quite there with the 'fun' factor...

## Data Scraping

It took a whole week of waiting around before the results came in, so I got impatient and tried to see what I could cover by scraping data from itch.io. I made a small [jupyter notebook](https://github.com/Deal-With-the-Dev/GMTK2020_OutOfControl/blob/master/ScrapingOutStats.ipynb) to collect data and see how we were stacking up on number of reviews.

![results-histogram](/assets/images/takestwotodisco/hist.png)

This is a histogram of the number of reviews every game got, which basically tells you what you'd expect. The median number is around 10 per game, and then a very few games received 100s of reviews. Some of this appears to be from good-looking games quickly rising to the top, or the combination of having a [unique visual style](https://itch.io/jam/gmtk-2020/rate/697103) and being lucky enough to get featured on one of Mark Brown's gameplay streams.


Takes Two To Disco ended up in the 97th percentile by this measure, but didn't go galactic. Another interesting result was seeing how much accessibility affected how many reviews a game received. The numbers made it pretty clear here too, having a web build makes your game far more likely to get noticed.

## How It Went

I think the single greatest feature I added was enemies leaving behind randomly colored splats when they die. In terms of how much it added to the experience per difficulty its very fun and got a lot of player feedback. 


The Good
- having a very modular component-based model instead of inheritance ("has a" vs "is a") for the enemies made adding in new features very fast
- being able to leverage Unity's tilemaps, WebGL builds, and sprite stuff made development and deployment go very fast
- was able to get some new designers up to speed quickly and set up so they could do rapid iteration on level creation
- solid gameplay loop and simple idea
- music


The Bad
- didn't have enough time to put in better [game feel](https://www.youtube.com/watch?v=AJdEqssNZ-U)
- had a few merge conflicts and versioning issues working with scenes, eventually made some UI and camera elements into prefabs to re-use across separate scene, but this could have gone smoother
- could have had a better tutorial and more reasonable difficulty curve


The Ugly
- never really settled on a consistent art style

Shipped something, pretty fun, good responses. Overall a win.
