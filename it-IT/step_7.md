## Sfida: migliora il tuo gioco

### Fai più blocchi

Vedi qualche altro codice uguale per tutti e quattro i pulsanti?

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game Over :: custom
end

when I receive [blue v]
if <(item (1 v) of [sequenza v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequenza v]
else
    Game over :: custom
end
```

Puoi creare un altro blocco personalizzato che tutti i pulsanti possono usare?

### Un altro costume

Riesci a vedere che il tuo gioco inizia con il tuo personaggio che mostra uno dei quattro colori e che il personaggio mostra sempre l'ultimo colore nella sequenza mentre il giocatore sta ripetendo la sequenza dei colori?

Puoi aggiungere un altro semplice costume bianco al tuo personaggio e aggiungere del codice in modo che il personaggio mostri questo costume all'inizio del gioco e mentre il giocatore sta ripetendo la sequenza?

![schermata](images/colour-white.png)

### Livello di difficoltà

Puoi permettere al tuo giocatore di scegliere tra giocare in "modalità facile" (usando solo i colori rosso e blu) e "modalità normale" (che usa tutti e quattro i colori)?

Se vuoi, puoi anche aggiungere una modalità 'difficile', che fa uso di un quinto tamburo!