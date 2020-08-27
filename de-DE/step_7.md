## Herausforderung: Verbessere dein Spiel

### Erstelle mehr Blöcke

Findest du noch anderen Code, der für alle vier Tasten gleich ist?

```blocks3
when I receive [rot v]
if <(item (1 v) of [Sequenz v])=[1]> then
	play drum (\(1\) Snare Drum v) for (0.25) beats
	delete (1 v) of [Sequenz v]
else
	Spiel vorbei :: custom
end

when I receive [blau v]
if <(item (1 v) of [Sequenz v])=[1]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [Sequenz v]
else
	Spiel vorbei :: custom
end
```

Kannst du einen anderen benutzerdefinierten Block erstellen, der von jeder Taste verwendet wird?

### Ein anderes Kostüm

Hast du bemerkt, dass das Spiel damit beginnt, dass dein Charakter eine der vier Farben zeigt, und dass das Kostüm immer die letzte Farbe anzeigt, die der Spieler beim wiederholen der Farbsequenz ausgewählt hat?

Kannst du dem Charakter ein anderes komplett weißes Kostüm geben, welches zu Beginn des Spiels angezeigt wird, und wenn der Spieler versucht, die Sequenz zu wiederholen?

![Bildschirmfoto](images/colour-white.png)

### Schwierigkeitsgrad

Kannst Du Deinen Spielern erlauben, zwischen dem "einfachen Modus" (nur mit roten und blauen Trommeln) und dem "normalen Modus" (alle vier Trommeln werden verwendet) zu wählen?

Du könntest sogar einen “Schwierig-Modus” hinzufügen, wo eine fünfte Trommel verwendet wird!