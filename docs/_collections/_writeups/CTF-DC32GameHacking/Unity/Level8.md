---
layout: default
title: Level 8
---
# Level 8
Jumping into Level 8 You're given a chest, you press E on it, and you get an item. Presumably there's a really low chance you get the key maybe flag, but I'm not THAT lucky, now am I?

![Image]({{post_url}}Images/Level8Chest.gif)

This level stumped me for the longest time, there was no real method in DNSpy that coordinated to the chest's spawning logic, so I figured that anything that needed to be edited in the game. This was the perfect opportunity to explore "MelonLoader" which was listed in the provided guides as something useful.

Now since the game is definitely, 100% 32 bit, the 32 bit melon loader is required. (I made this mistake at least once)

To install, simply drag+drop the contents of `MelonLoader...zip` into the Games directory.

It's notable that MelonLoader is not really useful on its own, it loads mods, that's about all it does. So what mod would be useful? [Unity Explorer](https://github.com/sinai-dev/UnityExplorer/releases) This is also listed in the hints, but I completely missed it at the time and found it myself (go figure).

To install UnityExplorer I grabbed the "UnityExplorer.MelonLoader.Mono.zip" and did the same thing to install melon loader, drag+drop!

With all of that inside of the directory, I launch the game and go straight to level 8 to dig around.

Now if you've used Unity before to create a game, the UnityExplorer windows should be somewhat familiar, a list of objects, a log, etc. 

I'm going to quickly branch off here and show off the Intended solution, I find it much more enjoyable, as the Unintended solution is quite lame in comparison.
## Intended Solution

What's most interesting is the chest. so search for it, and notice the `lottery_check` and `MoreMountains.TopDownEngine.Loot` and finally `MoreMountains.TopDownEngine.ButtonActivatedZone`
![Image]({{post_url}}Images/Pasted image 20240820224819.png)
![Image]({{post_url}}Images/Pasted image 20240820225054.png)

The loot function might be what I want, as well as `lottery_check`. It's notable that `ButtonActivatedZone` is a helper component that determines if the player is in the zone to even hit the button, neat!

Quickly inside of `Loot` I noticed the `Loot.LootTable` but more importantly `Loot.LootTableSO`. The distinction is important, since I want to follow `LootTableSO`->`LootTable`->`ObjectsToLoot`
![Image]({{post_url}}Images/Pasted image 20240820225755.png)
![Image]({{post_url}}Images/Pasted image 20240820225903.png)
![Image]({{post_url}}Images/Pasted image 20240820225936.png)

Now with all of these objects listed I inspect them one by one until I find one at index 3 with the `Loot` attribute equal to `LotteryFlag`. That's interesting, I should be able to spawn it by Copy/Paste-ing it over, with a `weight` of a very large number, a `ChancePercentage` of 100, and `RangeFrom` =0

With all that done, the flag will spawn almost guaranteed around the chest, just give it a grab (remember to close UnityExplorer with F7, or the flag will be encoded while still inside of your game!)

This reveals the flag:

`GHCTF{wow_wow_lucky_pull}`

Now I can continue to the Final(?) [Level 9](Level9)

## Unintended Solution (forbidden strategy)

Confession, I didn't get the intended solution from this particular level, I had to ask the creator, yes the intended solution is to have the chest spawn the flag by modifying the loot tables. That is actually super cool. But this is the level where I discovered the most tragic truth about Unity: Any object that needs to exist in a scene, already exists.

What does this mean? It means with Unity Explorer you can create any `GameObject` that exists within the scene already, whether or not it's active.

So how do you do this?

Open unity explorer, go to the little "Object Search" button in the Object Explorer
![Image]({{post_url}}Images/Pasted image 20240820231459.png)

Next search for a `UnityObject`, and for Name contains put: `flag`
![Image]({{post_url}}Images/Pasted image 20240820231527.png)
Immediately multiple things appear, LotteryFlag being the obvious choice.

You can now spawn the one with Type `UnityEngine.GameObject` by double clicking it and clicking "Instantiate"
![Image]({{post_url}}Images/Pasted image 20240820231632.png)
and there it is.

Now why is this forbidden? Well, simply put, this can be done in ***any*** of the levels. Yep. any of them. Repeat the steps, maybe even add `Unity.GameObject` to the filter to make it even more slim, and you'll immediately notice each flag can simply be spawned and picked up. I think this ruins the fun, so congratulations on reading this, the forbidden knowledge is now yours. To be fair during the competition, I don't think many (or any?) players abused this, mostly because it wasn't their first thought to download Unity Explorer and do it. If anything from this point onwards, they used it.
