## Random colours

First, let's create a character who will display a random sequence of colours for the player to memorise.

+ Start a new Scratch project, and delete the cat sprite so that your project is empty. You can find the online Scratch editor at [http://jumpto.cc/scratch-new](http://jumpto.cc/scratch-new).

+ Choose a character and a backdrop. Your character doesn't have to be a person, but it needs to be able to show different colours.

![screenshot](images/colour-sprite.png)

+ In your game, you'll use a different number to represent each colour:

	+ 1 = red;
	+ 2 = blue;
	+ 3 = green;
	+ 4 = yellow.

	Give your character four different coloured costumes, one for each of the four colours above. Make sure that your coloured costumes are in the same order as the list above.

	![screenshot](images/colour-costume.png)

Let's create a random sequence of colours.

+ Create a list called `sequence`{:class="blockdata"}. This is where you will store the random sequence. Only the character sprite needs to see the list, so you can select 'For this sprite only'.

[[[generic-scratch-make-list]]]

You should now see your empty list in the top-left of your stage, as well as lots of new blocks for using lists.

![screenshot](images/colour-list-blocks.png)

+ Add this code to your character, to add a random number to your list (and show the correct costume) 5 times:

```blocks
	when flag clicked
	delete (all v) of [sequence v]
	repeat (5)
		add (pick random (1) to (4)) to [sequence v]
		switch costume to (item (last v) of [sequence v]
		wait (1) secs
	end
```

Notice that you have also emptied the list to begin with.
