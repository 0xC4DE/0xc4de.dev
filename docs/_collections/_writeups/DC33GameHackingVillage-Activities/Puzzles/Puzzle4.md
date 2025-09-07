---
layout: default
title: DC33 Game Hacking Puzzle 4
---

## Puzzle 4

I will admit, puzzle 4 is a bit of a regression thematically, it is used to introduce loops in Lua. Lua has some quirks about loops, but for the purposes of this activity, I kept it simple e.g. using `for 1..10`. 

The only small catch with this one is that the amount of forwards changes every few turns, which isn't actually a concern because the program doesn't crash if it runs into a wall.

![Puzzle 4]({{post_url}}Images/Puzzle4.png)

![Puzzle 4 Screen]({{post_url}}Images/Puzzle4Screen.png)

## Solution

Also, a double loop makes this easy, too
```lua
for j=1, 5 do
    for i=1, 4 do
        turtle.forward()
    end
    turtle.turnLeft()
end
```

[Next Puzzle](Puzzle5)