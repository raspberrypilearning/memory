## Record

Ora salva il punteggio più alto in modo da poter giocare contro i tuoi amici.

\--- task \--- Aggiungi due nuove variabili chiamate `Punteggio record`{: class = "block3variables"} e `nome`{: class = "block3variables"} al tuo progetto. \--- /task \---

Quando il gioco finisce perché il giocatore ottiene la sequenza sbagliata, il gioco dovrebbe verificare se il punteggio è superiore al punteggio record corrente. Se lo è, il gioco deve salvare il punteggio come il punteggio record e anche memorizzare il nome del giocatore.

\--- task \--- Aggiungi codice al tuo sprite personaggio per memorizzare il `punteggio record`{: class = "block3variables"}. Chiedi anche il nome del giocatore e memorizzalo nella variabile `nome`{: class = "block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- Il tuo nuovo codice deve seguire questo schema:

Dopo il messaggio `gioco finito`{: class = "block3looks"} `Se`{: class = "block3control"} il `punteggio`{: class = "block3variables"} è `maggiore di`{: class = "block3operators "} il `punteggio più alto`{: class =" block3variables "} `Porta`{: class =" block3variables "} il `punteggio più alto`{: class =" block3variables "} uguale al `punteggio `{: class =" block3variables "} `Chiedi`{: class =" block3sensing "} il nome del giocatore `Imposta`{: class =" block3variables "} il `nome`{: class =" block3variables "} uguale alla `risposta`{: class = "block3sensing"} \--- /hint \--- \--- hint \---

Hai bisogno dei seguenti blocchi:

![ballerina](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(punteggio record)

ask [Come ti chiami?] and wait

set [punteggio record v] to [ ] 

set [nome v] to [ ] 
```

\--- /hint \--- \--- hint \--- Ecco come dovrebbe essere il codice per quando viene premuto il pulsante rosso:

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequenza v])=[1]> then
    play drum (item (1 v) of [sequenza v]) for (0.25) beats
    delete (1 v) of [sequenza v]
else
    say [Hai perso!] for (1) seconds
    if < (punteggio :: variables) > (Punteggio record) > then
        set [Punteggio record v] to (punteggio :: variables)
        ask [Record! Come ti chiami?] and wait
        set [nome v] to (answer)
    end
    stop [all v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

È necessario aggiungere questo nuovo codice allo sprite del personaggio anche per gli altri tre colori!

Riesci a vedere che il codice "Hai perso" per ciascuno dei quattro colori è esattamente lo stesso?

![ballerina](images/ballerina.png)

```blocks3
say [Hai perso!] for (1) seconds
if < (punteggio :: variables) > (Punteggio record) > then
    set [Punteggio record v] to (punteggio :: variables)
    ask [Record! Come ti chiami?] and wait
    set [nome v] to (answer)
end
stop [all v]
```

Se è necessario modificare il codice "Hai perso", ad esempio per aggiungere un suono o cambiare il messaggio "Hai perso", è necessario cambiarlo quattro volte. È fastidioso e fa perdere un sacco di tempo.

Invece, puoi definire il tuo blocco di codice e utilizzarlo ovunque nel tuo progetto.

\--- task \--- Fare clic su `I Miei Blocchi`{: class = "block3myblocks"}, quindi su **Crea blocco**. Chiama questo nuovo blocco `Hai perso`{: class = "block3myblocks"}.

\--- /task \---

\--- task \--- Aggiungi il codice dal blocco `else`{: class = "block3control"} collegato al `rosso`{: class = "block3events"} trasmesso al `Hai perso`{: class = blocco "block3myblocks"} in modo che assomigli a questo:

![ballerina](images/ballerina.png)

```blocks3
define Hai perso
say [Hai perso!] per (1) secondi
se < (punteggio :: variables) > (Punteggio record) > then
    set [Punteggio record v] to (punteggio :: variabili)
    ask [Record ! Come ti chiami?] and wait
    set [nome v] to (answer)
end
stop [all v]
```

\--- /task \---

\--- task \--- Ora rimuovi il codice che si trova nel blocco `else`{: class = "block3control"} collegato al messaggio `rosso`{: class = "block3events"} e aggiungi il blocco `Hai perso`{class = "block3myblocks"} al suo posto:

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequenza v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequenza v]
else
    Hai perso :: custom
end
```

\--- /task \---

\--- task \--- Metti alla prova il tuo nuovo blocco giocando e cliccando il pulsante rosso nel punto sbagliato nella sequenza di colori. \--- /task \---

Il tuo nuovo blocco `Hai perso`{: class = "block3myblocks"} è una **funzione**, un piccolo script che puoi usare ovunque nel codice aggiungendo il blocco `Hai perso`{: class = "block3myblocks"}.

\--- task \--- Sostituisci anche il codice nel blocco `else`{: class = "block3control"} collegato alle trasmissioni `broadcasts`{: class = "block3events"} per gli altri colori con il tuo nuovo blocco `Hai perso`{: class = "block3myblocks"}. Ecco come dovrebbe apparire il codice per il messaggio `blue`{: class = "block3events"}

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequenza v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequenza v]
else
    Hai perso :: custom
end
```

\--- /task \---

\--- task \--- Ora aggiungi un suono che viene riprodotto quando viene premuto il pulsante sbagliato. Devi solo aggiungere questo codice una volta nel blocco `Hai perso`{: class = "block3myblocks"} che hai creato, e non quattro volte!

![ballerina](images/ballerina.png)

```blocks3
define Hai perso
start sound [Cough1 v]
dì [Hai perso!] per (1) secondi
se < (punteggio :: variables) > (Punteggio record) > poi
    suono play (trumpet1 v)
    set [Punteggio record v] to (punteggio)
    ask [Record! Come ti chiami?] and wait
    set [nome v] to (answer)
end
stop [all v]
```

\--- /task \---