## Highscore

Lass uns den Highscore speichern, damit du gegen deine Freunde antreten kannst.

\--- task \---

Füge Deinem Projekt die 2 neuen Variablen `Highscore`{:class="block3variables"} und `Name`{:class="block3variables"} hinzu.

\--- /task \---

Wann immer das Spiel beendet wird (durch Drücken des falschen Knopfes), musst Du prüfen, ob das Ergebnis des Spielers höher ist als der aktuelle Highscore. Ist dies der Fall, musst Du sowohl die Punktzahl des neuen Highscores, als auch den Namen des Spielers speichern.

\--- task \---

Füge Code zu deiner Spielfigur hinzu, um den `Highscore`{:class="block3variables"} zu speichern. Frage nach dem Namen des Spielers und speichere ihn in der `Name`{:class="block3variables"} - Variable.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Dein neuer Code muss diesem Muster folgen:

Nach der `Spiel vorbei!`{:class="block3looks"} - Nachricht `Falls`{:class="block3control"} die `Punktzahl`{:class="block3variables"} `größer als`{:class="block3operators"} der `Highscore`{:class="block3variables"} ist, `setze`{:class="block3variables"} den `Highscore`{:class="block3variables"} auf `Punktzahl`{:class="block3variables"} `Frage`{:class="block3sensing"} nach dem Namen des Spielers `Setze`{:class="block3variables"} den `Namen`{:class="block3variables"} auf die `Antwort`{:class="block3sensing"}

\--- /hint \---

\--- hint \---

Du benötigst die folgenden Blöcke:

![Ballerina](images/ballerina.png)

```blocks3
Falls < >, dann
end

(Punktzahl)

(Punktzahl)

[ ] > [ ]

Antwort

(Highscore)

frage [Wie ist dein Name?] und warte

setze [Highscore v] auf [ ] 

setz [Name v] auf [ ] 
```

\--- /hint \---

\--- hint \---

So sollte dein Code beim Betätigen des roten Knopfes aussehen:

![Ballerina](images/ballerina.png)

```blocks3
Wenn ich [rot v] empfange
falls <(Element (1 v) von [Sequenz v]) = [1]> , dann 
    spiele Schlaginstrument (Element (1 v) von [Sequenz v]) für (0.25) Schläge
    lösche (1 v) aus [Sequenz v]
sonst 
    sage [Spiel vorbei!] für (1) Sekunden
    falls <(Punktzahl :: variables) > (Highscore)> , dann 
        setze [Highscore v] auf (Punktzahl :: variables)
        frage [Highscore! Wie ist dein Name?] und warte
        setze [Name v] auf (Antwort)
    end
    stoppe [alles v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

Du musst diesen neuen Code zu den anderen 3 Tasten hinzufügen!

Kannst du sehen, dass der "Spiel vorbei" -Code für jede der vier Farben genau gleich ist?

![Ballerina](images/ballerina.png)

```blocks3
sage [Spiel vorbei!] für (1) Sekunden
falls < (Punktzahl :: variables) > (Highscore) > , dann 
  setze [Highscore v] auf (Punktzahl :: variables)
  ask [Highscore! Wie ist dein Name?] und warte
    setze [Name v] auf (Antwort)
end
stoppe [alles v]
```

Wenn du jemals einen dieser Codes ändern musst, zum Beispiel um ein Geräusch hinzuzufügen oder die 'Spiel vorbei'-Nachricht zu ändern, müsstest du ganze 4 Mal die gleiche Änderung vornehmen! Das könnte lästig werden und viel Zeit verschwenden.

Stattdessen kannst du deine eigenen Bausteine definieren, und diese in deinem Projekt wiederverwenden.

\--- task \---

Um dies zu tun, klicke auf `Meine Blöcke`{:class="block3myblocks"} und dann **‘Neuer Block’**. Benenne diesen neuen Block `‘Spiel vorbei!’`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Füge den Code aus dem `sonst`{:class="block3control"} - Block zu der `roten`{:class="block3events"} Sendung zum `Spiel vorbei` {:class="block3myblocks"} - Block hinzu, sodass es wie folgt aussieht:

![Ballerina](images/ballerina.png)

```blocks3
Definiere Spiel vorbei
sage [Spiel vorbei!] für (1) Sekunden
falls < (Punktzahl :: variables) > (Highscore) >, dann
    setze [Highscore v] auf (Punktzahl :: variables)
    frage [Highscore! Wie ist dein Name?] und warte
    setze [Name v] auf (Antwort)
end
stoppe [alles v]
```

\--- /task \---

\--- task \---

Entferne nun den Code, der im `sonst`{:class="block3control"} - Block steht und mit der `rot`{:class="block3events"} - Nachricht verbunden ist. Füge stattdessen den `Spiel vorbei`{:class="block3myblocks"} - Block hinzu:

![Ballerina](images/ballerina.png)

```blocks3
Wenn ich [rot v] empfange
falls < (Element (1 v) von [Sequenz v]) = [1] >, dann 
    spiele Trommel ((1) Snare Drum v) für (0.25) Schläge
    lösche (1 v) aus [Sequenz v]
sonst 
    Spiel vorbei! :: custom
end
```

\--- /task \---

\--- task \---

Teste deinen neuen Block, indem du das Spiel spielst und auf den roten Knopf an der falschen Stelle in der Farbsequenz klickst.

\--- /task \---

Dein neuer `Spiel vorbei`{:class="block3myblocks"} - Block ist eine **Funktion**, ein kleines Skript, das du überall in deinem Code verwenden kannst, indem du den `Spiel vorbei`{:class="block3myblocks"} - Block einfügst.

\--- task \---

Entferne nun den Code, der im `sonst`{:class="block3control"} Block steht und mit der `rot`{:class="block3events"} - Nachricht verbunden ist, und füge stattdessen den `Spiel vorbei!`{:class="block3myblocks"} - Block hinzu. Hier siehst du wie der Code für die `blau` - Nachricht {:class="block3events"} aussehen sollte

![Ballerina](images/ballerina.png)

```blocks3
Wenn ich [blau v] empfange
falls < (Element (1 v) von [Sequenz v]) = [1]>, dann 
    spiele Schlaginstrument ((2) Basstrommel v) für (0.25) Schläge
    lösche (1 v) aus [Sequenz v]
sonst 
    Spiel vorbei! :: custom
end
```

\--- /task \---

\--- task \---

Füge als Nächstes ein Geräusch hinzu, wenn die falsche Taste gedrückt wird. Du musst diesen Code nur einmal im `Spiel vorbei`{:class="block3myblocks"} -Block hinzufügen, anstatt 4 Mal für jede einzelne Farbe!

![Ballerina](images/ballerina.png)

```blocks3
Definiere Spiel vorbei
spiele Klang [Husten v]
sage [Spiel vorbei!] für (1) Sekunden
falls < (Punktzahl :: variables) > (Highscore) >, dann 
  spiele Klang (Trompete v)
  setze [Highscore v] auf (Punktzahl)
  frage [Highscore! Wie ist dein Name?] und warte
    setze [Name v] auf (Antwort)
end
stoppe [alles v]
```

\--- /task \---