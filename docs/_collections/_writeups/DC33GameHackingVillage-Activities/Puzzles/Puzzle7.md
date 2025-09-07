---
layout: default
title: DC33 Game Hacking Puzzle 7
---

## Puzzle 7

Puzzle 7 is where I started trying to come up with new ideas. I was inspirted by the idea of a redstone puzzle, but because there's no clean way to make a turtle solve a puzzle, I settled for a series of pistons pushing a redstone block. This basically is just vanilla piston mechanics with some very simple redstone.

![Puzzle 7]({{post_url}}Images/Puzzle7.png)

![Puzzle 7 Screen]({{post_url}}Images/Puzzle7Screen.png)

## Solution

This solution is quite lengthy for no particular reason. It leverages the fact that you can call the output once, another alternative is to rebind `turtle.up()` and `turtle.forward()` in order to "sequence" the instructions, but this solution is the most straightforward and easy way.

```lua
-- The trick here is that the turtle can constantly output a signal, so you can call this once
redstone.setOutput("right", true)
turtle.turnLeft()
turtle.up()
turtle.up()
turtle.forward()
turtle.forward()
turtle.forward()
turtle.up()
turtle.up()
turtle.up()
turtle.forward()
turtle.forward()
turtle.back()
turtle.down()
turtle.down()
turtle.forward()
turtle.forward()
turtle.up()
turtle.up()
turtle.down()
turtle.down()
turtle.forward()
turtle.forward()
turtle.back()
turtle.up()
turtle.up()
turtle.down()
turtle.down()
```

[Next Puzzle](Puzzle8)