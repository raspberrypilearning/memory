## Multiple levels

So far, the player only has to remember a sequence of five colours. Let's improve the game by adding a score, and adding code so that as the player's score increases, the length of the sequence they have to remember becomes longer.

+ Create a new variable called `score`{:class="blockdata"}.

[[[generic-scratch-add-variable]]]

The `score`{:class="blockdata"} will be used to decide on the length of the sequence the player has to memorise. Let's start with a score (and a sequence length) of `3`.

+ Add a block at the start of your character's `when flag clicked`{:class="blockevents"} code to set the `score`{:class="blockdata"} to `3`.

Instead of always creating a sequence of five colours, you now want the `score`{:class="blockdata"} to determine the sequence length.

+ Change the character's `repeat`{:class="blockcontrol"} loop (for creating the sequence) to repeat `score`{:class="blockdata"} times:

```blocks
    repeat (score)
    end
```

+ If the sequence is guessed correctly, you should add `1` to the score to increase the length of the next sequence. Add this block to the character's code **at the point you know the sequence was guessed correctly**.

```blocks
    change [score v] by (1)
```

\--- hints \--- \--- hint \--- You know the sequence was guessed correctly at the point you broadcast the `win` message. \--- /hint \--- \--- /hints \---

+ Finally, you need to add a `forever`{:class="blockcontrol"} loop around the code which generates the sequence, so that a new sequence is created for each level. This is how your character's code might look:
    
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