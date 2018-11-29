## Add sound

--- task ---
Test your project a few times. Do you notice that sometimes the same number is chosen twice (or more) in a row, which makes the sequence harder to memorise?

Can you make a drum sound play each time the character changes costume? How about a different drum sound depending on which colour is chosen? The code you need to do this is __very__ similar to the code to change the character's costume.

--- hints ---
--- hint ---
You only need to add two blocks: a `play drum for (0.25) beats`{:class="blocksound"} block and a `item (last) of sequence`{:class="blockdata"} block.
--- /hint ---
--- hint ---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks
play drum (10 v) for (0.25) beats

item (last v) of [sequence v]
```
--- /hint ---

--- hint ---
Here is how your finished code should look:

![ballerina](images/ballerina.png)

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
