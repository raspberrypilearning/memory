## Höchstpunktestand

Lass uns den Höchstpunktestand bzw. High score speichern, damit Du gegen Deine Freunde antreten kannst.

\--- task \--- Füge Deinem Projekt die 2 neuen Variablen `High Score`{:class="block3variables"} und `Name`{:class="block3variables"} hinzu. \--- /task \---

Wann immer das Spiel beendet wird (durch Drücken des falschen Knopfes), musst Du prüfen, ob das Ergebnis des Spielers höher ist als der aktuelle Höchstpunktestand. Ist dies der Fall, musst Du sowohl die Punktzahl des neuen High scores, als auch den Namen des Spielers speichern.

\--- task \--- Füge Code zu deiner Spielfigur hinzu, um den `High Score`{:class="block3variables"} zu speichern. Frage auch den Namen des Spielers und speichere ihn in der `Name`{:class="block3variables"} - Variable.

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- Dein neuer Code sollte diesem Muster folgen:

Nach der `Game Over`{:class="block3looks"} - Nachricht `Falls`{:class="block3control"} die `Punktzahl`{:class="block3variables"} `größer als`{:class="block3operators"} der `High Score`{:class="block3variables"} ist, `setze`{:class="block3variables"} den `High Score`{:class="block3variables"} auf `Punktzahl`{:class="block3variables"} `Frage`{:class="block3sensing"} nach dem Namen des Spielers `Setze`{:class="block3variables"} den `Namen`{:class="block3variables"} auf die `Antwort`{:class="block3sensing"} \--- /hint \--- \--- hint \---

Du benötigst die folgenden Blöcke:

![Ballerina](images/ballerina.png)

```blocks3
Falls < >, dann
end

(Punktzahl)

(Punktzahl)

[ ] > [ ]

Antwort

(High Score)

frage [Wie ist dein Name?] und warte

setze [High Score v] auf [ ] 

setz [Name v] auf [ ] 
```

\--- /hint \--- \--- hint \--- So sollte dein Code bei betätigen des roten Knopfes aussehen:

![Ballerina](images/ballerina.png)

```blocks3
Wenn ich [rot v] empfange
falls <(Element (1 v) von [Sequenz v]) = [1]> , dann 
    spiele Trommel (Element (1 v) von [Sequenz v]) für (0.25) Schläge
    lösche (1 v) aus [Sequenz v]
sonst 
    sage [Game Over!] für (1) Sekunden
    falls <(Punktzahl :: variables) > (High Score)> , dann 
        setze [High Score v] auf (Punktzahl :: variables)
        frage [High Score! Wie ist dein Name?] und warte
        setze [Name v] auf (Antwort)
    end
    stoppe [alles v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

Du musst diesen neuen Code zu deiner Spielerfigur für die anderen drei Farben hinzufügen!

Kannst du sehen, dass der "Game Over" -Code für jede der vier Farben genau gleich ist?

![Ballerina](images/ballerina.png)

```blocks3
sage [Game Over!] für (1) Sekunden
falls < (Punktzahl :: variables) > (High Score) > , dann 
  setze [High Score v] auf (Punktzahl :: variables)
  ask [High Score! Wie ist dein Name?] und warte
    setze [Name v] auf (Antwort)
end
stoppe [alles v]
```

Wenn Du jemals einen dieser Codes ändern musst, zum Beispiel um ein Geräusch hinzuzufügen oder die ‘Game over’´-Nachricht zu ändern, müsstest Du ganze 4 Mal die gleiche Änderung vornehmen! Das könnte lästig werden und viel Zeit verschwenden.

Stattdessen kannst Du Deine eigenen Bausteine definieren, und diese in Deinem Projekt wiederverwenden.

\--- task \--- Um dies zu tun, klicke auf `Meine Blöcke`{:class="block3myblocks"} und dann **‘Neuer Block’**. Benenne diesen neuen Block `‘Game Over’`{:class="block3myblocks"}.

\--- /task \---

\--- task \--- Füge den Code aus dem `sonst`{:class="block3control"} - Block zu der `roten`{:class="block3events"} Sendung zum `Game Over` {:class="block3myblocks"} - Block hinzu, sodass es wie folgt aussieht:

![Ballerina](images/ballerina.png)

```blocks3
Definiere Game over
sage [Game over!] für (1) Sekunden
falls < (Punktzahl :: variables) > (High Score) >, dann
    setze [High Score v] auf (Punktzahl :: variables)
    frage [High Score! Wie ist dein Name?] und warte
    setze [Name v] auf (Antwort)
end
stoppe [alles v]
```

\--- /task \---

\--- task \--- Entferne nun den Code, der im `Sonst`{:class="block3control"} Block steht und mit der `rot`{:class="block3events"} - Nachricht verbunden ist, und füge stattdessen den `Game Over`{:class="block3myblocks"} - Block hinzu:

![Ballerina](images/ballerina.png)

```blocks3
Wenn ich [rot v] empfange
falls < (Element (1 v) von [Sequenz v]) = [1] > ,dann 
    spiele Trommel ((1) Snare Drum v) für (0.25) Schläge
    lösche (1 v) aus [Sequenz v]
sonst 
    Game over :: custom
end
```

\--- /task \---

\--- task \--- Teste deinen neuen Block, indem du das Spiel spielst und auf den roten Knopf an der falschen Stelle in der Farbsequenz klickst. \--- /task \---

Dein neuer `Game Over`{:class="block3myblocks"} - Block ist eine **Funktion**, ein kleines Skript, das du überall in deinem Code verwenden kannst, indem du den `Game Over`{:class="block3myblocks"} - Block einfügst.

\--- task \--- Entferne nun den Code, der im `Sonst`{:class="block3control"} Block steht und mit der `rot`{:class="block3events"} - Nachricht verbunden ist, und füge stattdessen den `Game Over`{:class="block3myblocks"} - Block hinzu. Hier siehst du wie der Code für die `blau` - Nachricht {:class="block3events"} aussehen sollte

![Ballerina](images/ballerina.png)

```blocks3
Wenn ich [blau v] empfange
falls < (Element (1 v) von [Sequenz v]) = [1]>, dann 
    spiele Trommel ((2) Basstrommel v) für (0.25) Schläge
    lösche (1 v) aus [Sequenz v]
sonst 
    Game over :: custom
end
```

\--- /task \---

\--- task \--- Füge jetzt einen Ton hinzu, der abgespielt wird, wenn der falsche Button gedrückt wird. Du musst diesen Code nur einmal in den `Game over`{:class="block3myblock"} - Block einfügen, den du erstellt hast, und nicht vier Mal getrennt!

![Ballerina](images/ballerina.png)

```blocks3
Definiere Game over
spiele Klang [Husten v]
sage [Game over!] für (1) Sekunden
falls < (Punktzahl :: variables) > (High Score) >, dann 
  spiele Klang (Trompete v)
  setze [High Score v] auf (Punktzahl)
  frage [High Score! Wie ist dein Name?] und warte
    setze [Name v] auf (Antwort)
end
stoppe [alles v]
```

\--- /task \---