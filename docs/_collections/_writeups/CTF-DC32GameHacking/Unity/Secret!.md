---
title: Secret!
layout: default
---
There's a secret flag! I found it.

Where was it, Secret!

Just kidding, it was on the main menu, where? Open the inspector...
![Image]({{post_url}}Images/Pasted image 20240820234715.png)

First, inspect the suspiciously `Flag` named object, then the `UI.Text` element, finally, there's an element inside of it called `text` which contains:

`GHCTF{I_guess_it_was_not_that_hidden}`

Yep. That was it (I spent about 2 hours on this 

BTW the intended solution was to run strings against the program files and grep for `GHCTF`.
