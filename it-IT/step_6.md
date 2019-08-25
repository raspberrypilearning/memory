## Record

Ora salva il punteggio più alto in modo da poter sfidare i tuoi amici.

\--- task \--- Aggiungi due nuove variabili chiamate `Punteggio record`{:class="block3variables"} e `nome`{:class="block3variables"} al tuo progetto. \--- /task \---

Quando il gioco finisce, perché il giocatore esegue una sequenza sbagliata, del codice dovrebbe verificare se il punteggio è superiore al punteggio record corrente. Se ciò si verifica, il gioco deve salvare il punteggio come il punteggio record e memorizzare anche il nome del giocatore.

\--- task \--- Aggiungi codice al tuo sprite personaggio per memorizzare il `punteggio record`{:class="block3variables"}. Chiedi anche il nome del giocatore e memorizzalo nella variabile `nome`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- Il tuo nuovo codice deve seguire questo schema:

Dopo il messaggio `game overo`{:class="block3looks"} `Se`{:class="block3control"} il `punteggio`{:class="block3variables"} è `maggiore`{:class="block3operators "} del `punteggio record`{:class=" block3variables "} `Porta`{:class="block3variables "} `record`{:class=" block3variables "} al valore `punteggio`{:class=" block3variables "} `Chiedi`{:class="block3sensing "} il nome del giocatore `Imposta`{:class="block3variables "} il `nome`{:class="block3variables "} al valore `risposta`{:class="block3sensing"} \--- /hint \--- \--- hint \---

Hai bisogno dei seguenti blocchi:

![ballerina](images/ballerina.png)

```blocks3
se < > allora
end

(punteggio)

(punteggio)

[ ] > [ ]

(risposta)

(record)

chiedi [What's your name?] e attendi

porta [record v] a [ ]

porta [nome v] a [ ] 
```

\--- /hint \--- \--- hint \--- Ecco come dovrebbe essere il codice per quando viene premuto il pulsante rosso:

![ballerina](images/ballerina.png)

```blocks3
quando ricevo [rosso v]
se <(elemento (1 v) di [sequenza v]) = [1]> allora 
  suona il tamburo (elemento (1 v) di [sequenza v]) per (0.25) battute
  cancella (1 v) da [sequenza v]
altrimenti 
  dire [Hai perso!] per (1) secondi
  se <(punteggio :: variables) > (punteggio record) > allora 
    porta [record v] a (punteggio :: variables)  chiedi [Nuovo record! Come ti chiami?] e attendi
    porta [nome v] a (risposta)
  end
  ferma [all v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

È necessario aggiungere questa parte di codice allo sprite personaggio anche in corrispondenza degli altri tre colori!

Ti risulta che il codice "Game over" per ciascuno dei quattro colori sia esattamente lo stesso?

![ballerina](images/ballerina.png)

```blocks3
dire [Hai perso!] per (1) secondi
se <(punteggio :: variables) > (punteggio record)> allora 
  porta [record v] a (punteggio :: variables) chiedi [Nuovo record! Come ti chiami?] e attendi
  porta [nome v] a (risposta)
end
ferma [all v]
```

Se vuoi modificare il codice di "Game over", ad esempio per aggiungere un suono o cambiare il messaggio "Hai perso", è necessario cambiarlo quattro volte. È fastidioso e fa perdere un sacco di tempo.

In alternativa, potresti definire un tuo blocco personale di codice e utilizzarlo più volte all'interno del tuo progetto.

\--- task \--- Fare clic su `I Miei Blocchi`{:class="block3myblocks"}, quindi su **Crea blocco**. Chiama questo nuovo blocco `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \--- Aggiungi il codice dal blocco `else`{: class = "block3control"} collegato al `rosso`{: class = "block3events"} trasmesso al `Hai perso`{: class = blocco "block3myblocks"} in modo che assomigli a questo:

![ballerina](images/ballerina.png)

```blocks3
definisci Hai perso
say [Hai perso!] per (1) secondi
se <(punteggio :: variables) > (Punteggio record)> then
porta [Punteggio record v] a (punteggio)
chiedi [Record ! Come ti chiami?] e attendi
porta [nome v] a (risposta)
end
ferma [all v]
```

\--- /task \---

\--- task \--- Ora rimuovi il codice che si trova nel blocco `else`{: class = "block3control"} collegato al messaggio `rosso`{: class = "block3events"} e aggiungi il blocco `Hai perso`{class = "block3myblocks"} al suo posto:

![ballerina](images/ballerina.png)

```blocks3
quando ricevo [rosso v]
se <(elemento (1 v) di [sequenza v]) = [1]> allora 
  suona il tamburo ((1) Snare Drum v) per (0.25) battute
  cancella (1 v) da [sequenza v]
altrimenti 
  Hai perso :: custom
end
```

\--- /task \---

\--- task \--- Metti alla prova il tuo nuovo blocco giocando e cliccando il pulsante rosso nel punto sbagliato nella sequenza di colori. \--- /task \---

Il tuo nuovo blocco `Hai perso`{: class = "block3myblocks"} è una **funzione**, un piccolo script che puoi usare ovunque nel codice aggiungendo il blocco `Hai perso`{: class = "block3myblocks"}.

\--- task \--- Sostituisci anche il codice nel blocco `else`{: class = "block3control"} collegato alle trasmissioni `broadcasts`{: class = "block3events"} per gli altri colori con il tuo nuovo blocco `Hai perso`{: class = "block3myblocks"}. Ecco come dovrebbe apparire il codice per il messaggio `blue`{: class = "block3events"}

![ballerina](images/ballerina.png)

```blocks3
quando ricevo [blu v]
se <(elemento (1 v) di [sequenza v]) = [1]> allora 
  suona il tamburo ((2) Bass Drum v) per (0.25) battute
  cancella (1 v) da [sequenza v]
altrimenti 
  Hai perso :: custom
end
```

\--- /task \---

\--- task \--- Ora aggiungi un suono che viene riprodotto quando viene premuto il pulsante sbagliato. Devi solo aggiungere questo codice una volta nel blocco `Hai perso`{: class = "block3myblocks"} che hai creato, e non quattro volte!

![ballerina](images/ballerina.png)

```blocks3
definisci Hai perso
avvia riproduzione suono [Cough1 v]
dì [Hai perso!] per (1) secondi
se <(punteggio :: variables) > (Punteggio record)> poi
suono play (trumpet1 v)
porta [Punteggio record v] a (punteggio)
ask [Record! Come ti chiami?] e attendi
porta [nome v] a (risposta)
end
ferma [all v]
```

\--- /task \---