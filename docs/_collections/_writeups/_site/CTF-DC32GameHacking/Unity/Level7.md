# Level 7
Immediately after entering Level 7 I am told that I'm cheating! The agony! The horror!
![[Pasted image 20240820222107.png]]

Well the game crashed itself, so that saves me a step at least.

Immediately I go into DNSpy to see what this "anticheat" is really doing, which is found in the "anticheat" script/class.

Looks like there's some CodeHash checking & a list of "known cheat tools"
![[Pasted image 20240820222227.png]]

Normally, I'd just wipe these out, but I think I can do one more better.

If you didn't know the Unity `MonoBehavior` scripts rely on a set of built in methods that the Unity engine looks for to do things by itself, `Start` and `Update` being some of the most used. without these methods, other scripts would have to call out to an instantiated `GameObject` containing the script as a component. This means our anticheat script will more than likely be rendered useless by simply removing any `MonoBehavior` methods that it may use, so I wipe out `Start` and `Update`. This approach assumes that the `anticheat` class/script relies solely on itself, however. 

After doing that, I just relaunch the game and finally get to look at the stage.

![[Pasted image 20240820222842.png]]

Sweet! Now lets play the game and find out what this is.

![[Level7Game.gif]]

Turns out I am not that fast at shooting, I'm not sure you're intended to even do that yourself! Well at least I know now the game is pretty much Wac-a-mole. Which reminded me of a script I saw in DNSpy! `wackamole`

This one is quite long, the most notable pieces being a little method called `CheckWin` It seems like you have to hit *every* mole to win, preposterous! Lets even out the odds.

```
if (this.spawnCount == this.killCount && this.spawnCount != 0)
```
Changed to
```
if (true)
```

That should do the trick!

![[Level7GameComplete.gif]]

Well that was fun, lets pick up the flag:

`GHCTF{nice_shooting_tex}`

and continue to [Level 8](Level8.md)

Note: I did hear a fun/novel solution would be to create a little aimbot that can do this for you, that was way beyond my depth (still kind of is!) and would require creating scripts. I opted for the easy road.