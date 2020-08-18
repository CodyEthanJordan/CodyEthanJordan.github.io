---
layout: post
title:  "A Number Riddle - Closest Without Going Over"
categories: math
mathjax: true
---

Been thinking about a riddle recently.

> What is the largest number still strictly less than 1 that can be described using n mathematical symbols?


To keep it managable I'm thinking about limiting it to basic symbols of arithmetic `1234567890^*/+-.!`. In essence the riddle is to create a number closest to 1 without going over. In order to get an idea of whats going on I made a [jupyter notebook to brute force](https://github.com/CodyEthanJordan/TutorialNotebooks/blob/master/ClosestWithoutGoingOver.ipynb) and evaluate all the combinations. This pretty quickly failed for two reasons

- floating point errors mean its hard to get that close to 1
- it gets really slow, really fast, like $16^n$

However it worked out the answers for the first few

n | string
--- | ---
1	| `0`
2	| `.9`
3	| `.99`
4	| `.999`
5	| `.9999`?
6	| `1-1/9!`?

Unfortuantely the brute force method fails at about the same point at which the analysis starts to get interesting.	I think in the n=7 to ~100 range there might be some interesting stuff. On my own I thought of a few strategies which could work:


- raising numbers close to 1 to fractional powers, something like `.9999^.5`
- the obvious lower bound, a string of 9s `.99999999`...
- create the largest number possible, $x$, and `1-1/(x)`

Asymptotically the problem may become easier to analyze than some of the large but finite cases. I suspect that some of the medium-range numbers may have ranges where each of these various tricks is the winner, but as n gets larger and larger I think it will eventually be dominated by `1-1/(x)` and trying to create the largest number possible in $n-6$ characters. 


One possibility there would be `1-1/9!!!!!!!`..., although that depends on more of the 'spirit' of the question in how you exactly define your syntax. I'd regard that as illegal because of the convention that `!` and `!!` (the [double factorial](https://mathworld.wolfram.com/DoubleFactorial.html)) are different operations, not repeated factorials.


Once again though as $n \to \infty$ I don't think any of these quibbles will matter. Even requring redundant parenthesis or being pedantic about the syntax would only introduce a constant or maybe polynomial number of additional symbols, which might make the large values of $n$ reduce to a more limited version of [Who Can Name the Biggest Number?](https://www.scottaaronson.com/writings/bignumbers.html).