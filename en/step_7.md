## High score

Let's save the high score, so that you can play against your friends.



+ Add 2 new variables to your project, called `high score`{:class="blockdata"} and `name`{:class="blockdata"}.

+ If ever the game ends (by pressing the wrong button), you need to check whether the player's score is higher than the current high score. If it is, you need to save the score as the high score, and store the name of the player. Here's how your red button should look:

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

+ You'll need to add this new code to the other 3 buttons too! Have you noticed that the 'Game over' code in each of the 4 buttons is exactly the same?

	![screenshot](images/colour-same.png)

+ If ever you need to change any of this code, such as adding a sound or changing the 'Game over!' message, you'd have to change it 4 times! That could get annoying, and waste a lot of time.

	Instead, you can define your own blocks, and reuse them in your project! To do this, click `more blocks`{:class="blockmoreblocks"}, and then 'Make a block'. Call this new block 'Game over'.

	![screenshot](images/colour-more.png)

+ Add the code from the `else`{:class="blockcontrol"} block from the red button to the new block that appears:

	![screenshot](images/colour-make-block.png)

+ You've now made a new _function_ called `Game over`{:class="blockmoreblocks"}, which you can use anywhere you like. Drag your new `Game over`{:class="blockmoreblocks"} block onto the 4 scripts for the buttons.

	![screenshot](images/colour-use-block.png)

+ Now add a sound for when the wrong button is pressed. You only need to add this code _once_ in the `Game over`{:class="blockmoreblocks"} block that you made, and not 4 separate times!

	![screenshot](images/colour-cough.png)

