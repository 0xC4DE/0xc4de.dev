---
layout: default
title: DC33 Game Hacking Puzzle 2
---

## Puzzle 2

Puzzle 2 is another simple puzzle, all you're doing is moving forward, like before the only change here is that you also need to turn right. The goal with this one is just as basic as the last, get some familiarity with the API and provide a easy on-ramp with the turtle API.

![Puzzle 2]({{post_url}}Images/Puzzle2.png)

![Puzzle 2 Screen]({{post_url}}Images/Puzzle2Screen.png)


## Solution

Note: This solution uses a loop which isn't formally introduced in the puzzle, but is less lines of code, which is why I used it (this will not be a recurring theme for my solutions)
```lua
for i=1, 5 do
    turtle.forward()
end
turtle.turnRight()
turtle.forward()
turtle.forward()
```

[Next Puzzle](Puzzle3)