---
category: Tech
title: The making of an arcade stick, pt. 1
---

I'm making an arcade stick. Or rather, I'm taking a pretty bad arcade stick and making it into an awesome arcade stick, and I'm going to let you in on how I do it.

First of all, at the time of writing, this project isn't  yet completed, so beware that forward-looking statements may change in the future.

### Parts

[@[The Mayflash fighting stick](building-arcade-stick-pt-1/IMG_0703.JPG@150x150)](@(building-arcade-stick-pt-1/IMG_0703.JPG@1600x1600))
[@[Seimitsu LS-32 and Sanwa OBSF-30](building-arcade-stick-pt-1/IMG_0731.JPG@150x150)](@(building-arcade-stick-pt-1/IMG_0731.JPG@1600x1600))
[@[Sanwa OBSF-30](building-arcade-stick-pt-1/IMG_0734.JPG@150x150)](@(building-arcade-stick-pt-1/IMG_0734.JPG@1600x1600))
[@[Seimitsu LS-32](building-arcade-stick-pt-1/IMG_0736.JPG@150x150)](@(building-arcade-stick-pt-1/IMG_0736.JPG@1600x1600))
[@[Seimitsu LS-32](building-arcade-stick-pt-1/IMG_0742.JPG@150x150)](@(building-arcade-stick-pt-1/IMG_0742.JPG@1600x1600))
[@[Sanwa OBSF-30](building-arcade-stick-pt-1/IMG_0756.JPG@150x150)](@(building-arcade-stick-pt-1/IMG_0756.JPG@1600x1600))
[@[Sanwa OBSF-30](building-arcade-stick-pt-1/IMG_0769.JPG@150x150)](@(building-arcade-stick-pt-1/IMG_0769.JPG@1600x1600))

* [Mayflash Fighting Stick](http://www.mayflash.com/?Products/PCUSB/PC042.html) (2009 circuit board rev.)
* Seimitsu LS-32
* 8x Sanwa OBSF-30
* Quick disconnects (16x 2.4 mm, 8x 4.8 mm)
* Wiring

### Tools needed

* Soldering iron (with solder)
* De-soldering braid
* Crimping tools for the quick disconnects
* Various sizes of screwdrivers
* Wirecutter
* Powerdrill
* Dremel
	* Cutting attachment
	* Sanding attachment

### Skills needed

* Basic electronics
* Medium soldering skills (button soldering points are surface mounted, but rather large)
* Basic power tools usage (and a steady hand)

### About the circuit board

The Mayflash Fighting Stick comes in different revisions, with slightly different circuitry. This guide is for the 2009 revision, indicated by the lettering 2009-04-20 on the circuit board.

[@[Circuit board markings](building-arcade-stick-pt-1/IMG_0700.JPG@400x400)](@(building-arcade-stick-pt-1/IMG_0700.JPG@1600x1600))

This revision uses a common ground for the buttons, but not for the joystick. Earlier revisions have used a common ground for the joystick too.

I **strongly** recommend that you first buy your fighting stick and take a look at the circuit board before you order any other parts. If e.g. you have the 2007 revision of the circuit board, I would instead recommend you use either a Seimitsu LS-32-01[^1] or a Sanwa JLF-TP-8YT joystick, which is made for a common ground circuit.

[^1]: The difference between the Seimitsu LS-32 and the LS-32-01 is that the LS-32-01 includes a circuit board with a standard 5 pin connector (4 signal leads and 1 common ground).

### Opening the Mayflash fighting stick

This is easy. Flip the fighting stick upside down. Two screws are visible, remove them. There are four more screws under the rubber feet. Gently partially lift each rubber foot, remove the screw and re-affix. Avoid touching the adhesive in order for it to get a good grip when you re-affix it. 

[@[The fighting stick, upside down](building-arcade-stick-pt-1/IMG_0692.JPG@400x400)](@(building-arcade-stick-pt-1/IMG_0692.JPG@1600x1600))

The bottom should come right out.

[@[Inside the fighting stick](building-arcade-stick-pt-1/IMG_0696.JPG@400x400)](@(building-arcade-stick-pt-1/IMG_0696.JPG@1600x1600))

### Removing the joystick

Start by removing the ball top. On the bottom end of the joystick, there's a large slotted screw. Insert a flat-head screwdriver, and hold on to prevent the joystick spinning around as you unscrew the ball top.

[@[Unscrewing the ball top](building-arcade-stick-pt-1/IMG_0709.JPG@400x400)](@(building-arcade-stick-pt-1/IMG_0709.JPG@1600x1600))

The wiring to the joystick is connected to the circuit board via two-lead connectors. Disconnect those.

[@[The connectors](building-arcade-stick-pt-1/IMG_0719.JPG@400x400)](@(building-arcade-stick-pt-1/IMG_0719.JPG@1600x1600))

In each corner of the joystick assembly there's a long Philips screw. Unscrew the four screws, and the joystick assembly should pop right out.

[@[The connectors](building-arcade-stick-pt-1/IMG_0701.JPG@400x400)](@(building-arcade-stick-pt-1/IMG_0701.JPG@1600x1600))

### Next up…

This is as far as I have gotten. My action plan for the future is as follows:

 * Cut off the leads to the joystick and attach them to 4.8 mm quick disconnects.
 * Cut off the moulded joystick holding assembly (at least the screw mounts and two of the walls)
 * Drill holes through the front panel to attach the joystick and mounting bracket (for bracing the joystick) using the same screws
 * Remove and desolder the button assembly
 * Sand down the holes for the buttons (which are approx. 4 mm ø too small for the OBSF-30 buttons)
 * Mount buttons
 * Create a common ground lead with quick disconnects
 * Create signal leads with quick disconnects
 * Solder the leads onto the circuit board
 * Assemble everything
 * Kick some ass in [Ninja Baseball Bat Man](http://en.wikipedia.org/wiki/Ninja_Baseball_Bat_Man)
 
So look forward to one or more posts detailing the rest of the modding. I'm also going to update this post with some images, as soon as I have taken them :)