---
layout: default
title: DC33 GHV Minecraft Activity
---

# DC33 Minecraft Puzzle Activity

The goal of this activity was to intruduce people to writing lua with an easier to digest tutorial. Although they would be working directly with libraries in Computer Craft, there's a ton of transferrable skill, mostly in raw exposure to the language and using the libraries that are provided to computer craft.

This section discusses the intentions of my design of the puzzles/map and a few details about how I think the activity went.

## The Rewards

The original intention is that the first solo, then team solver would get a solver badge (see: badges FIXME badges link) then there were two activities that involved creating an overly complicated/overengineered solution, then code golf. The complicated one was purely subjective, I would judge it based upon sheer complication. The golf one is much simpler, the shortest wins.

Because Hacker v Hacker didn't pick up enough traction, several solo winners of the Minecraft activity got badges instead, I cannot remember specific numbers; however, around six people got badges in total. Congratulations to them!

Apart from that, anybody who at least got Minecraft running eventually got a turtle coin (FIXME: turtle coin picture) it has a little secret, if you have one and are reading this ;) good luck

## The Purpose 

As mentioned previously the purpose of this activity/map was to expose people to Computer Craft & LUA, as well as serve as a little modding activity for Minecraft. Downloading the activity in general required using [Prism Launcher](https://prismlauncher.org/), which is one of the most popular launcher for modded minecraft and modpacks as a whole. There's a whole specled history of mod launchers, and this one has shown for quite the while to have the best support. I'll leave the history lesson as extra credit for whoever is reading this.

The overall hope of the map was to encourage people to look deeper into Minecraft Modding, as it is something that is important to me, Hello MeatballCraft! I was hoping that some people would flex some Minecraft cheats and shortcut to the final puzzle, and solve it immediately. Unfortunately most, if not all of the participants were rule followers and simply solved the puzzles with the real solutions.

Speaking of the puzzles, they were meant to be somewhat incremental and flex some of the capabilities of the turtle. Some ideas had to be thrown out because of clunky solutions or overly complicated puzzle implementations. Some of the limitations of Minecraft itself were most of the obstacles, as I didn't want to implement puzzle generation algorithms inside of the command computers (the ones that controlled the puzzles) themselves.

## The Design

So I will briefly discuss the design of the map, or rather how everything is controlled. 

It all starts with the pocket computer/tablet. This thing has a modem attached to it by default, which allows you to connect to [rednet](https://tweaked.cc/module/rednet.html), a layer of abstraction of the modem protocol, which allows computers in Computer Craft to communicate with one another in a controlled manner. The raw sockets are also available through the raw modem protocol, but using that was inconvenient, so all computers used rednet.

This tablet would communicate with a central computer which allowed it to pull which puzzles have been completed, this central computer had no particuar name, but it used the `puzzleControl` protocol and registered with rednet under `controlpc`. The tablet sends a `puzzleRequest` and then a separate thread is (hopefully) already waiting for a `puzzleResponse`, which contains the completed puzzles, and updates the interface. This protocol just ensures that every time the user restarted the computer, it would recieve all the completed puzzles.

Computer Craft Computers only really have one thread. Every PC only has one thing that can run "at a time", and is controlled by a central event queue, many commands that "await" simply wait for a specific event to fire to continue. Using a specific section of code is used for that event, hence `puzzleResponse` waits in a separate section of code that `puzzleRequest` is sent, as well as the main GUI being controlled in its own library (Basalt) I wont talk about Basalt because it was used out of pure convenience, I hate making GUIs.

This event model extends to each puzzle computer, which were used for each puzzle to detect solves based upon unique conditions. They had a lot of shared code, but my code quality can be discussed in a separate paragraph (hint: it's bad.) As mentioned the puzzle computers were meant to be pretty one-shot boring machines. All they did was check puzzle completion, and when detected, they would send a request to `controlpc` letting it know to mark the puzzle as completed. This had no source protection based upon hostname, which was ***intentional***, and only had a password, the password for *every* puzzle was `supersecretpasskey`. This could be discerned by reading the datapack that was present in the world. I was hoping at least one person would realize the protocol has statically defined passwords and try to break it, there might have even been a secret badge for anybody who did that, but no dice.

Overall, this system creates a fun little ecosystem that allows for any amount of puzzles (if the GUI on the tablet allows) and doesn't completely break if the puzzle computers go offline. 

There's a good graphic on the [github](https://github.com/0xC4DE/DC33-Game-Hacking-CC-Interface/tree/main), please go read the code if you're interested! :)

## The issues

During the con, two puzzle computers didn't function properly (oops), those puzzles would be 6 and 10. The issues were that puzzle 10 did not have enough fuel to complete any solution, and puzzle 6 crashed before sending off a task complete message. this was due to GROSS tech debt leading to me missing programming errors in these two puzzle scripts. Obviously a point of improvement would be to better modularize shared code, I just didn't want to be bothered to handle imports in LUA

The world also wasn't meant to be in creative... I meant to throw people into adventure mode, but for some reason it just didn't stick. I think most people actually enjoyed being in creative because it allowed them to fly around and look at puzzles, and explore some of the eastereggs/debugging stuff I left around the map. Violating the rules is up to whoever is playing, so I ended up just letting it slide and kept the world in creative.


## The puzzles

Because this page is already getting too long, I will talk about each puzzle in their own pages, most of the insight will be surface-level, and I will provide the most simple solutions that I came up with for each.

1. [Puzzle 1](Puzzles/Puzzle1)
2. [Puzzle 2](Puzzles/Puzzle2)
3. [Puzzle 3](Puzzles/Puzzle3)
4. [Puzzle 4](Puzzles/Puzzle4)
5. [Puzzle 5](Puzzles/Puzzle5)
6. [Puzzle 6](Puzzles/Puzzle6)
7. [Puzzle 7](Puzzles/Puzzle7)
8. [Puzzle 8](Puzzles/Puzzle8)
9. [Puzzle 9](Puzzles/Puzzle9)
10. [Puzzle 10](Puzzles/Puzzle10)

[Scrapped Ideas](Puzzles/ScrappedIdeas)