---
layout: post
title:  "Finding a Possessed Computer"
categories: software
---

Managing Ubuntu machines I'd been upgrading some servers to Ubuntu 18.04 but came across something...odd

![Demons](/assets/images/computers/cursed.png){: .left-image}

A machine which would not boot, and when I tried to boot in to the recovery mode I was presented with a series of increasingly disturbing visions. First, some UI weirdness, and then having to type in the administrator password a dozen times before it stuck.

I tried to check what directory I was in with "pwd" and ended up with a list of users logged in to the system instead. Random keypresses would end up in the BASH terminal or vanish in to the ether. I wasn't exactly sure how to proceed other than put

### My Ubuntu is possessed 18.04.1

in to Google. This (eventually) lead to an old bug report where the recovery menu and root terminal would fight for input, and the recovery menu would continually restart.

I wiped the drive.
