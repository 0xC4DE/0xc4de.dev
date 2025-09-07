---
layout: default
title: DC33 Game Hacking Puzzle 10
---

## Puzzle 10

Puzzle 10 has no help screen, and is presented in a way that makes people assume they have to do each step to solve it. The intention was that somebody would have to do each skill that they learned throughout the entire map such as placing items in the frame, placing items in a chest, emitting a redstone signal, and placing blocks.

What ended up actually happening is that players found out they could simply activate the first piston, then emit a redstone signal into the observer, which would solve the puzzle.

This is where I reveal that this map actually had no rule of following the rules of each puzzle, and no requirement to solve puzzles 1-9 before solving puzzle 10. To solve people only needed to go to this puzzle and give me a solution. I didn't make that obvious so that people would spend more time at the village and talk to people about their solutions.

![Puzzle 10]({{post_url}}Images/Puzzle10.png)


## Solution

This solution is somewhat lengthy, the day that I wrote it I didn't really have the will to create anything less long. Plenty of poeple (shoutouts to the code-golf completion) actually had more interesting solutions. This one wasn't meant to be particularly complex other than the fact that you had multiple steps to complete.

```lua
-- This puzzle is mostly lengthy, honestly probably shorter than some others, I expect at this stage
-- Somebody would potentially make their own movement sequencer, so that they can make a string like:
-- "ffubb" for "forward forward up back back"
turtle.suckUp()
turtle.turnLeft()
turtle.forward()
turtle.turnRight()
turtle.up()
turtle.up()
turtle.forward()
redstone.setOutput("front", true) -- power the last piston
sleep(1)
turtle.down()
turtle.down()
turtle.back()
turtle.turnLeft()
turtle.forward()
turtle.forward()
turtle.turnRight()
turtle.place() -- place first block
turtle.turnLeft()
turtle.forward()
turtle.forward()
turtle.up()
turtle.turnRight()
turtle.drop(1) -- place block in chest
turtle.down()
turtle.turnLeft()
turtle.forward()
turtle.forward()
turtle.turnRight()
turtle.up()
turtle.up()
turtle.place() -- place in frame
turtle.down()
turtle.down()
turtle.turnLeft()
turtle.forward()
turtle.forward()
turtle.turnRight()
turtle.forward()
turtle.forward()
turtle.forward()
turtle.place() -- Place lever
```
