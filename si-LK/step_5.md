## බහු(multiple) මට්ටම්(levels)

මෙතෙක්, ක්‍රීඩකයා මතක තබා ගත යුත්තේ වර්ණ පහක අනුක්‍රමයක්(sequence එකක්) පමණි. ලකුණු(score එකක්) ලබාගතහැකි ක්‍රමයක් ක්‍රීඩාවට එකතු කිරීමෙන් ඔබේ ක්‍රීඩාව වැඩි දියුණු කරන්න, එවිට ක්‍රීඩකයා ලකුණු ලබා ගන්නා විට, ක්‍රීඩාව ඊළඟ(next) මට්ටමට(level එකට) ගමන් කරන අතර මතක තබා ගතයුතු වර්ණ අනුක්‍රමය(sequence එක) දිගු වේ.

\--- task \--- `score`{:class="block3variables"} නමින් නව විචල්‍යයක්(variable එකක්) සාදන්න.

[[[generic-scratch3-add-variable]]] \--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \--- Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`. \--- /task \---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \--- Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

\--- /task \---

\--- task \--- If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
change [score v] by (1)
```

\--- hints \--- \--- hint \--- You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message. \--- /hint \--- \--- /hints \---

\--- /task \---

\--- task \--- Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
set [score v] to [3]
forever
    delete (all v) of [sequence v]
    repeat (score)
        add (pick random (1) to (4)) to [sequence v]
        switch costume to (item (length of [sequence v]) of [sequence v]
        wait (1) seconds
    end
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
    change [score v] by (1)
end
```

\--- /task \---

\--- task \--- Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it! \--- /task \---