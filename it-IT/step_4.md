## Ripetere la sequenza

Aggiungiamo 4 tasti che il giocatore può usare per ripetere la sequenza che ricorda.

+ Aggiungi 4 sprite al tuo progetto, che diventeranno tasti. Modifica i tuoi 4 sprite in modo che ce ne sia 1 per ognuno dei 4 colori.

	![screenshot](images/colour-drums.png)

+ Quando si clicca il tamburo rosso, dovrai trasmettere un messaggio al tuo personaggio, informandolo che il tasto rosso è stato cliccato. Aggiungi questo codice al tuo tamburo rosso:

	```blocks
		quando si clicca questo sprite
		invia a tutti [rosso v]
	```

+ Quando il tuo personaggio riceve questo messaggio, dovrebbe controllare se il numero 1 è all'inizio della lista (il che significa che il rosso è il prossimo colore nella sequenza). Se lo è, puoi rimuovere il numero dalla lista, in qaunto è stato indovinato correttamente. Altrimenti il gioco è finito!

	```blocks
		quando ricevo [rosso v]
		se <(item (1 v) of [sequenza v] :: list) = [1]> allora
  			cancella (1 v) da [sequenza v]
  		altrimenti
  			dire [Game over!] per (1) secondi
  			ferma [tutto v]
		end
	```

+ Puoi anche visualizzare delle luci lampeggianti una volta che la lista è vuota, perché significa che l'intera sequenza è stata indovinata correttamente. Aggiungi questo codice alla fine del testo `quando si clicca sulla bandiera verde` {.blockevents}.

	```blocks
		attendi fino a quando <(length of [sequenza v] :: list) = [0]>
		invia a tutti [won v] e attendi
	```

+ Clicca sul tuo quadro e aggiungi questo codice per riprodurre __qualsiasi__ suono e fare in modo che lo scenario cambi colore una volta che il giocatore ha vinto.

	```blocks
		quando ricevo [won v]
		produci suono [drum machine v]
		ripeti (50) volte
  			cambia effetto [colore v] di (25)
  			attendi (0.1) secondi
		end
		rimuovi effetti grafici
	```

## Sfida: Crea 4 tasti 
Ripeti gli stessi passi per i tasti blu, verde e giallo. Quale codice rimane lo stesso e quale cambierà per ciascun tasto?

Puoi anche aggiungere dei suoni che si attivano quando si premono i tasti.

Ricordati di provare il codice che hai aggiunto! Puoi memorizzare una sequenza di 5 colori? La sequenza è ogni volta diversa?
