## Adicionar som

\--- task \---

Testa o teu projeto algumas vezes. Vais perceber que às vezes o mesmo número é escolhido duas vezes (ou mais) seguidas, o que é que dificulta a memorização da sequência?

\--- /task \---

Consegues fazer tocar um som de bateria de todas as vezes que o sprite mudar de roupa? E que tal um som de bateria diferente para cada cor?

\--- task \---

Adiciona a extensão Música ao teu projeto para que possas uttiliar o bloco `play drum`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

O código que faz tocar o tambor é **muito** semelhante ao código que faz mudar o traje do sprite.

\--- hints \--- \--- hint \--- Basta adicionar dois blocos: um Bloco `play drum for (0.25) beats` {:class="block3sound"} e um bloco `item (length of sequence) of sequence`{:class="block3variables"}. \--- /hint \--- \--- hint \---

Aqui estão os blocos de que necessitas:

![bailarina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \--- Aqui está o aspeto que o teu código final deve ter:

![bailarina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
    play drum (item (length of [sequence v]) of [sequence v]) for (0.25) beats
    switch costume to (item (length of [sequence v]) of [sequence v])
    wait (1) seconds
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---