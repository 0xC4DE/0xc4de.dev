---
layout: default
title: DC33 Game Hacking Puzzle 8
---

## Puzzle 8

This puzzle expands further on the manipulation of items, the catch is that you have to search for the terracotta that is the right color. The screen describes this process briefly, with a description of how to do the search. It also recommends replicating the puzzle in a test world, if somebody hasn't already.

I noticed that most people ended up working around this puzzle by breaking the barrier and looking at the order of blocks.

![Puzzle 8]({{post_url}}Images/Puzzle8.png)

![Puzzle 8 Screen]({{post_url}}Images/Puzzle8Screen.png)


## Solutions

This solution uses a map in order to store the location of each block in the turtle's inventory. it's fairly simple, even though the length of this solution isn't exactly small.

```lua
turtle.turnRight()

-- This works because it just populates the inventory
for i=1, 6 do
    turtle.suck()
end

-- We know there's 6 slots occupied because there's 6 blocks (told by the board)
local colors = {"red", "green", "purple", "yellow", "orange", "cyan"}
local colorSlots = {nil, nil, nil, nil, nil, nil}

-- This isn't something I expect somebody to come up with, I expect an IF tree
for slot=1, #colors do
    for i=1, #colors do -- 1 to 6, because colors is 6 long
        if string.find(turtle.getItemDetail(slot).name, colors[i]) then
            colorSlots[i] = slot
        end
    end
end

-- There's better ways to sequence this like with some sort of instruction interpreter.
turtle.turnLeft()
turtle.forward()
turtle.select(colorSlots[2]) -- green
turtle.drop()
turtle.up()
turtle.up()
turtle.select(colorSlots[1]) -- red
turtle.drop()
turtle.turnRight()
turtle.forward()
turtle.forward()
turtle.forward()
turtle.turnLeft()
turtle.select(colorSlots[3]) -- purple
turtle.drop()
turtle.down()
turtle.down()
turtle.select(colorSlots[4]) -- yellow
turtle.drop()
turtle.turnRight()
turtle.forward()
turtle.forward()
turtle.forward()
turtle.turnLeft()
turtle.select(colorSlots[6]) -- cyan
turtle.drop()
turtle.up()
turtle.up()
turtle.select(colorSlots[5]) -- orange
turtle.drop()
```