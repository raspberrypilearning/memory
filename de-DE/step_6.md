## Highscore

Lass uns den Highscore speichern, damit du gegen deine Freunde antreten kannst.

--- task ---

Füge Deinem Projekt die 2 neuen Variablen `Highscore`{:class="block3variables"} und `Name`{:class="block3variables"} hinzu.

--- /task ---

Wann immer das Spiel beendet wird (durch Drücken des falschen Knopfes), musst Du prüfen, ob das Ergebnis des Spielers höher ist als der aktuelle Highscore. Ist dies der Fall, musst Du sowohl die Punktzahl des neuen Highscores, als auch den Namen des Spielers speichern.

--- task ---

Füge Code zu deiner Spielfigur hinzu, um den `Highscore`{:class="block3variables"} zu speichern. Frage nach dem Namen des Spielers und speichere ihn in der `Name`{:class="block3variables"} - Variable.

[[[generic-scratch3-high-score]]]

--- hints ---


--- hint ---

Dein neuer Code muss diesem Muster folgen:

Nach der `Spiel vorbei!`{:class="block3looks"} - Nachricht `Falls`{:class="block3control"} die `Punktzahl`{:class="block3variables"} `größer als`{:class="block3operators"} der `Highscore`{:class="block3variables"} ist, `setze`{:class="block3variables"} den `Highscore`{:class="block3variables"} auf `Punktzahl`{:class="block3variables"} `Frage`{:class="block3sensing"} nach dem Namen des Spielers `Setze`{:class="block3variables"} den `Namen`{:class="block3variables"} auf die `Antwort`{:class="block3sensing"}

--- /hint ---

--- hint ---

Du benötigst die folgenden Blöcke:

![Ballerina](images/ballerina.png)

```blocks3
if < > then
end

(Punktzahl)

(Punktzahl)

[ ] > [ ]

answer

(Highscore)

ask [Wie ist dein Name?] and wait

set [Highscore v] to [ ] 

set [Name v] to [ ] 
```

--- /hint ---

--- hint ---

So sollte dein Code beim Betätigen des roten Knopfes aussehen:

![Ballerina](images/ballerina.png)

```blocks3
when I receive [rot v]
if <(item (1 v) of [Sequenz v])=[1]> then
	play drum (item (1 v) of [Sequenz v]) for (0.25) beats
	delete (1 v) of [Sequenz v]
else
	say [Spiel vorbei!] for (1) seconds
	if < (Punktzahl :: variables) > (Highscore) > then
		set [Highscore v] to (Punktzahl :: variables)
		ask [Highscore! Wie ist dein Name?] and wait
		set [Name v] to (answer)
	end
	stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

Du musst diesen neuen Code zu den anderen 3 Tasten hinzufügen!

Kannst du sehen, dass der "Spiel vorbei" -Code für jede der vier Farben genau gleich ist?

![Ballerina](images/ballerina.png)

```blocks3
say [Spiel vorbei!] for (1) seconds
if < (Punktzahl :: variables) > (Highscore) > then
	set [Highscore v] to (Punktzahl :: variables)
	ask [Highscore! Wie ist dein Name?] and wait
	set [Name v] to (answer)
end
stop [all v]
```

Wenn du jemals einen dieser Codes ändern musst, zum Beispiel um ein Geräusch hinzuzufügen oder die 'Spiel vorbei'-Nachricht zu ändern, müsstest du ganze 4 Mal die gleiche Änderung vornehmen! Das könnte lästig werden und viel Zeit verschwenden.

Stattdessen kannst du deine eigenen Bausteine definieren, und diese in deinem Projekt wiederverwenden.

--- task ---

Um dies zu tun, klicke auf `Meine Blöcke`{:class="block3myblocks"} und dann **‘Neuer Block’**. Benenne diesen neuen Block `‘Spiel vorbei’`{:class="block3myblocks"}.

--- /task ---

--- task ---

Füge den Code aus dem `sonst`{:class="block3control"} - Block zu der `roten`{:class="block3events"} Sendung zum `Spiel vorbei`{:class="block3myblocks"} - Block hinzu, sodass es wie folgt aussieht:

![Ballerina](images/ballerina.png)

```blocks3
define Spiel vorbei
say [Spiel vorbei!] for (1) seconds
if < (Punktzahl :: variables) > (Highscore) > then
	set [Highscore v] to (Punktzahl :: variables)
	ask [Highscore! Wie ist dein Name?] and wait
	set [Name v] to (answer)
end
stop [all v]
```

--- /task ---

--- task ---

Entferne nun den Code, der im `sonst`{:class="block3control"} - Block steht und mit der `rot`{:class="block3events"} - Nachricht verbunden ist. Füge stattdessen den `Spiel vorbei`{:class="block3myblocks"} - Block hinzu:

![Ballerina](images/ballerina.png)

```blocks3
when I receive [rot v]
if <(item (1 v) of [Sequenz v])=[1]> then
	play drum (\(1\) Snare Drum v) for (0.25) beats
	delete (1 v) of [Sequenz v]
else
	Spiel vorbei :: custom
end
```

--- /task ---

--- task ---

Teste deinen neuen Block, indem du das Spiel spielst und auf den roten Knopf an der falschen Stelle in der Farbsequenz klickst.

--- /task ---

Dein neuer `Spiel vorbei`{:class="block3myblocks"} - Block ist eine **Funktion**, ein kleines Skript, das du überall in deinem Code verwenden kannst, indem du den `Spiel vorbei`{:class="block3myblocks"} - Block einfügst.

--- task ---

Entferne nun den Code, der im `sonst`{:class="block3control"} Block steht und mit der `rot`{:class="block3events"} - Nachricht verbunden ist, und füge stattdessen den `Spiel vorbei!`{:class="block3myblocks"} - Block hinzu. Hier siehst du wie der Code für die `blau`{:class="block3events"} - Nachricht aussehen sollte

![Ballerina](images/ballerina.png)

```blocks3
when I receive [blau v]
if <(item (1 v) of [Sequenz v])=[1]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [Sequenz v]
else
	Spiel vorbei :: custom
end
```

--- /task ---

--- task ---

Füge als Nächstes ein Geräusch hinzu, wenn die falsche Taste gedrückt wird. Du musst diesen Code nur einmal im `Spiel vorbei`{:class="block3myblocks"} -Block hinzufügen, anstatt 4 Mal für jede einzelne Farbe!

![Ballerina](images/ballerina.png)

```blocks3
define Spiel vorbei
start sound [Cough1 v]
say [Spiel vorbei!] for (1) seconds
if < (Punktzahl :: variables) > (Highscore) > then
	play sound (trumpet1 v)
	set [Highscore v] to (Punktzahl)
	ask [Highscore! Wie ist dein Name?] and wait
	set [Name v] to (answer)
end
stop [all v]
```

--- /task ---