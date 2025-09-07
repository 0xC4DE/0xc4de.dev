---
layout: default
title: DC33 Game Hacking Puzzle 6
---

## Puzzle 6

Puzzle 6 is intended to show off the placing functionality of a turtle, The movement part of the turtle is more of a given, and the focus is more on how to manipulate the item frames without breaking them.

![Puzzle 6]({{post_url}}Images/Puzzle6.png)

![Puzzle 6 Screen]({{post_url}}Images/Puzzle6Screen.png)

## Solution

```lua
turtle.turnRight()
turtle.suck()
turtle.turnLeft()
turtle.up()
for i=1, 5 do
    turtle.place()
    turtle.turnRight()
    turtle.forward()
    turtle.turnLeft()
end
```

[Next Puzzle](Puzzle7)
