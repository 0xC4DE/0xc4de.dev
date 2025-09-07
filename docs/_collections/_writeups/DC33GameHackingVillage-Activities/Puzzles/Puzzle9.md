---
layout: default
title: DC33 Game Hacking Puzzle 9
---

## Puzzle 9

Puzzle 9 leverages the turtle's inspection ability, and forces you to use conditional logic in order to move around. The puzzle is designed in such a way that if you do take a wrong turn, you get stuck, without much feedback. Which would be an issue if somebody is earlier on, but given that most players that get to this stage would (hopefully) know how to solve it pretty quickly, I figured not adding any feedback as to whether or not the turtle was actively moving was a good enough idea.

![Puzzle 9]({{post_url}}Images/Puzzle9.png)

![Puzzle 9 Screen]({{post_url}}Images/Puzzle9Screen.png)


## Solution

```lua
-- This puzzle has several bad solutions and a couple easy/elegant ones. This is somewhere in between.
turtle.forward()

function ironBlock()
    turtle.turnRight()
    turtle.forward()
    turtle.turnLeft()
    turtle.forward()
    turtle.forward()
end

function goldBlock()
    turtle.turnLeft()
    turtle.forward()
    turtle.turnRight()
    turtle.forward()
    turtle.forward()

end

-- This loop can be run a large number of times or if the player is clever they can observe for green concrete
r, underBlock = turtle.inspectDown()
while r and underBlock.name ~= "minecraft:green_concrete" do
    ret, block = turtle.inspect()
    if block.name == "minecraft:iron_block" then
        ironBlock()
    elseif block.name == "minecraft:gold_block" then
        goldBlock()
    end
    r, underBlock = turtle.inspectDown()
end
```

[Next Puzzle](Puzzle10)