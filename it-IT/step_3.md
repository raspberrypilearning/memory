## Aggiungi un suono

--- task ---

Metti alla prova il tuo progetto alcune volte. Hai notato che a volte lo stesso numero viene scelto due o più volte consecutivamente, rendendo più difficile memorizzare la sequenza?

--- /task ---

Sei in grado di aggiungere un suono di batteria ogni volta che lo sprite del personaggio cambia costume? E che dire di un suono di batteria diverso per ogni colore?

--- task ---

Aggiungi l'estensione Musica al tuo progetto in modo da poter usare il blocco `suona il tamburo`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

Il codice che suona il tamburo è **molto** simile al codice che cambia il costume del personaggio.

--- hints ---


--- hint ---

Hai solo bisogno di aggiungere due blocchi: un blocco `suona tamburo per (0.25) battute`{:class="block3sound"} e un `elemento (lunghezza di sequenza) di sequenza`{:class="block3variables"}.

--- /hint ---

--- hint ---

Ecco i blocchi di codice che ti serviranno:

![ballerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequenza v]) of [sequenza v])
```

--- /hint ---

--- hint ---

Ecco come dovrebbe essere il codice completo:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequenza v]
repeat (5)
	add (pick random (1) to (4)) to [sequenza v]
    play drum (item (length of [sequenza v]) of [sequenza v]) for (0.25) beats
    switch costume to (item (length of [sequenza v]) of [sequenza v])
    wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---