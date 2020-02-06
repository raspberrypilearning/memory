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

Hai solo bisogno di aggiungere due blocchi: un blocco `suona tamburo per (0.25) battute`{:class="block3sound"} e un `elemento (lunghezza di sequenza) di sequenza`{:class="block3variables"}.

\--- /hint \---

\--- hint \---

Ecco i blocchi di codice che ti serviranno:

![ballerina](images/ballerina.png)

```blocks3
suona il tamburo ((1) Snare Drum v) per (0.25) battute

(elemento (lunghezza di [sequenza v]) di [sequenza v])
```

\--- /hint \---

\--- hint \---

Ecco come dovrebbe essere il codice completo:

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