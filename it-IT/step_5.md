## Livelli multipli

Finora, il giocatore deve solo ricordare una sequenza di cinque colori. Migliora il tuo gioco aggiungendo un punteggio e facendo in modo che, quando il giocatore guadagna punti, il gioco passi al livello successivo e la sequenza di colori da ricordare diventi più lunga.

\--- Crea una nuova variabile chiamata `punteggio`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

In base al `punteggio `{:class="block3variables"}, il gioco deciderà la lunghezza della sequenza di colori. Inizia con un punteggio (e una lunghezza della sequenza) di `3`.

\--- task \--- Aggiungi un blocco sotto `quando si clicca sulla bandiera verde`{:class="block3events"} per impostare il `punteggio`{:class="block3variables"} a `3`. \--- /task \---

Invece di creare sempre una sequenza di cinque colori, ora vuoi che sia il `punteggio`{:class="block3variables"} a determinare la lunghezza della sequenza.

\--- task \--- Modifica il ciclo `ripeti`{:class="block3control"} (usato per creare la sequenza di colori) per far sì che venga ripetuto un numero di volte pari a `punteggio`{:class="block3variables"}:

![sprite](images/ballerina.png)

```blocks3
repeat (punteggio :: variables)
end
```

\--- /task \---

\--- task \--- Se il giocatore ripeterà la sequenza corretta, dovrai aggiungere `1` al `punteggio `{:class="block3variables"}, e così facendo aumenterà anche la lunghezza della sequenza successiva. Aggiungi il seguente blocco al codice del personaggio **nel punto che ritieni sia giusto**:

![sprite](images/ballerina.png)

```blocks3
cambia [punteggio v] di (1)
```

\--- task \--- Chiedi ai tuoi amici di testare il tuo gioco. Ricorda di nascondere la lista `sequenza`{:class="block3variables"} prima di giocare! \--- /task \---

\--- /task \---

\--- task \--- Per conludere, aggiungi un ciclo `per sempre`{:class="block3control"} attorno al codice che genera la sequenza, in modo che il gioco crei una nuova sequenza di colori per ogni livello. Il codice del tuo personaggio dovrebbe assomigliare a questo:

![ballerina](images/ballerina.png)

```blocks3
quando si clicca sulla bandiera verde
porta [punteggio v] a [3]
per sempre 
  cancella (all v) da [sequenza v]
  ripeti (punteggio) volte 
    aggiungi (numero a caso tra (1) e (4)) a [sequenza v]
    passa al costume (elemento (lunghezza di [sequenza v]) di [sequenza v])
    attendi (1) secondi
  end
  attendi fino a quando <(lunghezza di [sequenza v]) = [0]>
  invia a tutti (vinto v) e attendi
  cambia [punteggio v] di (1)
end
```

\--- /task \---

\--- task \--- Chiedi ai tuoi amici di testare il tuo gioco. Ricorda di nascondere la lista `sequenza`{:class="block3variables"} prima di giocare! \--- /task \---