\--- challenge \---

## Challenge: adding sound

Test your project a few times. You may notice that sometimes the same number is chosen twice (or more) in a row, making the sequence harder to memorise. Can you make a drum sound play each time the character changes costume?

Can you make a different drum sound play depending on which number was chosen? This will be *very* similar to your code to change the character's costume.

\--- hints \--- \--- hint \--- You can complete this challenge by adding just two blocks to your character's current code! \--- /hint \--- \--- hint \--- Here are the blocks you will need:

![Hint drum blocks](images/hint-drumblocks.png) \--- /hint \---

\--- hint \--- Here is how your finished code should look:

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

\--- /hint \---

\--- /hints \---

\--- /challenge \---