# Level 9
Level 9 is a little race track, as explained by the horse, you have 10 seconds to get to the other side, and there is no way to beat it going "Normal speed".
![[Pasted image 20240820232714.png]]
Now there's a few ways to tackle this. I chose what I thought was the most interesting: "Dont die when the game says you "need to".

to do this, I re-opened DNSpy and quickly located `l9_finish` and `l9_timer`

Starting with `l9_time`, I quickly spotted the "KillPlayer" trigger in `trigger_game_end`
So I just made it not do that 
```C#
private void trigger_game_end() { 
    MMGameEvent.Trigger("KillPlayer");
}
```

```C#
private void trigger_game_end() { 
    return;
}
```

I figured that probably wouldn't be enough, and took a quick look at `l9_finish` Immediately there's a few methods that seem to just count coins, and compare them to if you've got them all. That's a lot of hooplah. Lets just modify `OnTriggerEnter` to always spawn the flag.
```C#
public partial class l9_finish : MonoBehaviour
{
	private void OnTriggerEnter(Collider other)
	{
		if (other.CompareTag("Player"))
		{
			if (this.gameOver)
			{
				return;
			}
			if (!this.checkGameEndRequirements())
			{
				MMGameEvent.Trigger("KillPlayer");
			}
			this.completionFeedbacks.PlayFeedbacks();
			this.gameOver = true;
			UnityEngine.Object.Instantiate<GameObject>(this.speedFlag, base.transform.position, Quaternion.identity);
		}
	}
}
```
Turns into 
```C#
public partial class l9_finish : MonoBehaviour
{
	private void OnTriggerEnter(Collider other)
	{
		if (other.CompareTag("Player"))
		{
			UnityEngine.Object.Instantiate<GameObject>(this.speedFlag, base.transform.position, Quaternion.identity);
		}
	}
}
```

After these quite easy changes, which were just removing code, I should be good to take a brisk walk to the finish.
![[Pasted image 20240820232558.png]]
This flag also doesn't disappear for whatever reason, whatever!

`GHCTF{zoom_zoom_money_maker}`

Now all the levels are done, right? [Level10](Level10.md)

Another Note: The intended solution is a speedhack. You can do this in the inspector by finding your "PoCChar" (Proof of Concept Character) which is your actual character, and inspecting it, then going into `MoreMountains.TopDownEngine.CharacterRun` (It's more controllable if you do run) then changing the value of `CharacterRun.RunSpeed` to just like, a high number, after doing this, just run the track! Remember to press shift!