## Repeating the sequence

Let's add four buttons for the player to press to repeat the sequence they've remembered.

--- task ---
+ Add four new sprites to your project to represent the four buttons. Edit the costumes so that there is one sprite in each of the four colours. Lay out the sprites in the same order as the costumes — red, blue, green, yellow.

![screenshot](images/colour-drums.png)
--- /task ---

--- task ---
+ When the red drum is clicked, you'll need to broadcast a message to your character, letting them know that the red button has been clicked. Add this code to your red drum:

![red-drum](images/red_drum.svg)

```blocks
	when this sprite clicked
	broadcast [red v]
```
--- /task ---

A broadcast is a bit like making an announcement over a loudspeaker — you might have heard this when you are shopping in the supermarket. All of the sprites can hear the message, but only the sprite whose job it is to respond will do something.

--- task ---
+ Add similar code to the blue, green, and yellow drums to make them broadcast messages about their own colour.

--- hints ---
--- hint ---
Here is an easy way to copy the code from one sprite to another. Change the broadcast message in each sprite to match the colour of the sprite.
![Duplicate the code](images/broadcast-duplicate.gif)
--- /hint ---
--- /hints ---

--- /task ---

Remember we said that the broadcast was a bit like making an announcement over a loudspeaker? Only the sprite whose job it is to respond will do something, so let's make it the character sprite's job to respond to the messages. We do this by writing some code for the character to do when they hear each message.

--- task ---
 + When your character sprite receives the message `red`, the code should check whether the number `1` is at the start of the list (which means that `red` is the next colour in the sequence).

 If it is, the code should remove the number from the list, as the colour was guessed correctly. Otherwise it's game over, and we need to `stop all`{:class="blockcontrol"} to stop the game.

![ballerina](images/ballerina.svg)

```blocks
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
delete (1 v) of [sequence v]
else
say [Game over!] for (1) secs
stop [all v]
end
```
--- /task ---

+ Add to the code you just wrote so that a drum beat also plays when the correct colour is received.

--- hints ---
--- hint ---
Can you use the numbers that correspond to each colour to play the correct drum beat?
+ 1 = red
+ 2 = blue
+ 3 = green
+ 4 = yellow
--- /hint ---
--- hint ---
You will need to add the `play drum`{:class="blocksound"} block to play the first sound in the sequence list before `delete 1 of sequence`{:class="blockdata"}:

![Play drum](images/hint-play-drum.png)
--- /hint ---
--- hint ---
Here is the code you will need to add:

```blocks
play drum (item (1 v) of [sequence v]) for (0.25) beats
```
--- /hint ---
--- /hints ---

+ Duplicate the code you used to make your character sprite respond to the message `red`. This time, change the message to `blue`.

When the sprite responds to the message `blue`, which bit of code should stay the same, and which bit should change? Remember that each colour has a corresponding number.

+ Change your code so that the character responds correctly to the `blue` message.

--- hints ---
--- hint ---
Keep these blocks, but you will need to change them in some way:
![Change these blocks](images/hint-change-blocks.png)
--- /hint ---
--- hint ---
Here is how your code should look for the blue broadcast.

```blocks
	when I receive [blue v]
	if <(item (1 v) of [sequence v])=[2]> then
        play drum (item (1 v) of [sequence v]) for (0.25) beats
		delete (1 v) of [sequence v]
	else
		say [Game over!] for (1) secs
		stop [all v]
	end
```

--- /hint ---
--- /hints ---

+ Duplicate the code again twice for the green and yellow buttons, and change the necessary parts so that the character responds correctly.

+ Remember to test the code you've added! Can you memorise a sequence of five colours? Is the sequence different each time?

You could also display some flashing lights as a reward once the list is empty, as that means the entire sequence was memorised correctly.

+ Add this code to the end of your character's `when flag clicked`{:class="blockevents"} script:

```blocks
	wait until < (length of [sequence v]) = [0]>
	broadcast [won v] and wait
```

+ Switch to the stage, and add this code to play a sound and make the backdrop change colour once the player has won. You can choose any sound you like.

```blocks
	when I receive [won v]
	play sound [drum machine v]
	repeat (50)
		change [color v] effect by (25)
		wait (0.1) secs
	end
	clear graphic effects
```
