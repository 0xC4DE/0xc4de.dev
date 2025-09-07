---
layout: default
title: DC33 Game Hacking Puzzle 3
---

## Puzzle 3

This puzzle is the start of what I would call "pratical" turtle use-cases or applications. One of my goals with creating this activity was to show people that the turtles can do some interesting stuff in-game, and interact with containers. So, this puzzle introduces the idea of moving items and manipulating inventories. The screen has a decent description of how to ues the turtle to pull the items and drop them into chests.

Later, this concept of placing items in chests is expanded to sorting specific items into chests.

![Puzzle 3]({{post_url}}Images/Puzzle3.png)

![Puzzle 3 Screen]({{post_url}}Images/Puzzle3Screen.png)


## Solution

```lua
turtle.suck()
turtle.up()
turtle.forward()
turtle.forward()
turtle.down()
for i=1, 7 do
    turtle.forward()
end
turtle.drop()
```

[Next Puzzle](Puzzle4)