## Livelli multipli

Finora, il giocatore deve solo ricordare una sequenza di cinque colori. Miglioriamo il gioco aggiungendo un punteggio e del codice in modo che la lunghezza della sequenza da ricordare aumenta insieme al punteggio.

+ Crea una nuova variabile chiamata `punteggio`{:class="blockdata"}.

[[[generic-scratch-add-variable]]]

Il `punteggio`{:class="blockdata"} sarà usato per determinare la lunghezza della sequenza che il giocatore deve memorizzare. Iniziamo con un punteggio (e una lunghezza della sequenza) di `3`.

+ Aggiungiamo un blocco all'inizio del codice del tuo personaggio che inizia con `quando si clicca sulla bandiera verde`{:class="blockevents"} per impostare il `punteggio`{:class="blockdata"} a `3`.

Invece di creare sempre una sequenza di cinque colori, ora dovrai impostare la lunghezza della sequenza in base al `punteggio`{:class="blockdata"}.

+ Cambia il loop `ripeti`{:class="blockcontrol"} del personaggio (che crea la sequenza) per farlo ripetere `punteggio`{:class="blockdata"} volte:

```blocks
    ripeti (punteggio) volte
    end
```

+ Se la sequenza è stata indovinata, dovrai aggiungere `1` al punteggio per aumentare la lunghezza della sequenza successiva. Aggiungi questo blocco al codice del personaggio **nel punto in cui la sequenza viene indovinata**.

```blocks
    cambia [punteggio v] di (1)
```

\--- hints \--- \--- hint \--- Saprai che la sequenza è stata indovinata correttamente nel punto in cui trasmetti il messaggio `vinto`. \--- /hint \--- \--- /hints \---

+ Infine, dovrai aggiungere un loop `per sempre`{:class="blockcontrol"} attorno al codice che genera la sequenza, così da creare una sequenza per ogni livello. Il codice del tuo personaggio dovrebbe assomigliare a questo:
    
    ```blocks
        quando si clicca sulla bandiera verde
        porta [punteggio v] a [3]
        per sempre 
            cancella (tutto v) da [sequenza v]
            ripeti (punteggio) volte 
                aggiungi (numero a caso tra (1) e (4)) a [sequenza v]
                passa al costume (elemento (last v) di [sequenza v])
                attendi (1) secondi
            end
            attendi fino a quando <(length of [sequenza v]) = [0]>
            invia a tutti [vinto v] e attendi
            cambia [punteggio v] di (1)
        end
    ```

+ Fai testare il gioco ai tuoi amici. Ricordati di nascondere la lista `sequenza`{:class="blockdata} prima di farli giocare!