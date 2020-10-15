---
layout: post
title:  "Making My Blog Look Like DND"
categories: design
---

I wanted to create a new theme for my website inspired by the old school look of AD&D books or RIFTS. I've always loved their typographic style and layout and always love laying out RPG stuff in LaTeX.

# The Plan

Right now I'm using markdown to write the posts and using [Jekyll](https://jekyllrb.com/) to generate the site through GitHub. Needing some way to have a way to see how the changes look as I work I came up with a plan

> Instead of just using lorem ipsum text create an actual blog post and see how it looks. I'll have to create a lot of rambling text to get a good idea of how the layout looks

## Next Section

How does code look?

```latex
\documentclass[10pt,twoside,twocolumn,openany]{book}

\usepackage{realmlords}
\usepackage{pdfpages}
\usepackage{etoolbox}

\patchcmd{\chapter}{\thispagestyle{plain}}{\thispagestyle{fancy}}{}{}

\begin{document}
\null
\NoBgThispage
\DeactivateBG
\includepdf[pages=-]{images/FrontPage_noImage.png}
\ActivateBG

\tableofcontents
\clearpage

\chapter{Character Creation}
\section{Player's Guide}
Entire realms burned and souls were traded by the hundreds
```

Maybe try out some Python

```python
import numpy as np
import matplotlib.pyplot as plt
import scipy as sp
import sympy as sym
from scipy.special import binom
from scipy.special import comb

import warnings
warnings.filterwarnings('ignore') #overflow and stuff is gonna happen, might try symbolic versions later
```
### Time to hit up some bullet points

Uh oh bullet points

- point 
- point 
- point 
- point 
- point 

Ordered list?

1. First item
1. The next item
1. The next item
1. The next item
1. The next item
1. The next item

#### The ultimate challenge, some lore ipsum

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi sed aliquet enim. Donec in consequat nunc, id scelerisque massa. Sed viverra magna ac urna condimentum elementum. Praesent vulputate ultrices odio in egestas. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nunc non venenatis mauris. Etiam et diam dolor. Ut vestibulum nibh sed bibendum convallis. Aenean rhoncus diam at neque efficitur, a finibus tortor auctor. Vivamus et odio nisl. Aliquam in massa imperdiet, congue nunc quis, gravida nisi. Sed tristique, urna et hendrerit pellentesque, ante nulla porttitor tellus, eu pharetra lectus sapien at elit.

> *Creating a Realmlord*
> Choose up to 10 points of Curses and equivalent points of
Boons. Major Boons or Curses count as 3, while minor count
as 1.
> - Maximum of 1 Cursed Destiny
- Maximum 5 Minor Curses
- Receive Marked by Law and Chaos and Sanctuary for
free
- Maximum 2 Personality Curses, of which only 1 may be
Major
- Maximum 1 Major Magical Boon (in addition to Sanctuary)



Phasellus eu nulla nunc. Donec at consectetur dolor, a finibus velit. Proin mollis tincidunt sapien, lacinia accumsan ante. Pellentesque sit amet lacus sodales, ornare ante porttitor, iaculis risus. In sem dolor, semper eu facilisis eu, blandit et nunc. Donec semper accumsan ipsum, vehicula ultricies quam porttitor sed. Phasellus ipsum ex, molestie eget venenatis quis, auctor et erat. Mauris ac odio eget nisl iaculis elementum. In hac habitasse platea dictumst. Praesent at odio vulputate justo ullamcorper fringilla ac ac est. Curabitur consectetur aliquet pretium. Nam in nisi nec nisl fringilla scelerisque at et odio. Praesent auctor ultricies tortor et aliquet. Integer neque dolor, sollicitudin vitae ex eget, consectetur semper neque.

----

Phasellus eu nulla nunc. Donec at consectetur dolor, a finibus velit. Proin mollis tincidunt sapien, lacinia accumsan ante. Pellentesque sit amet lacus sodales, ornare ante porttitor, iaculis risus. In sem dolor, semper eu facilisis eu, blandit et nunc. Donec semper accumsan ipsum, vehicula ultricies quam porttitor sed. Phasellus ipsum ex, molestie eget venenatis quis, auctor et erat. Mauris ac odio eget nisl iaculis elementum. In hac habitasse platea dictumst. Praesent at odio vulputate justo ullamcorper fringilla ac ac est. Curabitur consectetur aliquet pretium. Nam in nisi nec nisl fringilla scelerisque at et odio. Praesent auctor ultricies tortor et aliquet. Integer neque dolor, sollicitudin vitae ex eget, consectetur semper neque. Trying out a table

| Priority apples | Second priority | Third priority |
|-------|--------|---------|
| ambrosia | gala | red delicious |
| pink lady | jazz | macintosh |
| honeycrisp | granny smith | fuji |


Tags?



