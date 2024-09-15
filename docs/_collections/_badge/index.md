---
layout: default
title: DC256 Badge
category: badge
permalink: /badge
---

# This Page

This page will have the updates, information, and things related to the badge that I am creating with the DC256 group.

Also, no pictures right now since no prototypes exist yet! (this will be removed when I have images :)

## Badge Overview

The badge discussed on this page is prepared for the DEFCON-256 group and will (hopefully) be worn for the DEFCON 33 conference taking place in August of 2025.

I wanted to create something iconic to this group, as to express our identity and provide some neat features as a side-effect. So, after some brainstorming I came up with the idea of using the iconic Saturn V rocket that is shown at the Huntsville Space & Rocket Center. The name of such a badge is the "Saturn V Badge" or the "Rocket Badge" for the uninitiated.

Originally the badge would contain an RP2040 as the main microcontroller, but that was quickly switched to an ESP32-S3-WROOM-1. This will allow the badge to do almost anything that somebody wants over Wi-Fi, bluetooth, or serial, it also makes it reusable. The badge will also be in two parts: the backplane (with the most electronics) and the front part, which will feature the Saturn V and (mostly) cover up the electronic components of the badge, but will allow several LEDs to shine through due to some trickery with PCB design.

Other features will include: 

* Battery Charging Circuit for LiPo batteries (will be included with purchase)
* 7 Addressible RGB LEDs
* 2 Simple Add-Ons (SAOs)
    * Both are wired to the I2C ports on the ESP32
    * There are planned "Official" SAOs that will likely take the form of other Iconic Saturn Rockets.
* Firmware w/web interface
* Challenge attached to the badge, Firmware, Crypto? You'll have to wait and see!
* Potential "Wardriving" mode that will collect names of APs it comes across. Will probably use a switch.

Minor features that dont really count:

* ESP32-S3-Wroom has easily solderable exposed pads if you wished to mod the badge, I will also try to include solder points.
* Solder pads for a clock (deep sleep feature that I wont implement)
* Anything else that people suggest and I find cool enough to implement!

Ideas I have no guarantee of implementing but I'm putting here so that I can remember them

* Capacitive touch of the rocket to change LED modes
* SD-Card storage slot (only needs a few pins, there's plenty to spare!


## September 15th: Planning, Preproduction, Prototyping

Yesterday, I announced that I am making a badge for the DC256 group (to the group) I had previously chattered about it but this time I did a short talk about the badge discussion what few details I could at that moment.

I have spent the past 3 weeks (As of September 15th) spending a LOT of freetime learning, designing the schematic, and creating the design for the PCB for this badge. I will spare the gorey detail of cerating the art, the backplane of the badge, and design especially since I am by no means an artist. What I will talk about is that the main part of the badge is based off the original art of the DC256 sticker and painstakingly traced by somebody who does not know how to create vector art. After hours of clicking, cutting, and overal tweaking with a LOT of frustration (ask my wife) I finally landed on a good enough design for a first-order and placed said order.

As of now this is where this ends. Hope to have more updates when V1 shows up and even more after I start adding some features.. As of now I plan on making sure everything works, and doing a phase 2 with any new features that people express interest in. I hope you're here from the interest check, hello otherwise! 
