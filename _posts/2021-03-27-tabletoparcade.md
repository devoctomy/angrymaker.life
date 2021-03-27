---
title: Making a Mini Table-Top Arcade
author: Nick Pateman
date: 2021-03-27 08:32:00 +0000
categories: [Blogging,3dPrinting,Fun,Difficult,Emulation,Raspberry-Pi]
tags: [3dprinting,difficult,fun,emulation,raspberry-pi]
math: false
mermaid: false
---

One thing I've been getting really into as of late is emulation on the Raspberry Pi. Whether it be retro gaming on the Sega Master System or learning to code Amos on the Amiga, the possibilities are practically endless and there are so many projects out there for free, or ones that you can purchase to enable you to have a little 3D Printing / Electronics project of your own, you just need to look about, typically on YouTube.

Which is exactly where I found this little beauty,

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/lmgmUAL6M6c" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Gathering The Parts

Now before you go off setting your 3D printer into action for days on-end, to produce your beatiful arcade cabinet, I would suggest making sure that you can actually source all of the components.  You should be able to, it just might take some time.  It took me about a month, from start to finish, that includes the 2 weeks or so that it took for the screen to come from China. So bear that in mind, it's not a quick weekend thing, *unless* you have all of the parts ready-to-go.

I'm just going to list a few key parts that that I purchased for this project to help save you some searching,

* [HDMI / VGA / AV Control Driver Board + 8-inch HE080IA-01D 1024 * 768 IPS HD LCD Display](https://www.aliexpress.com/item/4000183134282.html?spm=a2g0s.9042311.0.0.1b134c4dUUaOMg)

> Please Note : I did not get the USB to DC adapter with my screen and had to bodge one together myself using an old power adapter and a USB terminal connector.  On the plus side, I didn't have to pass the screen through the power-switch like he does in the video, it works fine with the Raspberry Pi 4.

Preferably when you order the arcade joystick you will order the correct one to begin with, but I ended up ordering one with a slightly different encoder board that had a USB connector on it.  Unfortunately this got in the way so I had to order the correct encoder board separately so that everything fit into the cabinet nicer.  This wasn't essential but I wanted to do it properly.  The Joystick itself actually turned out to be Sanwa, although not advertised as such, the buttons were not though, although to be honest I doubt it will matter much.

* [EG STARTS 2 Player USB Controller To PC Game 2x 5Pin Stick + 4x 24mm Push Button + 16x 30mm Buttons For Arcade Games DIY Cabinet Kits Parts Mame SNK KOF Raspberry Pi Retropie Projects & Red / Blue](https://www.amazon.co.uk/gp/product/B076H38W5G/ref=ppx_yo_dt_b_asin_title_o05_s00?ie=UTF8&psc=1)

* [Quimat Zero Delay Arcade USB Encoder PC to Joystick for Mame Jamma & Other PC Fighting Games](https://www.amazon.co.uk/gp/product/B06XD1WF8G/ref=ppx_yo_dt_b_asin_title_o07_s00?ie=UTF8&psc=1)

This following adapter, although way too big really, enabled me to expose a USB-C connector on the outside of the cabinet so that I can power the device soley through that.  This does come with a down side relating to undervoltage which I explain briefly at the end, but hasn't turned out to be a show stopper for me as the device still functions fine.

* [Duttek USB C Panel Flush Mount Cable Gold-Plated USB 3.1 Extension USB Mount, Dash Mount, Flush Mount, Panel Mount Cable, For Car, Boat, Motorcycle (Round Single Type C 1M/3.3Ft)](https://www.amazon.co.uk/gp/product/B08B7VV3M5/ref=ppx_yo_dt_b_asin_title_o09_s00?ie=UTF8&psc=1)

These little speakers are surprisingly difficult to get hold of, and pretty expensive if you ask me. So if you can source an alternative that fits in the cabinet, then I would, but if you want to keep everything vanilla, this is where I purchased them from.

* [Soundtraxx 810078 40mm x 28.5mm Oval 8 Ohm Speaker](https://www.ebay.co.uk/itm/Soundtraxx-810078-40mm-x-28-5mm-Oval-8-Ohm-Speaker/233766386145?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2057872.m2749.l2649)

## Preparing The 3D Printer(s)

Unfortunately this was the single most annoying part of the project, due to a combination of my calibration issues and inherent issues with part collisions, I ended up wasting a shit load of awesome [Eryone - Ultra Silk Copper PLA](https://www.amazon.co.uk/gp/product/B082QNWRXX/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1), unfortunately that's 3D printing for you so you just have to deal with it.

Basically what was happening was, when printing the main bottom piece of the cabinet, my printer was colliding with the print, only ever so slightly but as it's a solid design, it was enough to relocate the printer head and ruin the print, a whole day through printing, when I thought that everything was going fine.

![First Layer Porn : That Eryone - Ultra Silk Copper PLA in all it's glory.](/assets/img/prints/fun/arcade/1.jpg)

![One failed print, after roughly 24 hours of printing.](/assets/img/prints/fun/arcade/2.jpg)

So how did I resolve this issue with collisions? Well technically I didn't I just switched to my Eryone ER-20 which seems to out perform every other 3D printer I have at the moment. It printed it perfectly, first time.

![My Eryone-ER20 doing it's thing, reliably, unlike my Ender 3 V2.](/assets/img/prints/fun/arcade/3.jpg)

![The completed bottom part, 1 day, 4 hours and 33 minutes after it started.](/assets/img/prints/fun/arcade/4.jpg)

I also had to switch to a different PLA as it was looking unlikely that the Copper PLA would last, fortunately I had some [SUNLU - Rainbow Silk PLA](https://www.amazon.co.uk/Filaments-Rainbow-Printer-spools-Filament/dp/B085QB1JQV/ref=sr_1_7?dchild=1&keywords=SUNLU+rainbow&qid=1616836518&sr=8-7) that I hadn't even tried, and to be honest, I think the end result looks great.  I ended up using a combination of the Rainbow PLA for the main body and some awesome [Eryone - Matt Black PLA](https://www.amazon.co.uk/Eryone-filament-printers-dimensional-accuracy/dp/B08JGP1JFB/ref=sr_1_5?crid=3T0L6FQELLJJ1&dchild=1&keywords=eryone+matte+black&qid=1616836623&sprefix=eryone+ma%2Coffice-products%2C154&sr=8-5) for the side panels.

![All printed parts complete, ready to be assembled.](/assets/img/prints/fun/arcade/5.jpg)

I only had 2 issues with the final printed parts,

* Firstly the Matt Black Raspberry Pi mount, pictured above, lying ontpop of the back grill, was too weak, and snapped, but may have been down to my printer as that was done on my Ender 3 V2.
* Also the feet were a bit pointless, I attempted using TPU to start with but it just kept jamming in my extruder so I really couldn't be bothered with it at that stage of the process. So the feet got shit-canned and I printed the Raspberry Pi mount in Rainbow PLA on my Eryone ER-20. I also replaced the feet with stick on rubber pads.

## Assembly

So as for the assembly, things went pretty smoothly.  I just followed along with the YouTube video (linked at the start of this page) and everything happened as it should. Even with my shitty soldering abilities for the stereo amplifier module.

![The stereo amplifier, neatly in place.](/assets/img/prints/fun/arcade/6.jpg)

![The stereo amplifier again, close-up](/assets/img/prints/fun/arcade/7.jpg)

![All of the internals, ready for assembly.](/assets/img/prints/fun/arcade/9.jpg)

![The joystick and buttons, complete with the original encoder board that I swapped out as it didn't fit properly](/assets/img/prints/fun/arcade/8.jpg)

![Almost entirely assembled](/assets/img/prints/fun/arcade/10.jpg)

As it goes, this was actually quite painless, and very enjoyable, although I did do a few steps incorrectly which resulted in me dropping some C-Bombs, but it wouldn't be me if that hadn't happened.  The end result was awesome and filled me with pride.

## The Final Build

![My baby, in all its glory!](/assets/img/prints/fun/arcade/11.jpg)

The observant of you may notice the mark on the top black panel, that was caused by me attempting to use super glue to stop it from bowing out, as there are no screw holes in this location.  Unfortunately it didn't go as cleanly as I had hoped so I ended up with that small mark, but to be totally honest, I don't care, just look at it!

## Final Notes

So with that all done, are there any problems with this design?

* The screen is directly powered from the Raspberry Pi, using a USB to DC jack adapter, and even with an adequate power supply this does cause some voltage dips.  So if I were to fix that, I would using a 12v DC to 2 x 5v USB module and power them separately from that.

* The joystick plate isn't as snug as I would like it to be and it can lift slightly whilst in use. I would rather it was screwed in, but there is nothing to screw it to in this design so would require some reworking.

* The speakers are a little noisy. I should have used proper speaker cable, not the cable suggested in the video, but I just didn't think at the time.

Do I recommend building this yourself? Hell yeah, get it done!