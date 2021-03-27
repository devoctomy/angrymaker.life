---
title: Useful Prints - Coffee Filter Caddy
author: Nick Pateman
date: 2021-03-13 11:43:00 +0000
categories: [Blogging,3dPrinting,Useful]
tags: [3dprinting,useful,modification]
math: false
mermaid: false
---

One of the more rewarding aspects of 3D printing is being able to design something useful, from scratch, print it out and then start actually using it to make your life that little bit better. Or maybe even to save yourself a few £££. This coffee filter paper caddy is one of the more useful things I've printed, as it gets used every day. The only problem is that the original design only fits small filter papers, that's nothing a little blender work can't cure.

## The Original Design

![My original design (on the left), printed in 'wood' PLA, next to the new design, printed in rainbow PLA](/assets/img/prints/useful/filtercaddy/1.jpg)

The original design, pictured above and on the left was my first "final" version of a filter paper caddy.  It is designed to fit '01' V60 filter papers and works pretty well. It has a lid that drops shut on its own and a simple hinge mechanism to keep the 2 parts together.


![The original design with its hinge mechanism.](/assets/img/prints/useful/filtercaddy/2.jpg)

I decided to stick with this design as having used it for over a year now and not experienced any issues, why change what works? All I needed was for it to be a bit taller and a bit deeper.

## Simple Modification

As long as the 3D model has simple geometry, it's just a matter of dragging a few vertices to extend the mesh along a single axis at a time.

> I won't go into too much detail of how I done that in Blender in this post as it can be a total pain in the arse if you don't know what you're doing, and I have no plan on doing Blender tutorials in this blog. Sorry!  I know right? What a cunt!
   

![The mesh in Blender, in all its glory.](/assets/img/prints/misc/blender1.jpg)

Just to give you the basic gist of what was done to resize this, I had to do the following,

1. Change to 'Right' orthographic view
2. Switch to wireframe,
3. Switch X-Ray on
4. Select all of the vertices on the right past the start of the top flat section of the base piece
5. Move them all to the right enough to occomodate the larger size papers
6. Repeat the process with the top section, this time moving the vertices up
7. Using the measure tool to make sure that the inner cavity is a little larger than the filter papers

Hopefully that should give you some guidance at least, one thing I will recommend is *not* trying to make things to an exact size when 3D printing, as every 3D printer has a different level of tollerance and will not print everything exact, so you may need to play around and iterate on your design before you find the right size.

## Printing

Once done, I printed in some Rainbow PLA that I recently used for another project (coming soon), and BOOM, it worked perfect first time.

![The new design with lid open, it slides on great with very little friction.](/assets/img/prints/useful/filtercaddy/3.jpg)
![Both caddy sizes with their lids taken off.](/assets/img/prints/useful/filtercaddy/4.jpg)

The 2 caddy's pictured above with their lids taken off. Simple but effective, and means I can keep my filter papers nice and safe.
## Downloads

<form method="get" action="/assets/downloads/sources/filtercaddyblender.zip">
	<button type="submit" class="btn btn-success">Blender Sources (Everything, including the failed revisions)</button>
</form>
<br/>
<form method="get" action="/assets/downloads/stls/filtercaddy.zip">
	<button type="submit" class="btn btn-success">STL Files for both caddy sizes</button>
</form>