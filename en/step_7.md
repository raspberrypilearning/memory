## High score

Let's save the high score, so that you can play against your friends.

+ Add two new variables to your project, called `high score`{:class="blockdata"} and `name`{:class="blockdata"}.

When the game ends because the player got the sequence wrong, you need to check whether the player's score is higher than the current high score. If it is, you need to save the score as the high score, and store the name of the player.

+ Add code inside your character sprite to store the high score. Also ask the player their name and record it in the `name`{:class="blockdata"} variable.

[[[generic-scratch-high-score]]]

--- hints ---
--- hint ---
After the "Game over" message:
**If** the **score** is **greater than** the **high score**
**Set** the **high score** to the **score**
**Ask** the player's name
**Set** the **name** to the **answer**
--- /hint ---
--- hint ---
You will need the following blocks:

![Hint for high score](images/hint-high-score.png)

--- /hint ---
--- hint ---
Here's how your code should look for when the red button is pressed:

```blocks
	when I receive [red v]
	if <(item (1 v) of [sequence v])=[1]> then
		delete (1 v) of [sequence v]
	else
		say [Game over!] for (1) secs
		if < (score) > (high score) > then
			set [high score v] to (score)
			ask [High score! What is your name?] and wait
			set [name v] to (answer)
		end
		stop [all v]
	end
```
--- /hint ---
--- /hints ---

+ You'll need to add this new code to the character sprite for the other three colours too! Have you noticed that the 'Game over' code for each of the four colours is exactly the same?

![screenshot](images/colour-same.png)

If you ever needed to change any of this code, such as adding a sound or changing the 'Game over!' message, you'd have to change it four times. That could get annoying, and waste a lot of time.

Instead, you can define your own blocks, and reuse them in your project. To do this, click `more blocks`{:class="blockmoreblocks"}, and then 'Make a block'. Call this new block 'Game over'.

![screenshot](images/colour-more.png)

+ Add the code from the `else`{:class="blockcontrol"} block from the red button to the new block that appears:

![screenshot](images/colour-make-block.png)

+ You've now made a new _function_ called `Game over`{:class="blockmoreblocks"}, which you can use anywhere you like. Drag your new `Game over`{:class="blockmoreblocks"} block onto the four scripts for the buttons.

![screenshot](images/colour-use-block.png)

+ Now add a sound for when the wrong button is pressed. You only need to add this code _once_ in the `Game over`{:class="blockmoreblocks"} block that you made, and not four separate times!

![screenshot](images/colour-cough.png)
