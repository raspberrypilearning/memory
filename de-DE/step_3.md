## Geräusche hinzufügen

--- task ---

Teste dein Projekt einige Male. Du stellst möglicherweise fest, dass manchmal die gleiche Zahl zweimal (oder mehrmals) nacheinander ausgewählt wird, was es schwieriger macht sich die Reihenfolge zu merken.

--- /task ---

Kannst du jedes Mal, wenn dein Charakter das Kostüm wechselt, ein Trommel-Geräusch spielen? Kannst du auch jeweils ein anderes Trommel-Geräusch spielen, abhängig von der Zufallszahl, die ausgewählt wird?

--- task ---

Füge die Musik-Erweiterung zu deinem Projekt hinzu, damit du den `Spiele-Schlaginstrument`{:class="block3extensions"} - Block nutzen kannst.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

Der Code, der die Trommel spielen lässt, ist **sehr** ähnlich zu dem Code, der für das Verändern des Kostüms des Charakters verantwortlich ist.

--- hints ---


--- hint ---

Du brauchst nur zwei Blöcke hinzufügen: einen `spiele Schlaginstrument für (0,25) Schläge`{:class="block3sound"} - Block und einen `Element (Länge von Sequenz) von Sequenz`{:class="block3variables"} - Block.

--- /hint ---

--- hint ---

Hier sind die Blöcke, die du brauchst:

![Ballerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [Sequenz v]) of [Sequenz v])
```

--- /hint ---

--- hint ---

So sollte dein fertiger Code aussehen:

![Ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [Sequenz v]
repeat (5)
	add (pick random (1) to (4)) to [Sequenz v]
    play drum (item (length of [Sequenz v]) of [Sequenz v]) for (0.25) beats
    switch costume to (item (length of [Sequenz v]) of [Sequenz v])
    wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---