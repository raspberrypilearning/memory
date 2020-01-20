## Sfida: Aggiungi un suono

\--- task \---

Metti alla prova il tuo progetto alcune volte. Hai notato che a volte lo stesso numero viene scelto due o più volte consecutivamente, rendendo più difficile memorizzare la sequenza?

\--- /task \---

Sei in grado di aggiungere un suono di batteria ogni volta che lo sprite del personaggio cambia costume? E che dire di un suono di batteria diverso per ogni colore?

\--- task \---

Aggiungi l'estensione Musica al tuo progetto in modo da poter usare il blocco `suona il tamburo`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

Il codice che suona il tamburo è **molto** simile al codice che cambia il costume del personaggio.

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /hint \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
suona il tamburo ((1) Snare Drum v) per (0.25) battute

(elemento (lunghezza di [sequenza v]) di [sequenza v])
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

```blocks3
quando si clicca sulla bandiera verde
cancella (all v) da [sequenza v]
ripeti (5) volte 
  aggiungi (numero a caso tra (1) e (4)) a [sequenza v]
  suona il tamburo (elemento (lunghezza di [sequenza v]) di [sequenza v]) per (0.25) battute
  passa al costume (elemento (lunghezza di [sequenza v]) di [sequenza v])
  attendi (1) secondi
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---