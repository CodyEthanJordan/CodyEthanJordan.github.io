---
layout: page
title: Software Projects
---

A few interesting software projects I've done.


## Developer on Scout for Bucher-Emhart Glass
![Bucher-Emhart Glass Logo](/assets/images/flexbc.jpg){: .left-image}
<ul class="skillList">
<li>C#</li>
<li>WinRT / UWP</li>
<li>MVVM Pattern</li>
<li>Jenkins</li>
<li>MongoDB</li>
<li>WIX Toolset</li>
</ul>

[Scout](https://www.emhartglass.com/SCOUT) is the software that controls
Bucher-Emhart Glass' line of Flex inspection machines. These process a stream of
~400 pieces of glassware per minute, using computer vision to sort good bottles
from bad.

My main role was developing interfaces with [UWP](https://docs.microsoft.com/en-us/windows/uwp/get-started/universal-application-platform-guide)
and C#. Users would need to hand-tune aspects of the vision algorithms when inspecting different styles of container, and to be able to track statistics about specific types of defects. Typically this meant reacting quickly to bottles with broken glass, a big health hazard, by tossing out that batch. Or noticing that a particular molding machine had a large error rate and taking it offline for repairs.

Alongside development I maintained a MongoDB database of test images recorded from machines in the field, and deployed a Jenkins server to run unit tests and create new builds. Being the "build guy" and the "UI guy" I communicated frequently between our development team, QA, and field service personnel using the new software.

## Monochromator Controller
![UHV setup](/assets/images/monochromator/labSetup.jpg){: .left-image}
<ul class="skillList">
<li>C / Arduino</li>
<li>LabView</li>
<li>Optical Control</li>
</ul>

Created an Arduino-based controller for the laser coming out of our lab's high-harmonic generator, which interfaces with data collection in LabView. [My post]({% post_url 2019-02-18-monochromatorLives %}) goes in to more detail about the hardware and how it is used in the lab.

## Galactic Rotation Curves
![Galactic spectrum](/assets/images/code_projects/galaxy.png){: .left-image}
<ul class="skillList">
<li>Python</li>
<li>Conda / Astroconda</li>
<li>Data Analysis</li>
</ul>

Analyzed spectral data from a distant galaxy using Python in order to find evidence of dark matter.
[This post]({% post_url 2018-12-06-galacticCurve %}) explains the steps for conducting the data analysis, mostly using [NumPy](http://www.numpy.org/) and [AstroConda](https://astroconda.readthedocs.io/en/latest/).


## Teaching with Jupyter Notebooks
![Fractal](/assets/images/code_projects/fractal.png){: .left-image}
<ul class="skillList">
<li>Python</li>
<li>Jupyter Notebooks</li>
<li>Numerical Methods</li>
<li>Outreach</li>
</ul>

Slowly building up a [collection of Jupyter Notebooks](https://github.com/CodyEthanJordan/TutorialNotebooks) designed to teach intermediate concepts in physics and numerical methods, and give new programmers a launching point to start tackling scientific questions using those skills. The image is from a [tutorial on Newton's Method making fractals](https://github.com/CodyEthanJordan/TutorialNotebooks/blob/master/Fractals%2C%20Newton's%20Method%2C%20and%20the%20Roots%20of%20Unity%2C%20A%20Tutorial.ipynb).


## Indie Galactic Space Jam: Conversion
![Game logo for Conversion](/assets/images/code_projects/conversion.jpg){: .left-image}
<ul class="skillList">
<li>C#</li>
<li>Unity3D</li>
<li>Game Jam</li>
</ul>

I design games with Unity as a hobby. One of my recent projects is [Conversion](https://github.com/CodyEthanJordan/Conversion), a game about operating a lab bench on Mars developed in 48 hours as
part of [Indie Galactic Space Jam 2018](https://codyethanjordan.itch.io/conversion).

Game development gives me a chance to be more creative with code, and try out a host of design patterns and development techniques.
