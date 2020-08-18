---
layout: post
title:  "Tutorial on Parsing Techniques"
categories: math, teaching
---

I started writing a [jupyter notebook explaining parsing](https://github.com/CodyEthanJordan/TutorialNotebooks/blob/master/Parsing%20Dice%20Notation.ipynb), trying to teach people about how different parsing problems can be handled by increasingly complex techniques. What I've always wanted is for there to be better resources for curious beginners or people who have background in different fields to get a vertical slice of some technical aspect. The main goals for this are to

- introduce how categories of formal languages are required for different parsing techniques (as in, why XML is not a regular language)
- show the power of regex
- talk about some of the issues and techniques when converting data from one representation to another


The main problem which I'm addressing is how something like [AnyDice](https://anydice.com/) operates. This means being able to read in the notation which tabletop roleplaying games use, such as "3d6" and turn this into the output of rolling 3 six-sided die.