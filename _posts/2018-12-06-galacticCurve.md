---
layout: post
title:  "Finding Dark Matter with a Galactic Rotation Curve"
categories: physics, software
---

Finished a pretty interesting school project about analyzing spectral data. Here is a small piece of what we looked at.

![Galactic spectrum](/assets/images/code_projects/galaxy.png){: .left-image}

The main things to notice are

- the three curvy galaxies on the left <- this is the scientific data
- the strong vertical lines
- random white pixels
- the general noise in the background

The image is taken of an edge-on galaxy through a dispersive element, meaning that each wavelength of light has been spread out to a particular column of data. If I can calibrate the pixels of dispersion with actual differences in wavelength I can see how half of the galaxy is slightly blueshifted while the other half is slightly redshifted. This shift comes from how the galaxy is spinning, meaning that this information can correspond to a plot of distance from galactic center against rotational velocity.


![Velocity distribution](/assets/images/galaxy/velocity.png){: .left-image}

Which is where the dark matter comes in. The expected shape of this galactic rotation curve, without unknown matter, would follow the same distribution as the velocities of the planets about the sun. However the general flattening near the edges indicates that there is a large concentration of mass away from the galactic center, and away from where we can observe normal matter.

Doing this analysis was the main challenge of the project. Removing sky lines, estimating the sensitivity of pixels in the CCD, and ignoring stray cosmic rays.  
