## Ripetere la sequenza

Ora stai per aggiungere quattro pulsanti che il giocatore deve premere per ripetere la sequenza di colori.

--- task ---

Aggiungiamo quattro nuovi sprite al tuo progetto per rappresentare i quattro pulsanti.

+ Modifica il colore ai costumi dei nuovi sprite in modo che ci sia uno sprite corrispondente a ciascuno dei quattro colori
+ Metti gli sprite nello stesso ordine sul palco come i costumi: rosso, blu, verde, giallo

![schermata](images/colour-drums.png)

--- /task ---

--- task ---

Aggiungi il codice al sprite rosso in modo che, quando lo sprite viene cliccato, un messaggio "rosso" `viene inviato`{:class="block3events"} allo sprite personaggio:

![tamburo-rosso](images/red_drum.png)

```blocks3
when this sprite clicked
broadcast (rosso v)
```

--- /task ---

L'`invia a tutti`{:class="block3events"} è simile a quei messaggi emessi dagli altoparlanti, che si possono sentire per esempio nelle scuole o nei supermercati. Tutti gli sprite possono ascoltare l'`invia a tutti`{:class="block3events"}, ma solo lo sprite incaricato di rispondere farà qualcosa.

--- task ---

Aggiungi codice simile al precedente anche agli sprite blu, verde e giallo per far `inviare a tutti`{:class="block3events"} il numero del proprio colore.

--- /task ---

Ti ricordi che l'`invia a tutti`{:class="block3events"} è come un messaggio di un altoparlante? Aggiungerai del codice per assicurarti che lo sprite del personaggio reagisca ai messaggi trasmessi tramite l'`invia a tutti`{:class="block3events"}.

--- task ---

Quando il tuo personaggio sprite riceve il messaggio `rosso`{:class="block3events"}, il codice dovrebbe verificare se il numero `1` è all'inizio della lista `sequenza`{:class="block3variables"} (ciò significa che `rosso`{:class="block3events"} è il colore successivo nella sequenza).

Se `1` è all'inizio della lista, il codice rimuoverà il numero dalla lista perché il giocatore ha ricordato il colore corretto. Diversamente sarà game over e un comando `ferma tutto`{:class="block3control"} terminerà il gioco.

![ballerina](images/ballerina.png)

```blocks3
when I receive [rosso v]
if <(item (1 v) of [sequence v])=[1]> then
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

--- /task ---

--- task ---

A quanto appena scritto, aggiungi del codice in modo che anche un tamburo suoni, quando lo sprite del personaggio riceve, tramite l'`invia a tutti`{:class="block3events"}, il messaggio corretto.

--- hints ---

--- hint ---

Riesci a usare i numeri che corrispondono ad ogni colore per riprodurre il suono di tamburo corretto?

+ 1 = rosso
+ 2 = blu
+ 3 = verde
+ 4 = giallo

--- /hint ---

--- hint ---

Sopra il `cancella 1 da sequenza`{:class="block3variables"}, aggiungi `suona il tamburo`{:class=" block3sound "} per riprodurre il primo suono nell'elenco `sequenza`{:class="block3variables "}.

--- /hint ---

--- hint ---

Ecco il codice che dovrai aggiungere:

```blocks3
when I receive [rosso v]
if <(item (1 v) of [sequence v])=[1]> then
+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

Duplica il codice che hai usato per far rispondere lo sprite personaggio al messaggio `rosso`{:class="block3events"}. Cambia il codice appena copiato in modo che invii il messaggio `blu`{:class="block3events"}.

--- /task ---

Quando lo sprite risponde al messaggio `blu`{:class="block3events"}, quale parte di codice dovresti mantenere e quale cambiare? Ricorda che ad ogni colore corrisponde un numero preciso.

--- task ---

Modifica il codice dello sprite personaggio in modo che il personaggio risponda correttamente al messaggio `blu`{:class="block3events"}.

--- hints ---

--- hint ---

Puoi riciclare questi blocchi, ma devi modificarli in qualche modo:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [rosso v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

--- /hint ---

--- hint ---

Ecco come dovrebbere risultare il codice in risposta all'invio del messaggio`blu`{:class="block3events"}.

![ballerina](images/ballerina.png)

```blocks3
when I receive [blu v]
if <(item (1 v) of [sequence v])=[2]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	say [Game over!] for (1) seconds
	stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

Duplica nuovamente il codice due volte (per i pulsanti verde e giallo) e modifica le parti necessarie in modo che il carattere risponda correttamente ai nuovi messaggi `inviati a tutti`{:class="block3events"}.

--- /task ---

Ricordati di testare il codice! Viene memorizzata una sequenza di cinque colori? La sequenza è diversa ogni volta?

Quando il giocatore ripete correttamente l'intera sequenza di colori, la lista `sequenza`{:class="block3variables"} si svuota e il giocatore vince. Se vuoi, puoi anche mostrare alcune luci lampeggianti come ricompensa una volta che la lista `sequenza`{:class="block3variables"} è vuota.

--- task ---

Aggiungi questo codice alla fine del codice del tuo personaggio che inizia con `quando si clicca sulla bandiera verde`{:class="block3events"}:

![ballerina](images/ballerina.png)

```blocks3
wait until < (length of [sequence v]) = [0]>
broadcast (won v) and wait

    attendi fino a quando <(lunghezza di [sequenza v]) = [0]>
invia a tutti (vinto v) e attendi
```

--- /task ---

--- task ---

Passa allo Stage e importa il suono `drum machine` o quello che desideri.

[[[generic-scratch3-sound-from-library]]]

--- /task ---

--- task ---

Aggiungi questo codice per riprodurre un suono e fare in modo che lo sfondo cambi colore quando il giocatore vince.

![ballerina](images/stage.png)

```blocks3
when I receive [vinto v]
start sound (drum machine v)
repeat (50)
	change [color v] effect by (25)
	wait (0.1) seconds
end
clear graphic effects
```

--- /task ---