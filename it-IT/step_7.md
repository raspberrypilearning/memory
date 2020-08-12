## Sfida: migliora il tuo gioco

### Crea più blocchi

Vedi qualche altro codice ripetuto in tutti e quattro i pulsanti?

```blocks3
when I receive [rosso v]
if <(item (1 v) of [sequenza v])=[1]> then
	play drum (\(1\) Snare Drum v) for (0.25) beats
	delete (1 v) of [sequenza v]
else
	Game over :: custom
end

when I receive [blu v]
if <(item (1 v) of [sequenza v])=[1]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [sequenza v]
else
	Game over :: custom
end
```

Saresti capace di creare un altro blocco personalizzato che tutti i pulsanti possano usare?

### Un altro costume

Hai notato che il tuo gioco inizia con il personaggio che mostra uno dei quattro colori e che, mentre il giocatore sta ripetendo la sequenza, mostra l'ultimo colore estratto?

Sapresti aggiungere un altro semplice costume bianco al tuo personaggio e aggiungere del codice in modo che venga mostrato questo costume all'inizio del gioco e mentre il giocatore sta ripetendo la sequenza?

![schermata](images/colour-white.png)

### Livello di difficoltà

Puoi dare la possibilità al tuo giocatore di scegliere se giocare in "modalità facile" (usando solo i colori rosso e blu) o "modalità normale" (che usa tutti e quattro i colori)?

Se vuoi, puoi anche aggiungere una "modalità difficile", che fa uso di un quinto tamburo!