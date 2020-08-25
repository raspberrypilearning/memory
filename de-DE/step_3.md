## Geräusche hinzufügen

\--- task \---

Teste dein Projekt einige Male. Du stellst möglicherweise fest, dass manchmal die gleiche Zahl zweimal (oder mehrmals) nacheinander ausgewählt wird, was es schwieriger macht sich die Reihenfolge zu merken.

\--- /task \---

Kannst du jedes Mal, wenn dein Charakter das Kostüm wechselt, ein Trommel-Geräusch spielen? Kannst du auch jeweils ein anderes Trommel-Geräusch spielen, abhängig von der Zufallszahl, die ausgewählt wird?

\--- task \---

Füge die Musik-Erweiterung zu deinem Projekt hinzu, damit du den `Spiele-Schlaginstrument` {:class="block3extensions"} - Block nutzen kannst.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

Der Code, der die Trommel spielen lässt, ist **sehr** ähnlich zu dem Code, der für das Verändern des Kostüms des Charakters verantwortlich ist.

\--- hints \---

\--- hint \---

Du brauchst nur zwei Blöcke hinzufügen: einen `spiele Schlaginstrument für (0,25) Schläge` {:class="block3sound"} - Block und einen `Element (Länge von Sequenz) von Sequenz`{:class="block3variables"} - Block.

\--- /hint \---

\--- hint \---

Hier sind die Blöcke, die du brauchst:

![Ballerina](images/ballerina.png)

```blocks3
spiele Schlaginstrument ((1) Snare Drum v) für (0.25) Schläge

(Element (Länge von [Sequenz v]) von [Sequenz v])
```

\--- /hint \---

\--- hint \---

So sollte dein fertiger Code aussehen:

![Ballerina](images/ballerina.png)

```blocks3
Wenn die grüne Flagge angeklickt wird
lösche (alle v) aus [Sequenz v]
wiederhole (5) mal 
    füge (Zufallszahl von (1) bis (4)) zu [Sequenz v] hinzu
    spiele Schlaginstrument (Element (Länge von [Sequenz v]) von [Sequenz v]) für (0.25) Schläge
  wechsle zu Kostüm (Element (Länge von [Sequenz v]) von [Sequenz v])
  warte (1) Sekunden
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---