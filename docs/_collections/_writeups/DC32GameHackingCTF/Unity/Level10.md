# Level 10
Level 10 is actually the easiest level if you've progressed linearly up to this point.

Assuming UnityExplorer is already installed, open the game, go to the menu and in the Object Explorer, you can use the box at the bottom that says `[Select a scene]`, this dropdown should have `Scene 10: hidden`, just click it and click `Load (Single)`

From here you should see a chest that is open with an "E" prompt. It has the `chest` script on it. And doesn't open whenever you try to activate it.
![[Pasted image 20240820233745.png]]

I wrote a weird solution to this completely on accident while trying to solve Level 8, in DNSpy I modified the chest class with the following:
```C#
public void Awake()
{
    this.chestObj.SetActive(false);
	this.completionFeedbacks.PlayFeedbacks();
	UnityEngine.Object.Instantiate<GameObject>(this.hiddenFlag, base.transform.position, Quaternion.identity);
}
```

To quickly explain this: `Awake` is a `MonoBehavior` method that is called whenever an object "Wakes up" as in, when it is created within the scene. Since the chest is created on scene load, it will do what is inside of the method. The contents are ripped straight out of `OpenChest` and should just de-spawn the chest, and spawn the flag. I figured this would solve Level 8 before I even knew it didn't use the `Chest` script, lucky for me this one does.

![[Pasted image 20240820233613.png]]

`GHCTF{well_played_hacker_gg}`

And that's the [end](Secret!.md) of the main-level challenges of this segment of the CTF. Learning these was a LOT of fun, and I had a decent amount of difficulty in the start. Discounting the [Forbidden Strategy](Level8#Unintended Solution (forbidden strategy))

Anyhow, thanks for reading my writeups on the Unity section! I tried to make them a little more flowing towards how I was thinking, and tried to explain the things I did and why. I have a more personal style of writing because I think just going through things mechanically gets quite boring quite quickly. Hopefully that came off in the writing, or it didn't. 