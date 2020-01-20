## Meerdere levels

Tot nu toe hoeft de speler maar een reeks van vijf kleuren te onthouden. Verbeter je spel door een score toe te voegen en code toe te voegen, zodat wanneer de speler punten scoort, het spel naar het volgende niveau gaat en de te onthouden kleurenreeks langer wordt.

\--- task \---

Create a new variable called `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \---

Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`.

\--- /task \---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \---

Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
herhaal (score)
einde
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
verander [score v] met (1)
```

\--- hints \---

\--- hint \---

You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks3
wanneer groene vlag wordt aangeklikt
maak [score v] [3]
herhaal 
  verwijder (alle v) van [reeks v]
  herhaal (score)
    voeg (willekeurig getal tussen (1) en (4)) toe aan [reeks v]
    verander uiterlijk naar (item (lengte van [reeks v]) van [reeks v]
    wacht (1) sec.
  einde
  wacht tot <(lengte van [reeks v]) = [0]>
  zend signaal (gewonnen v) en wacht
  verander [score v] met (1)
einde
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---