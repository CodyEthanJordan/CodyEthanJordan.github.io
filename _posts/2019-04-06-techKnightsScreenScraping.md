---
layout: post
title:  "How to Cheat at Games with Python: A Workshop"
categories: software, teaching
---

Something which always bothered me about learning programming early on is how not many of my classes connected the basic skills we learned to programs which I would actually want to make. Either something useful my friends could use, or a game, or a tool to solve a practical problem which I had. Because of this I've always liked data scraping as a way to turn information from a complex world into something which can be used in a program.

![Workshop Flyer](/assets/images/workshop/CnCFlyer.png)

So I themed this workshop around how to take basic Python skills and use that to manipulate a game. The [source code for the game (in Unity) and the script to cheat it are both on GitHub](https://github.com/CodyEthanJordan/TechKnights2019_ScreenScraping), along with basic documentation about setup and the goals for the workshop.


The essential "problem" which I wanted to solve is how some RPGs let you roll your character's stats at the beginning of the game. Baulder's Gate in particular lets you roll three dice for each stat, save/load an array, and then finalize your character. For this I made a quick game which just replicates the functionality of this screen, along with some [customs stats for my Cults n Chimeras](https://docs.google.com/document/d/1AgNQMNDxm7puPKpjjB07FwxwIlmOhmr7TmryFOxkxFo/edit?usp=sharing).

![Cults n Chimeras Screenshot](/assets/images/workshop/CultsNChimeras.png)

Heres the essential problem

> How can I get the best stats possible in this game? 


With the workshop I discussed a couple of approaches with the audience

- Use something like CheatEngine to manipulate the code in memory
- Create your character and then alter the save file on disk
- Don't cheat (this was an audience suggestion)
- Use a program to read the screen and control mouse inputs to roll until a good result comes up

The last one is what I decided to explore for the rest of the talk, focusing on how to turn an image from the screen into useful data from your program to manipulate. This, and controlling the mouse, I approached with pyautogui. Didn't do anything fancy with OCR because it only needs to read the numbers 3 through 18 in fixed places on the screen, and it worked pretty well. Also discussed some pros and cons with everyone there

- Using the program itself will be limited by whatever speed the program can respond to use input
- It is "undetectable" in some sense because it can be made to operate very similar to user input
- Debugging a rogue program which has control of your mouse can be challenging
- The process may take far longer than direct editing due to the unlikelihood of rolling straight 18s

This last one along with the data collecting raised an interesting point, [how do the probabilities work in this scenario?](couponCounting). 


In conclusion, workshop went well, I think peopled learned. I was surprised how few people in a programming club had ever played Dungeons and Dragons but heartened by how many of them were interested in probability and Python. Looking forward to doing the next one.
