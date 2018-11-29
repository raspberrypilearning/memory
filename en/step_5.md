## Multiple levels

So far, the player only has to remember a sequence of five colours. Improve your game by adding a score, and adding code so that as the player scores points, the game moves to the next level and the colour sequence to remember becomes longer.

--- task ---
Create a new variable called `score`{:class="blockdata"}.

[[[generic-scratch-add-variable]]]
--- /task ---

Based on the `score`{:class="blockdata"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

--- task ---
Add a block at the start of your character's `when flag clicked`{:class="blockevents"} code to set the `score`{:class="blockdata"} to `3`.
--- /task ---

Instead of always creating a sequence of five colours, you now want the `score`{:class="blockdata"} to determine the sequence length.

--- task ---
Change the character's `repeat`{:class="blockcontrol"} loop (for creating the colour sequence) to repeat `score`{:class="blockdata"} times:

![sprite](images/ballerina.png)
```blocks
repeat (score)
end
```
--- /task ---

--- task ---
If the player repeats the correct sequence, you should add `1` to `score`{:class="blockdata"}, and doing so increases the length of the next sequence. Add the following block to the character's code __at the point you know the sequence is correct__:

![sprite](images/ballerina.png)
```blocks
change [score v] by (1)
```

--- hints ---
--- hint ---
You know the sequence is correct at the point when the game `broadcasts`{:class="blockevents"} the 'win' message.
--- /hint ---
--- /hints ---

--- /task ---

--- task ---
Finally, add a `forever`{:class="blockcontrol"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks
when flag clicked
set [score v] to [3]
forever
	delete (all v) of [sequence v]
	repeat (score)
		add (pick random (1) to (4)) to [sequence v]
		switch costume to (item (last v) of [sequence v]
		wait (1) secs
	end
	wait until < (length of [sequence v]) = [0]>
	broadcast [won v] and wait
	change [score v] by (1)
end
```
--- /task ---

--- task ---
Get your friends to test out your game. Remember to hide the `sequence`{:class="blockdata"} list before they play it!
--- /task ---
