---
title: Level 6
layout: default
---
# Level 6
Level 6 starts getting a little weird. There's a cat statue, an apple and we're supposed to give a fish.

Well, in the previous problem, using DNSpy, I noticed there's a script called "HasFish" which sounded like the ideal place to start.
![Image]({{post_url}}Images/Pasted image 20240820221629.png)

This method is a little busy, but I immediately am able to pick out the most important part:

```C#
this.fishItems = this.inventory.InventoryContains("Fish");
```

Well... I have an apple, so what if my inventory contains an apple instead? 

```C#
this.fishItems = this.inventory.InventoryContains("Apple");
```

I change the script, recompile, and relaunch!
![Image]({{post_url}}Images/Pasted image 20240820221901.png)
Tahdah! This gets me the flag, notice how there are some signs at the end of this. When you get near them it says "NO CHEATING ALLOWED BEYOND THIS POINT".

Wonder what that means.

Anyway, the flag is 

`GHCTF{Kitty_appreciates_the_fish_magic}`

and I continue to [Level 7](Level7)
