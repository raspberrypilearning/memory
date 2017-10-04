## Repeating the sequence

Let's add 4 buttons, for the player to repeat the sequence they've remembered.

+ Add 4 sprites to your project, that will become buttons. Edit your 4 sprites, so that there's 1 for each of the 4 colours.

	![screenshot](images/colour-drums.png)

+ When the red drum is clicked, you'll need to broadcast a message to your character, letting them know that the red button has been clicked. Add this code to your red drum:

	```blocks
		when this sprite clicked
		broadcast [red v]
	```

+ When your character receives this message, they should check whether the number 1 is at the start of the list (which means that red is the next colour in the sequence). If it is, you can remove the number from the list, as it's been guessed correctly. Otherwise it's game over!

	```blocks
		when I receive [red v]
		if <(item (1 v) of [sequence v])=[1]> then
			delete (1 v) of [sequence v]
		else
			say [Game over!] for (1) secs
			stop [all v]
		end
	```

+ You could also display some flashing lights once the list is empty, as it means the entire sequence has been guessed correctly. Add this code to the end of your character's `when flag clicked`{:class="blockevents"} script:

	```blocks
		wait until < (length of [sequence v]) = [0]>
		broadcast [won v] and wait
	```

+ Click on your stage, and add this code to play __any__ sound and make the backdrop change colour once the player has won.

	```blocks
		when I receive [won v]
		play sound [drum machine v]
		repeat (50)
			change [color v] effect by (25)
			wait (0.1) secs
		end
		clear graphic effects
	```
