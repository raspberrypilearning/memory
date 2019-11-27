## Reihenfolge wiederholen

Jetzt musst Du vier Tasten hinzufügen, die der Spieler drücken muss, um die Farbsequenz zu wiederholen.

\--- task \--- Füge Deinem Projekt vier Figuren hinzu, welche die vier Tasten darstellen.

+ Bearbeite Deine Figuren so, dass jeweils eine Figur für eine der vier Farben steht
+ Bringe die Figuren in der gleichen Reihenfolge auf die Bühne wie die Kostüme: rot, blau, grün, gelb

![Screenshot](images/colour-drums.png) \--- /task \---

\--- task \--- Wenn die rote Taste angeklickt wird, musst Du Deinem Charakter eine Nachricht `senden`{:class="block3events"}, dass die 'rote' Taste gedrückt wurde:

![rote Trommel](images/red_drum.png)

```blocks3
    Wenn diese Figur angeklickt wird
    sende (rot v) an alle
```

\--- /task \---

Ein `Sendung an alle`{:class="block3events"} ist wie eine Nachricht über einen Lautsprecher, die man zum Beispiel in Schulen oder Supermärkten hören kann. Alle Sprites hören die`Sendung an alle`{:class="block3events"}, aber nur die Figur, deren Aufgabe es ist, zu reagieren, wird etwas tun.

\--- task \---

Wiederhole die oben beschriebenen Schritte für Deine blauen, grünen und gelben Tasten, damit auch sie eine `Sendung an alle` für ihre eigene Farbe senden.

\--- /task \---

Erinnerst du dich, dass die `Sendung an alle`{:class="block3events"} wie eine Lautsprecher-Durchsage funktioniert? Füge nun Code zu deiner Spielerfigur hinzu, damit sie auf die `Sendung an alle`{:class="block3events"} - Nachrichten reagiert.

\--- task \---

Wenn dein Charakter die Nachricht `rot`{:class="block3events"} empfängt, sollte der Code prüfen, ob die Nummer `1` am Anfang der `Sequenz`{:class="block3variables} steht (was bedeutet, dass `rot`{:class="block3events"} die nächste Farbe in der Sequenz ist).

Wenn `1` am Beginn der Liste steht, kann die Nummer aus der Liste entfernt werden, da sie richtig erraten worden ist, weil der Spieler sich an die richtige Farbe erinnert hat. Ansonsten ist das Spiel vorbei, und der Code muss `alles anhalten`{:class="block3control"} um das Spiel zu beenden.

![Ballerina](images/ballerina.png)

```blocks3
Wenn ich [rot v] empfange
falls <(Element (1 v) von [Sequenz v]) = [1]>, dann 
lösche (1 v) aus [Sequenz v]
sonst 
sage [Game over!] für (1) Sekunden
stoppe [alles v]
end
```

\--- /task \---

\--- task \--- Füge zu dem Code, den du gerade geschrieben hast, hinzu, dass auch ein Trommelschlag gespielt wird, wenn die Charakterfigur die korrekte `Sendung an alle`{:class="block3events"} erhält.

\--- hints \--- \--- hint \--- Kannst du Zahlen nutzen, passend zu der jeder Farbe, um das Trommel-Geräusch zu spielen?

+ 1 = rot
+ 2 = blau
+ 3 = grün
+ 4 = gelb \--- /hint \--- \--- hint \--- Füge über dem `lösche 1 aus Sequenz`{:class="block3variables"} - Block einen `spiele Trommel`{:class="block3sound"} - Block hinzu um das erste Geräusch der `Sequenz`{:class="block3variables"} - Liste zu spielen.

\--- /hint \--- \--- hint \--- Hier steht der Code, den du brauchen wirst:

```blocks3
Wenn ich [rot v] empfange
falls <(Element (1 v) von [Sequenz v]) = [1]>, dann 

+ spiele Trommel ((1) Snare Drum v) für (0.25) Schläge
lösche (1 v) aus [Sequenz v]
sonst 
sage [Game over!] für (1) Sekunden
stoppe [alles v]
end

```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Kopiere den Code, den du gerade genutzt hast, um deiner Spielerfigur auf die Nachricht `rot`{:class="block3events"} zu reagieren. Ändere den kopierten Code, sodass er die Nachricht `blau` {:class="block3events"}sendet. \--- /task \---

Wenn die Figur auf die Nachricht `blau`{:class="block3events"} reagiert, welcher Teil des Codes sollte dann gleich bleiben und welcher sich verändern? Erinnere dich daran, dass jede Farbe eine zugehörige Ziffer hat.

\--- task \--- Ändere den Code der Spielerfigur so, dass der Character jedes Mal korrekt auf die Nachricht `blau`{:class="block3events"} reagiert.

\--- hints \--- \--- hint \---

Behalte diese Blöcke, aber du musst sie irgendwie ändern:

![Ballerina](images/ballerina.png)

```blocks3
<(Element (1 v) von [Sequenz v]) = [1]>

Wenn ich [rot v] empfange

spiele Trommel ((1) Snare Drum v) für (0.25) Schläge
```

\--- /hint \--- \--- Hinweis \--- So sollte dein Code für die `blau`{:class="block3events"} - Nachrichten aussehen.

![Ballerina](images/ballerina.png)

```blocks3
Wenn ich [blau v] empfange
falls < (Element (1 v) von [Sequenz v]) = [2] >, dann 
    spiele Trommel ((2) Basstrommel v) für (0.25) Schläge
    lösche (1 v) aus [Sequenz v]
sonst 
    sage [Game over!] für (1) Sekunden
    stoppe [alles v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Kopiere den Code erneut (für die grünen und gelben Schaltflächen), und ändere die notwendigen Teile, damit die Spielerfigur korrekt auf die neuen `Sendung an alle`{:class="block3events"} reagiert. \--- /task \---

Denke daran, den Code, den Du hinzugefügt hast, zu testen! Kannst Du Dir eine Folge von 5 Farben merken? Ist die Reihenfolge jedes Mal anders?

Wenn der Spieler die komplette `Sequenz`{:class="block3variables"} korrekt wiederholt, ist die Liste leer und der Spieler gewinnt. Du kannst auch ein paar blinkende Lichter anzeigen, sobald die `Liste`{:class="block3variables"} leer ist, da es bedeutet, dass die komplette Reihenfolge der Farben richtig erraten worden ist.

Fügen diesen Code an das Ende des `wenn Fahne geklickt`{:class="block3events"} -Skripts Deines Charakters hinzu:

![Ballerina](images/ballerina.png)

```blocks3
    warte bis <(Länge von [Sequenz v]) = [0]>
    sende (gewonnen v) an alle und warte
```

\--- /task \---

\--- task \--- Wechsele die Bühne und importieren den `Drum-Maschine`-Ton oder andere Töne, die du magst.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \--- Füge diesen Code hinzu, um einen Ton abzuspielen und den Hintergrund zu wechseln, sobald der Spieler gewonnen hat.

![Ballerina](images/stage.png)

```blocks3
    Wenn ich [gewonnen v] empfange
    spiele Klang (drum machine v)
    wiederhole (50) mal 
        ändere Effekt [Farbe v] um (25)
        warte (0.1) Sekunden
    end
    schalte Grafikeffekte aus
```

\--- /task \---