## Livelli multipli

Finora, il giocatore deve solo ricordare una sequenza di cinque colori. Migliora il tuo gioco aggiungendo un punteggio e aggiungendo del codice in modo che quando il giocatore guadagna punti, il gioco passi al livello successivo e la sequenza di colori da ricordare diventi più lunga.

\--- Crea una nuova variabile chiamata `punteggio`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

Sulla base del `punteggio `{: class = "block3variables"}, il gioco deciderà sulla lunghezza della sequenza di colori. Inizia con un punteggio (e una lunghezza della sequenza) di `3`.

\--- task \--- Aggiungi un blocco `all'inizio`{: class = "block3events"} per impostare il `punteggio `{: class = "block3variables"} su `3`. \--- /task \---

Invece di creare sempre una sequenza di cinque colori, ora vuoi che `punteggio `{: class = "block3variables"} determini la lunghezza della sequenza.

\--- task \--- Modifica il ciclo `repeat`{: class = "block3control"} (per creare la sequenza di colori) per far sì che venga ripetuto `punteggio`{: class = "block3variables"} volte:

![sprite](images/ballerina.png)

```blocks3
repeat (punteggio :: variables)
end
```

\--- /task \---

\--- task \--- Se il giocatore ripete la sequenza corretta, dovresti aggiungere `1` al `punteggio `{: class = "block3variables"}, e così facendo aumenta la lunghezza della sequenza successiva. Aggiungi il seguente blocco al codice del personaggio **nel punto in cui sai che la sequenza è corretta**:

![sprite](images/ballerina.png)

```blocks3
cambia [punteggio v] di (1)
```

\--- hints \--- \--- hint \--- Sai che la sequenza è corretta nel punto in cui il gioco trasmette un `broadcast`{: class = "block3events"} contenente il messaggio 'vinto'. \--- /hint \--- \--- /hints \---

\--- /task \---

\--- task \--- Infine, aggiungi un ciclo `forever`{: class = "block3control"} attorno al codice che genera la sequenza, in modo che il gioco crei una nuova sequenza di colori per ogni livello. Il codice del tuo personaggio dovrebbe assomigliare a questo:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
set [score v] to [3]
forever
    delete (all v) of [sequenza v]
    repeat (punteggio)
        add (pick random (1) to (4)) to [sequenza v]
        switch costume to (item (length of [sequenza v]) of [sequenza v]
        wait (1) seconds
    end
    wait until < (length of [sequenza v]) = [0]>
    broadcast (vinto v) and wait
    change [punteggio v] by (1)
end
```

\--- /task \---

\--- task \--- Chiedi ai tuoi amici a mettere alla prova il tuo gioco. Ricorda di nascondere la lista `sequenza`{: class = "block3variables"} prima di giocare! \--- /task \---