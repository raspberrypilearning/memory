## Več stopenj

Zaenkrat si mora igralec zapomniti zaporedje petih barv. Izboljšaj svojo igro, tako da dodaš točke in dodaj kode, da bo igralec, ko dobi dovolj točk, prešel na naslednjo stopnjo, na kateri si bo moral zapomniti daljše zaporedje.

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
ponovi (točke :: Spremenljivka) krat
konec
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
spremeni [točke v] za (1)
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
ko kliknemo na zastavico
nastavi [točke v] na (3)
ponavljaj
    izbriši (vse v) v [zaporedje v]
    ponovi (točke) krat
        dodaj (naključno število med (1) in (4)) k [zaporedje v]
        zamenjaj videz na (element (dolžina [zaporedje v]) v [zaporedje v]
        počakaj (1) sekund
    konec
    počakaj dokler ni < (dolžina [zaporedje v]) = (0)>
    objavi (zmaga v) in čakaj
    spremeni [točke v] za (1)
konec
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---