## High score

Let's save the high score, so that you can play against your friends.


--- task ---
Add two new variables called `high score`{:class="blockdata"} and `name`{:class="blockdata"} to your project.
--- /task ---

When the game ends because the player got the sequence wrong, you need to check whether their score is higher than the current high score. If it is, you need to save the score as the high score, and store the name of the player.

--- task ---
Add code to your character sprite to store the high score. Also ask the player their name and record it in the `name`{:class="blockdata"} variable.

[[[generic-scratch-high-score]]]

--- hints ---
--- hint ---
Your new code needs to follow this logic:
After the `Game over`{:class="blocklooks"} message
`If`{:class="blockcontrol"} the `score`{:class="blockdata"} is `greater than`{:class="blockoperators"} the `high score`{:class="blockdata"}
`Set`{:class="blockdata"} the `high score`{:class="blockdata"} to the `score`{:class="blockdata"}
`Ask`{:class="blocksensing"} the player's name
`Set`{:class="blockdata"} the `name`{:class="blockdata"} to the `answer`{:class="blocksensing"}
--- /hint ---
--- hint ---
You will need the following blocks:

![ballerina](images/ballerina.svg)

```blocks
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```
--- /hint ---
--- hint ---
Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.svg)

```blocks
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
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
--- /task ---

You'll need to add this new code to the character sprite for the other three colours too! Have you noticed that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.svg)

```blocks
say [Game over!] for (1) secs
if < (score) > (high score) > then
	set [high score v] to (score)
	ask [High score! What is your name?] and wait
	set [name v] to (answer)
end
stop [all v]
```

If you ever needed to change any of this code, for example to add a sound or change the 'Game over' message, you'd have to change it four times. That could get annoying, and waste a lot of time.

Instead, you can define your own blocks, and reuse them in your project.

--- task ---
Click `More blocks`{:class="blockmoreblocks"}, and then **Make a block**. Call this new block 'Game over'{:class="blockmoreblocks"}.

![ballerina](images/ballerina.svg)

```blocks
define Game over
say [Game over!] for (1) secs
if < (score) > (high score) > then
	set [high score v] to (score)
	ask [High score! What is your name?] and wait
	set [name v] to (answer)
end
stop [all v]
```
--- /task ---
--- task ---
Add the code from the `else`{:class="blockcontrol"} block connected to the red button to the block you've created:

![ballerina](images/ballerina.svg)

```blocks
define Game over
say [Game over!] for (1) secs
if < (score) > (high score) > then
	set [high score v] to (score)
	ask [High score! What is your name?] and wait
	set [name v] to (answer)
end
stop [all v]

when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Game over
end
```
--- /task ---

--- task ---
You've now made a new _function_ called `Game over`{:class="blockmoreblocks"}, which you can use anywhere you like. Drag your new `Game over`{:class="blockmoreblocks"} block onto the four scripts for the buttons.
--- /task ---

--- task ---
Now add a sound for when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="blockmoreblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.svg)

```blocks
define Game over
play sound [cough-female v]
say [Game over!] for (1) secs
if < (score) > (high score) > then
	play sound [trumpet1 v]
	set [high score v] to (score)
	ask [High score! What is your name?] and wait
	set [name v] to (answer)
end
stop [all v]
```
--- /task ---
