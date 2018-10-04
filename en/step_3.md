## Adding sound

--- task ---
Test your project a few times. You may notice that sometimes the same number is chosen twice (or more) in a row, making the sequence harder to memorise. Can you make a drum sound play each time the character changes costume? How about a different drum sound play depending on which number was chosen? This will be _very_ similar to your code to change the character's costume.


--- hints ---
--- hint ---
You can complete this challenge by adding just two blocks to your character's current code! You'll need a `play drum for (0.25) beats`{:class="blocksound"} and a `item (last) of sequence`{:class="blockdata"}
--- /hint ---
--- hint ---
Here are the blocks you will need:

![ballerina](images/ballerina.svg)

```blocks
play drum (10 v) for (0.25) beats

item (last v) of [sequence v]
```
--- /hint ---

--- hint ---
Here is how your finished code should look:

![ballerina](images/ballerina.svg)

```blocks
when flag clicked
delete (all v) of [sequence v]
repeat (5)
	add (pick random (1) to (4)) to [sequence v]
    play drum (item (last v) of [sequence v]) for (0.25) beats
    switch costume to (item (last v) of [sequence v])
    wait (1) secs
end
```
--- /hint ---

--- /hints ---

--- /task ---
