## Več stopenj

Zaenkrat si mora igralec zapomniti zaporedje petih barv. Izboljšaj svojo igro, tako da dodaš točke in dodaj kode, da bo igralec, ko dobi dovolj točk, prešel na naslednjo stopnjo, na kateri si bo moral zapomniti daljše zaporedje.

\--- task \--- Ustvari novo spremenljivko z imenom `točke`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

Glede na točke `score`{:class="block3variables"}, se bo igra odločila, kako dolgo bo zaporedje. Začni s številom točk (in dolžino zaporedja) `3`.

\--- task \--- Na začetek bloka `ko kliknemo na zastavico`v figuri tvojega lika {:class="block3events"} dodaj kodo, ki nastavi `točke`{:class="block3variables"} na `3`. \--- /task \---

Namesto tega, da vedno ustvariš zaporedje petih barv, boš sedaj uporabil-a `točke`{:class="block3variables"} za določitev dolžine zaporedja.

\--- task \--- Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![figura](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

\--- /task \---

\--- task \--- If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![figura](images/ballerina.png)

```blocks3
spremeni [točke v] za (1)
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