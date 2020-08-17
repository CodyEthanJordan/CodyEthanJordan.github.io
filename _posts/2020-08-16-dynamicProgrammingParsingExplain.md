---
layout: post
title:  "Using Dynamic Programming for Parsing Puzzle"
categories: software
published: false
---

"Dynamic programming" can seem a bit mysterious for folks just starting out, so I want to walk through a [few different ways](https://en.wikipedia.org/wiki/Multiple_representations_(mathematics_education)) to visualize the problem to try to give a few ways to understand whats going on here.

## The Problem

Given a string of numbers corresponding to English letters (`1 -> A ... 26 -> Z`), how many valid ways are there to parse the numbers into a string of characters? 


For example "424" can be parsed as "4\|24" -> "DX", or as "4\|2\|4" -> "DBD", meaning that there are two ways.

> Input: string containing digits 0 - 9


> Output: number of valid ways to parse into a string of letters A - Z

## The Solution

`throw new NotImplementedException()`