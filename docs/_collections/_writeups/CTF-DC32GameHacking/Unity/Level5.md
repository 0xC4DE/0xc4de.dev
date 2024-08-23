---
title: Level 5
layout: default
---

# Level 5
Level 5 is the first level where I looked at it and immediately knew I had to do something different. 

Probably because of the big red kill box, but IDK you tell me

![Image]({{post_url}}Images/Pasted image 20240820215450.png)

The hint said to use DNSpy, so away I went.

Now I didn't know this before but, it's extremely important to use the correct version (64 bit or 32 bit) of DNSpy for the application you're trying to modify. I spent at least an hour figuring out why the 64 bit version just wasn't handling it. It's a learning experience they say...

After loading up the 32 bit version of DNSpy, I just loaded the Unity.exe, because I figured "That's where scripts are stored right?" That was not right. After some light googling and finding a [video](https://www.youtube.com/watch?v=-7dW3Cfn2O8) on quite a strange game, I determined you're supposed to use the "Assembly-CSharp.dll" to peek and edit scripts.

Here's a picture of DNSpy when you load it in properly. Get familiar with it, I will be using it much more in these writeups.
![Image]({{post_url}}Images/Pasted image 20240820215847.png)

Immediately notice the scripts on the left. There's some intriguing things such as "HasFish" "KillFloor" "L9_timer" "LazerTurret" and "PitFall".

This is where I learned I could have made the Pitfall from Level 4 not even fall! The horror!

Well, the lesson here was not lost, at this point, I just needed to look at little harder at what happens when the character does die, the turret shoots you, aha! That's going to be what I go for next.

So "LazerTurret" looks like this:
![Image]({{post_url}}Images/Pasted image 20240820221136.png)

Notice the "FireLazer", maybe I can just, turn that off. By making it `return`
![Image]({{post_url}}Images/Pasted image 20240820221406.png)

From here I'm sure you know the drill by now, I walk into the box, dont die, and collect the flag:

`GHCTF{OK_now_you_have_godmode}`

And I can continue to [Level 6](Level6)




