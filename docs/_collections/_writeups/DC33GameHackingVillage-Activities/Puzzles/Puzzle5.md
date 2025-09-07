---
layout: default
title: DC33 Game Hacking Puzzle 5
---

## Puzzle 5

This puzzle is (as stated on the monitor) a bit of an intermission. I wanted to show off an optional funtionality of CC Turtles that allows it to interact with a lever. This is configured with a datapack and is a quite interesting feature, as most mods use configs, rather than datapacks for this. Minimal versions of datapacks can be made at this link: https://datapacks.madefor.cc/

I'd recommdn checking out the datapacks and what they're capable of. This one leverages the turtles using levers function. The only catch with Turtles using levers is that the turtle must be holding an item in its active slot in order to flip the lever, which is told on the screen. The intention is using functionality from Puzzle 3 to grab this item.

![Puzzle 5]({{post_url}}Images/Puzzle5.png)

![Puzzle 5 Screen]({{post_url}}Images/Puzzle5Screen.png)

## Solution

```lua
turtle.suckUp()
for i=1, 5 do
    turtle.forward()
end
turtle.place()
```

[Next Puzzle](Puzzle6)
