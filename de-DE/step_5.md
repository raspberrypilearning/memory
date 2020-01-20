## Mehrere Level

Bisher muss sich der Spieler nur 5 Farben merken. Lass uns Dein Spiel verbessern, so dass die Länge der Farbsequenz erhöht wird. Verbessere dein Spiel, indem du Punkte hinzufügst und Code, der dafür sorgt, dass der Spieler zum nächsten Level gelangt und die Farbsequenz länger wird, wenn er genug Punkte gesammelt hat.

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
wiederhole (Punktzahl :: variables) mal
end
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
ändere [Punktzahl v] um (1)
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
Wenn die grüne Flagge angeklickt
setze [Punktzahl v] auf [3]
wiederhole fortlaufend 
    lösche (alles v) aus [Sequenz v]
    wiederhole (Punktzahl) mal 
        füge (Zufallszahl von (1) bis (4)) zu [Sequenz v] hinzu
        wechsle zu Kostüm (Element (Länge von [Sequenz v]) von [Sequenz v])
        warte (1) Sekunden
  end
    warte bis <(Länge von [Sequenz v]) = [0]>
    sende (gewonnen v) an alle und warte
    ändere [Punktzahl v] um (1)
end
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---