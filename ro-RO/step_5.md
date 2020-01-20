## Nivele multiple

Până în prezent, jucătorul trebuie doar să-și amintească o secvență de cinci culori. Îmbunătățiți-vă jocul prin adăugarea unui scor și adăugând un cod, astfel încât, în timp ce jucătorul să înscrie puncte, jocul trece la nivelul următor și secvența de culori pe care trebuie să o memoreze devine mai lungă.

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
repetare (scor :: variabile)
sfârșit
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
schimba [scorul v] de către (1)
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
când flag apasat
set [scor v] până la [3]
pentru totdeauna
    șterge (toate v) din [secvență v]
    repeat (scor)
        add (alege aleator (1) la (4)) la [secvență v]
        costum comutator la (elementul (lungimea secvenței v)) a secvenței v
        așteptați 1 secunde
    sfârșitul
    așteptați până la < (lungimea secvenței v) = [0]>
    difuzați (câștigați v) și așteptați
    schimbați [ scor v] de (1)
sfarsit
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---