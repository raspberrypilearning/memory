## Multiple levels

So far, the player only has to remember 5 colours. Let's improve your game, so that the length of the sequence increases.



+ Create a new variable called `score`{:class="blockdata"}.

	![screenshot](images/colour-score.png)

+ This `score`{:class="blockdata"} will be used to decide on the length of the sequence the player has to memorise. So, to begin with the score (and the sequence length) is 3. Add this code block to the start of your character's `when flag clicked`{:class="blockevents"} code:

	```blocks
		set [score v] to [3]
	```

+ Instead of always creating a sequence of 5 colours, you now want the `score`{:class="blockdata"} to determine the sequence length. Change your character's `repeat`{:class="blockcontrol"} loop (for creating the sequence) to:

	```blocks
		repeat (score)
		end
	```

+ If the sequence is guessed correctly, you should add 1 to the score, to increase the length of the sequence.

	```blocks
		change [score v] by (1)
	```

+ Finally, you need to add a `forever`{:class="blockcontrol"} loop around the code to generate the sequence, so that a new sequence is created for each level. This is how your character's code should look:

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

+ Get your friends to test out your game. Remember to hide the `sequence`{:class="blockdata"} list before they play it!



