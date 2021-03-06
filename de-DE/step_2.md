## Erstelle ein zufällige Farbenfolge

Erstelle zuerst einen Charakter, der eine zufällige Farbfolge anzeigen kann.

--- task ---

Erstelle ein neues Scratch-Projekt.

**Online:** Erstelle ein neues Scratch-Projekt unter [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Offline**: Öffne ein neues Projekt im Offline-Editor.

Wenn du den Scratch-Offline-Editor herunterladen und installieren möchtest, findest du diesen unter [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}.

--- /task ---

--- task ---

Füge eine neue Figur, sowie den passenden Bühnenhintergrund hinzu. Dein Charakter muss keine Person sein, aber er muss verschiedene Farben annehmen können.

![Bildschirmfoto](images/colour-sprite.png)

--- /task ---

+ Dein Spiel sollte für jede Farbe eine andere Nummer verwenden:
    
    + 1 = rot
    + 2 = blau
    + 3 = grün
    + 4 = gelb

--- task ---

Gib deinem Charakter vier Kostüme mit unterschiedlichen Farben, ein Kostüm für jede der oben gezeigten Farben. Stelle sicher, dass die Farben der Kostüme richtig geordnet sind.

![Bildschirmfoto](images/colour-costume.png)

--- /task ---

Du kannst den **Fülleimer** verwenden, um Teile des Kostüms mit einer anderen Farbe zu füllen.

![eine-Form-einfärben](images/color-a-shape.png)

Füge jetzt eine Liste hinzu, um die zufällige Reihenfolge der Farben zu speichern, die der Spieler sich merken soll.

--- task ---

Erstelle eine neue Liste namens `Sequenz`{:class="block3variables"}. Da nur deine Figur die Liste sehen muss, kannst du beim Erstellen der Liste **Nur für diese Figur** auswählen.

[[[generic-scratch3-make-list]]]

--- /task ---

Du solltest nun sowohl deine leere Liste in der oberen linken Ecke deiner Bühne sehen, als auch eine Menge neuer Bausteine für die Verwendung der Liste.

![Bildschirmfoto](images/colour-list-blocks-annotated.png)

Jede Farbe hat eine andere Nummer, so kannst du eine Zufallszahl auswählen um ein zufällige Farbe in die Liste hinzuzufügen.

--- task ---

Füge diesen Code zur Figur hinzu, um der `Sequenz`{:class="block3variables"} nacheinander eine zufällige Nummer zuzuordnen:

![Ballerina](images/ballerina.png)

```blocks3
when flag clicked
add (pick random (1) to (4)) to [Sequenz v]
```

--- /task ---

--- task ---

Teste deinen Code. Überprüfe, dass jedes Mal, wenn du auf die Flagge klickst, eine zufällige Nummer zwischen 1 und 4 zur Liste hinzugefügt wird.

--- /task ---

--- task ---

Kannst du dem Programm einen Code hinzufügen, um damit fünf zufällige Zahlen gleichzeitig zu erhalten?

--- hints ---


--- hint ---

Füge ein `lösche alles aus Sequenz`{:class="block3variables"} hinzu, um zunächst alle Elemente in der Liste zu entfernen und dann über einen `Wiederhole`{:class="block3control"} - Block 5 zufällige Elemente zu der Liste hinzufügen.

--- /hint ---

--- hint ---

So sollte dein Code aussehen:

![Ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [Sequenz v]
repeat (5)
	add (pick random (1) to (4)) to [Sequenz v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

Ändere jedes Mal, wenn eine neue Zahl zur Liste hinzugefügt wird, das Kostüm, sodass die Farbe des Kostüms zur Zahl passt. Füge diese Blöcke in deinen Code ein, direkt unter dem Teil, an dem die Zufallszahlen zur `Sequenz`{:class="block3variables"} hinzugefügt werden:

![Ballerina](images/ballerina.png)

```blocks3
switch costume to (item (length of [Sequenz v]) of [Sequenz v])
wait (1) seconds
```

--- /task ---