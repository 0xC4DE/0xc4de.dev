---
layout: default
title: Unity Writeup 1
---

# Level 1
Level 1 was the warmup for the entire thing, it's the first level you launch into when you get into the game. Because I wasn't sure where to start I took a look at the guide & decided to download Cheat Engine.

However, the first REAL challenge was Windows. I wrestled with Defender for about 20 minutes trying to download Cheat Engine! It continually quarantined CheatEngine.exe until I turned it almost completely off!

Anyhow, getting into level 1 you are told to take the weapon, but it is behind a box with some health attached to it 
![Image]({{post_url}}Images/Pasted image 20240820203510.png)

In order to get this box you need to just keep hitting it, so lets see what happens when I do that.
![Image]({{post_url}}Images/Level1Hurt.gif)
Well obviously I'm not going to have enough health, lets get into Cheat Engine to just give myself more!

After restarting the level, I load up Cheat Engine and attaching to the process I run a basic "exact value" search for Float values at 100.

![Image]({{post_url}}Images/Pasted image 20240820204701.png)

After that, I give it a few and select "Unchanged value" just to help remove clutter, this is a decent practice if you have what I will call a "stable  value" like health.

Now, I get hit, and do another exact value search for 90, Immediately there's only one result
![Image]({{post_url}}Images/Pasted image 20240820204845.png)

Now I double click it, change the value to 1000, and my health immediately updates!
![Image]({{post_url}}Images/Pasted image 20240820204912.png)

Lucky me, that turned out to be correct. I can now take damage and pick up the gun. 

After doing that the flag spawns above my head, a chime plays, and the exit opens.

![Image]({{post_url}}Images/Pasted image 20240820205217.png)

collecting the flag with jump (Spacebar) adds it to my inventory and gives me the gun I picked up. I open my inventory with 'i', giving me the flag.

`GHCTF{this_is_the_first_flag_woot}`

I can now move on to [Level 2](Level2)

