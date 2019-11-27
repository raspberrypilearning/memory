## Herausforderung: Geräusche hinzufügen

\--- task \---

Teste Dein Projekt einige Male. Du stellst möglicherweise fest, dass manchmal die gleiche Zahl zweimal (oder mehrmals) nacheinander ausgewählt wird, was es schwieriger macht sich die Reihenfolge zu merken.

\--- /task \---

Kannst Du jedes Mal, wenn das Kostüm wechselt ein Trommel-Geräusch spielen? Kannst Du jeweils ein anderes Trommel-Geräusch machen, abhängig von der Zufallszahl, die ausgewählt wird?

\--- task \---

Füge die Musik-Erweiterung zu deinem Projekt hinzu, damit du den `Spiele-Trommel` {:class="block3extensions"} - Block nutzen kannst.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

Dies wird **sehr** ähnlich zu dem Code sein, der für das Verändern des Kostüms des Charakters verantwortlich ist.

\--- hints \--- \--- hint \--- Du brauchst nur zwei Blöcke hinzufügen: einen `spiele-Trommel für (0,25) Schläge` {:class="block3sound"} - Block und einen `Element (Länge der Sequenz) von Sequenz`{:class="block3variables"} - Block. \--- /hint \--- \--- hint \---

Hier sind die Blöcke, die du brauchst:

![Ballerina](images/ballerina.png)

```blocks3
spiele Schlaginstrument ((1) Snare Drum v) für (0.25) Schläge

(Element (Länge von [Sequenz v]) von [Sequenz v])
```

\--- /hint \---

\--- hint \---So sollte dein fertiger Code aussehen:

![Ballerina](images/ballerina.png)

```blocks3
Wenn die grüne Flagge angeklickt
lösche (alle v) aus [Sequenz v]
wiederhole (5) mal 
    füge (Zufallszahl von (1) bis (4)) zu [Sequenz v] hinzu
    spiele Trommel (Element (Länge von [Sequenz v]) von [Sequenz v]) für (0.25) Schläge
  wechsle zu Kostüm (Element (Länge von [Sequenz v]) von [Sequenz v])
  warte (1) Sekunden
end
```

\--- /hint \---

\---/hints\---

\--- /task \---