## Mehrere Ebenen

Bisher muss sich der Spieler nur 5 Farben merken. Lass uns dein Spiel verbessern, so dass die Länge der Farbenfolge erhöht wird. Verbessere dein Spiel, indem du Punkte hinzufügst und Code, der dafür sorgt, dass der Spieler zum nächsten Level gelangt und die Farbsequenz länger wird, wenn er genug Punkte gesammelt hat.

\--- task \---

Erstelle eine neue Variable namens `Punktzahl`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Basierend auf der `Punktzahl`{:class="block3variables"}, entscheidet das Spiel über die Länge der Farbsequenz. Beginnt mit einer Punktzahl (und einer Sequenzlänge) von `3`.

\--- task \---

Füge einen Block am Beginn des `wenn Fahne geklickt`{:class="block3events"} - Codes deines Charakters ein, um die `Punktzahl`{:class="block3variables"} auf `3` zu setzen.

\--- /task \---

Anstatt immer eine Folge von 5 Farben zu haben, möchtest Du nun, dass die `Punktzahl`{:class="block3variables"} die Sequenzlänge bestimmt.

\--- task \---

Ändere die `wiederholen`{:class="block3control"} - Schleife deines Charakters (für die Erstellung der Farbsequenz) um `Punktzahl`{:class="block3variables"} zu wiederholen:

![Figur](images/ballerina.png)

```blocks3
wiederhole (Punktzahl :: variables) mal
end
```

\--- /task \---

\--- task \---

Wird die Reihenfolge der Farben richtig wiedergegeben, solltest du `1` zu der `Punktzahl`{:class="block3variables"} hinzufügen, um die Länge der Sequenz zu erhöhen. Füge den folgenden Block zu dem Code deines Charakters **an der Stelle, an der du weißt, ob die Farbsequenz korrekt ist**, hinzu:

![Figur](images/ballerina.png)

```blocks3
ändere [Punktzahl v] um (1)
```

\--- hints \---

\--- hint \---

Du weißt, dass die Farbsequenz korrekt ist, wenn das Spiel die Nachricht 'Gewonnen' `sendet`{:class="block3events"}.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Schließlich musst du dem Code eine `Wiederhole fortlaufend`{:class="block3control"} - Schleife hinzufügen, sodass eine neue Farbsequenz für jedes Level erstellt wird. So sollte der Code deines Charakters aussehen:

![Ballerina](images/ballerina.png)

```blocks3
Wenn die grüne Flagge angeklickt wird
setze [Punktzahl v] auf [3]
wiederhole fortlaufend 
    lösche (alles v) aus [Sequenz v]
    wiederhole (Punktzahl) mal 
        füge (Zufallszahl von (1) bis (4)) zu [Sequenz v] hinzu
        wechsle zu Kostüm (Element (Länge von [Sequenz v]) von [Sequenz v])
        warte (1) Sekunden
  end
    warte bis <(Länge von [Sequenz v]) = [0]>
    sende (Gewonnen v) an alle und warte
    ändere [Punktzahl v] um (1)
end
```

\--- /task \---

\--- task \---

Lass deine Freunde das Spiel testen. Denke daran, die`Sequenz`{:class="block3variables"}-Liste auszublenden, bevor sie das Spiel starten!

\--- /task \---