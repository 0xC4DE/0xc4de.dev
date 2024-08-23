---
title: Level 4
layout: default
---
# Level 4
At this point in the competition, I was in a workshop with my Wife, for some ICS topic I did not really care to hear (it was hot and I was bored), so I decided I was going to hack away at this.

The first thing you notice as you enter the level is that the flag is right there! Just go and grab it!

![Image]({{post_url}}Images/Level4Pitfall.gif)

... Oh.

Well, One thing to do, escape the pit! The only real way I can discern how to do this is to raise myself above the pit, and put myself back down on the exit area, presumably.

To do that I need one thing, my Z placement in the world. The easiest way to grab, then manipulate that, to me, at the time, was still Cheat Engine.

So I went back to Cheat Engine and started an "Unknown Initial Value" search using the Float type. Note that after hitting "First Scan" nothing will appear because there's just a bunch of things. To sanitize the next results, I make sure to click "Unchanged Value", then I move on both X, Y axis (not jumping!) and do that again. Finally comes the real methodology I used:

* (In the game) jump up a step of the stairs in the pit
* do a "Next Scan" for a "increased value" in cheat engine
* Repeat the previous two until I get to the top
* Once I get to the top, drop to the bottom, do a "Decreased value" next scan

Now, after all that, I notice that there's a *lot* of values left, about 77 in my example, so how do I determine which one is real? Well I noticed some addresses seemed to still be messy, so I did two things:

1. Did a scan for "Exact Value" with NOT selected, and 0
2. Did a scan for "Unchanged Value"

This still left me with 74 values, so what now?

Well on the day of, I simply just changed all of the values to a high number, then positioned myself above the ground, and put them back down to a not so high number! This was a really naive approach that broke multiple things in the game, but it worked!

The real way is to determine the *actual* value, as follows:
* Add all of the addresses into the saved addresses
* Freeze half
* Try to jump
* If jump worked, freeze the other half
* If jump didn't work right, delete the unfrozen half
* unfreeze all addresses, go to step 2

doing this I found a float with the value of ~-3 that was my magic number, and when frozen created a really buggy jump/fall sequence. 

![Image]({{post_url}}Images/Pasted image 20240820214836.png)

This bugginess didn't matter because all I had to do now was just make myself go up, then move a little to the right, then make myself go down! Luckily the floor is at/around Z=0 (I may have ended up killing my character on one occasion, keep the value frozen!)

![Image]({{post_url}}Images/Level4Complete.gif)

With that, the level is complete and can grab my flag

`GHCTF{You_should_play_basketball}`

and move on to [Level 5](Level5) 

After crashing because I forgot to unfreeze some values....
