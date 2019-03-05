---
layout: post
title:  "It Lives! Controlling our Monochromator"
categories: physics, software
---

Our lab uses a high-harmonic generator to turn 800 nm infrared pulses in to a range of higher energy
ultraviolet pulses. However this produces around ten different wavelengths so we direct the laser
on to a diffraction grating to spatially sperate the various harmonics. For this to be reliable this grating is controlled with a stepper motor with [code I developed](https://github.com/CodyEthanJordan/LaserControl).

![Stepper motor controlling grating](/assets/images/monochromator/stepper.png){: .left-image}

The motor is hooked up to a power supply and stepper motor controller, all of which is interfaced to the computer with an Arduino using a USB cable. The electronics were fairly straightforward, and testing it the stepper motor was precise and reliable enough for controlling the diffraction grating.

![Control box](/assets/images/monochromator/box.jpg){: .left-image}

LabView controls the stepper motor and uses a multi-channel scaler to collect photoelectron spectra at every position of the diffraction grating from our time-of-flight spectrometer. Practically this means that we can sweep through the harmonics and see how strong each color of extreme ultraviolet light is coming out of the high-harmonic generator.

![Control box](/assets/images/monochromator/harmonics.png){: .left-image}

The hardest part of this project was trying to get LabView to communicate with something not made by National Instruments. NI didn't seem to have a great library to connect to an Arduino, and although I found a great 3rd-party library it was pretty heavy. The Uno wasn't able to fit both the LabView interface library and the stepper motor library at the same time, rendering it pretty useless.

I ended up hacking together a basic command protocol where the Arduino would listen for commands over the serial line, and using the LabView serial controller directly.

- m500# : move to stepper position 500 steps
- z : treat the current position as the new zero
- p : report back the current position

There are a few rough edges still to sort out. The Arduino stores its current position in non-volatile storage so being powered-off doesn't re-zero it, but adding an encoder to the motor would be better. Also there should be a few more safety checks to increase reliability when using the laser at high power.
