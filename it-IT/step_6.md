## Record

Ora salva il punteggio più alto in modo da poter sfidare i tuoi amici.

--- task ---

Aggiungi due nuove variabili chiamate `Punteggio record`{:class="block3variables"} e `nome`{:class="block3variables"} al tuo progetto.

--- /task ---

Quando il gioco finisce, perché il giocatore esegue una sequenza sbagliata, del codice dovrebbe verificare se il punteggio è superiore al punteggio record corrente. Se ciò si verifica, il gioco deve salvare il punteggio come il punteggio record e memorizzare anche il nome del giocatore.

--- task ---

Aggiungi codice al tuo sprite personaggio per memorizzare il `punteggio record`{:class="block3variables"}. Chiedi anche il nome del giocatore e memorizzalo nella variabile `nome`{:class="block3variables"}.

[[[generic-scratch3-high-punteggio]]]

--- hints ---

--- hint ---

Il tuo nuovo codice deve seguire questo schema:

Dopo il messaggio `game over`{:class="block3looks"} `Se`{:class="block3control"} il `punteggio`{:class="block3variables"} è `maggiore`{:class="block3operators "} del `punteggio record`{:class=" block3variables "} `Porta`{:class="block3variables "} `record`{:class=" block3variables "} al valore `punteggio`{:class=" block3variables "} `Chiedi`{:class="block3sensing "} il nome del giocatore `Imposta`{:class="block3variables "} il `nome`{:class="block3variables "} al valore `risposta`{:class="block3sensing"}

--- /hint ---

--- hint ---

Hai bisogno dei seguenti blocchi:

![ballerina](images/ballerina.png)

```blocks3
if < > then
end

(punteggio)

(punteggio)

[ ] > [ ]

answer

(record)

ask [Come ti chiami?] and wait

set [record v] to [ ] 

set [nome v] to [ ] 
```

--- /hint ---

--- hint ---

Ecco come dovrebbe essere il codice per quando viene premuto il pulsante rosso:

![ballerina](images/ballerina.png)

```blocks3
when I receive [rosso v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	say [Game over!] for (1) seconds
	if < (punteggio :: variables) > (record) > then
		set [record v] to (punteggio :: variables)
		ask [Record! Come ti chiami?] and wait
		set [nome v] to (answer)
	end
	stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

È necessario aggiungere questa parte di codice allo sprite personaggio anche in corrispondenza degli altri tre colori!

Ti risulta che il codice "Game over" per ciascuno dei quattro colori sia esattamente lo stesso?

![ballerina](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (punteggio :: variables) > (record) > then
	set [record v] to (punteggio :: variables)
	ask [Record! Come ti chiami?] and wait
	set [nome v] to (answer)
end
stop [all v]
```

Se vuoi modificare il codice di "Game over", ad esempio per aggiungere un suono o cambiare il messaggio "Hai perso", è necessario cambiarlo quattro volte. È fastidioso e fa perdere un sacco di tempo.

In alternativa, potresti definire un tuo blocco personale di codice e utilizzarlo più volte all'interno del tuo progetto.

--- task ---

Fare clic su `I Miei Blocchi`{:class="block3myblocks"}, quindi su **Crea blocco**. Chiama questo nuovo blocco `Game over`{:class="block3myblocks"}.

--- /task ---

--- task ---

Dal gruppo di comandi riguardanti la ricezione del messaggio `rosso`{:class="block3events"}, copia il codice contenuto in `altrimenti`{:class="block3control"} e aggiungilo al blocco `Game over`{:class="block3myblocks"} in modo che assomigli a questo:

![ballerina](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (punteggio :: variables) > (record) > then
	set [record v] to (punteggio :: variables)
	ask [Record! Come ti chiami?] and wait
	set [nome v] to (answer)
end
stop [all v]
```

--- /task ---

--- task ---

Ora rimuovi il codice che si trova nel blocco `else`{:class="block3control"} collegato al messaggio `rosso`{:class="block3events"} e aggiungi il blocco `Hai perso`{class="block3myblocks"} al suo posto:

![ballerina](images/ballerina.png)

```blocks3
when I receive [rosso v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(1\) Snare Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Game over :: custom
end
```

--- /task ---

--- task ---

Testa il tuo nuovo blocco giocando e cliccando il pulsante rosso in un punto sbagliato nella sequenza di colori.

--- /task ---

Il tuo nuovo blocco `Game over`{:class="block3myblocks"} è una **funzione**, un piccolo script che puoi usare ovunque nel codice aggiungendo il blocco `Game over`{:class="block3myblocks"}.

--- task ---

Sostituisci anche il codice sotto `altrimenti`{: class = "block3control"} all'interno del gruppo di codice `quando ricevo`{:class="block3events"}, relativo agli altri colori, con il tuo nuovo blocco personale `Game over`{:class="block3myblocks"}. Ecco come dovrebbe apparire il codice per il messaggio `blu`{:class="block3events"}

![ballerina](images/ballerina.png)

```blocks3
when I receive [blu v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Game over :: custom
end
```

--- /task ---

--- task ---

Ora aggiungi un suono che venga riprodotto quando viene premuto il pulsante sbagliato. Devi solo aggiungere questo codice una volta sola, all'interno del blocco `Game over`{:class="block3myblocks"} che hai creato, e non quattro volte!

![ballerina](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (punteggio :: variables) > (record) > then
	play sound (trumpet1 v)
	set [record v] to (punteggio)
	ask [Record! Come ti chiami?] and wait
	set [nome v] to (answer)
end
stop [all v]
```

--- /task ---