---
title: The Joys of Printer Calibration
author: Nick Pateman
date: 2021-02-14 16:26:00 +0000
categories: [Blogging,3dPrinting]
tags: [3dprinting,calibration,problems]
math: false
mermaid: false
image: /assets/img/mycr6se1.jpg
---

If I were to convey one thing about 3d printing to someone wanting to get into it, it's to not expect everything to go perfectly, and if you don't have the patience to sit through hours upon hours of testing and troubleshooting, don't bother yet, wait until Sony release the 3d Print Man in like 2050. With that said, if you do persist, you will be rewarded.

## You can't Google your way out of everything

Unlike Software Engineering, which I'm confident in saying that Google will be your most valuable resource, 3d printing is still pretty new and the scene is full of people on the wrong side of the [Dunning-Kruger](https://en.wikipedia.org/wiki/Dunning%E2%80%93Kruger_effect) curve, and that includes me, even after about 5 years of this shit.

So last year I saw the Creality CR6 SE appear on Kickstarter, and at the time my current printer was a Creality CR 20 Pro, a right little workhorse that served me well. I fell hook line and sinker for the marketing blurb and thought that the CR6 SE was going to be *the* printer for me.

![Creality CR6 SE in all it's glory](/assets/img/cr6se1.jpg)

Now I won't go into detail of the shit storm that this printer and Creality's own ineptitude bought about, as it's been told a thousand times all over the internet, let's just say that it had *some issues*, which made it a bit burny, a bit sparky, a bit smokey, a combination of all of the above, and none. Yup, it's manufacturing process was far from consistent.

I was actually somewhere in the middle with my list of issues,

* The bed thermister died pretty quickly, requiring me to replace
* The power switch was very flakey, so I replaced it before it became an issue
* The extruder is total shitballs, I replaced that pretty quick
* Firmware has been a complete and utter disaster.  If ever there was an example of a company that should leave software to the experts, it's Creality.  They butcher Marlin with pretty much every printer they release and rely on others to fix it.

At this stage of my journey (around December 2020), even though I was getting some nice prints out of the CR6 SE, the risk of it setting on fire or destroying my laptop was too high so I ordered the BTT SKR CR6 board to hopefully remove the risk entirely.

Installation was a breeze and thanks to the [CR6Community](https://github.com/CR6Community) GitHub and the people working wonders there (primarily [Sebastiaan Dammann](https://github.com/Sebazzz)), I was up and running again in no time... but with a lingering extrusion issue (something I was sure I could solve on my own).

![Under extrusion is a bitch and will result in your printer producing things that you can literally crush with your bare hands.](/assets/img/prints/misc/underextrusion1.jpg)

To cut a long story short, I have just spent the past 3 months failing to get anything to print properly out of my CR6 SE due to under extrusion, something I thought I would resolve through tweaking, but which turned out to actually be caused by a combination of my technique for e-step calibration, and a bug in Marlin, or at least the build I was using.

This is where I get onto Google not being the solution for everything, nothing I searched for helped, what **did** help is a couple of people on the [CR6 SE Discord](https://discord.gg/KMXm3Jd8) and now onto the cause of the issue...

## Sometimes you just need to ask real people for help

After spending a few hours on Discord chatting to some rather helpful and tollerant people we managed to get to the bottom of my issue, my e-step calibration technique which I had acquired from previous Google searches.

What I was doing was this

```
g91
g1 f100 e100
```

* Switch to relative positioning mode
* Extrude 100mm at 100 feed rate

This unfortunately was extruding 200mm of filament with a BMG style extruder with an e-step value of 415.  This caused me to reduce my e-steps down to half that, 207.5 in order to extrude just the 100 requested.

Now in theory this is fine, except that this is wrong, the printer *should* have been extruding just 100mm, and a "bug" (undocumented feature) with relative positioning mode was causing 200mm to be extruded. Meaning that me lowering the e-steps to 207.5 was causing hella under extrusion.

The code to calibrate using absolute positioning mode is as follows,

```
M82
G92 E0
G1 E100 F100
```

* Switch to absolute positioning mode
* Set extruder position to 0
* Extrude 100mm at 100 feed rate

This simple change resolved my under extrusion issue and now my CR6 SE is pumping filament out its hot end with vigor again like it did when it was younger, not just puffs of dust.  It's got its mojo back.

## The calibration continues

Now don't get me wrong, even after all of this, I don't have a perfectly working CR6 SE.  It's pretty good but still has some little issues preventing me from using it for any big jobs just yet, but then that's 3d printing for you, an endless stream of calibration.

The following is the bear minimum I'd expect to have calibrated before I go committing my printer to producing nice things that I want to keep / use,

* E-Steps calibrated
* Flow rate calibrated.
* Retraction distance calibrated.
* Z-Offset calibrated
* Bed dimensions tested and noted
* ABL working correctly

That's my checklist anyway and something I have achieved in practically no time at all on my latest printer, an [Eryone ER20](https://eryone3d.com/products/er-20).  This printer is producing great prints reliably, and cost me roughly half of what my CR6 SE did.

Anyway, I think my point is (after all of that), don't give up, and don't just rely on Google, as there are some pretty helpful people out there that probably know more than you do. Look for a Discord, ask about, talk to some folk.

Happy printing!
