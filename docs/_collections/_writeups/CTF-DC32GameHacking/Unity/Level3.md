---
title: Level 3
layout: default
---
# Level 3
This level's premise is just like the second's, kill the unicorn to get the flag, one problem, the unicorn now has a shield, it hurts you, and it billboards (faces you) constantly. But I did note that the turning has SOME delay to it, and is not instant!

![Image]({{post_url}}Images/Level3Unicorn.gif)

This one really threw me for a loop initially, mainly because I was stuck on using Cheat Engine to "try to learn it" but also because I did not know how to find the Unicorns Quaternion (used for rotation in Unity, don't google it if you don't want a headache) and freeze it using Cheat Engine to prevent the unicorn from rotating.

After some contemplation I look at the hints:
```
You may need a combination of the first two solutions to solve this level

You may notice that the address that stored your health value has changed with the level switch. In order to save a consistent place your health, ammo, etc are stored you will need to understand multi-level pointers, which can be tricky to grasp at first, but it is a critical aspect of understanding in-memory cheats.
```

I thought "That's weird" to the multi-level pointer stuff and proceeded to do the exact same methods described in Levels 1 and 2 and just raised my ammo & health to really high values.

Now, theoretically all I had to do was get the Unicorn in my line of sight for just a second to shoot it, take note there's a somewhat hidden sprint feature in the game by just pressing shift.

That sounded like a great plan of action... but my L:aptop had other plans. You see I didn't *think* I had a mouse on me, which posed an aiming and movement problem right away. If you aren't aware, It's common for laptops to, at the hardware level, limit keyboard and trackpad use at the same time! This is mostly so that you don't start clicking buttons while you type, but for games, it's **really** annoying!

At this point I did ask for a small hint from the runners, I was told maybe implement a speedhack or make the Unicorn slow, since I handicapped myself by only using Cheat Engine (for now), I considered those out of the question.

I eventually realized I had my mouse+dongle in my LTT Tech Sack™ inside of my backpack which I had completely forgotten I brought to Defcon in the first place! Using this, I was *barely* able to sprint around and shoot the unicorn. Keep in mind *I am left handed* and this game is coded to use WASD controls only, the table had a cloth on it, and my mouse I carry is *not* good quality!

Stories aside, I will show the somewhat-intended solution of jamming yourself between unicorn and shield, which is somewhat finicky, and simply shooting it to death, after you've added ammo and health. 

![Image]({{post_url}}Images/Level3Finish.gif)

There's the flag:

`GHCTF{the_best_defense_is_offense}`

I can now breathe a sigh of relief and continue to [Level 4](Level4)
