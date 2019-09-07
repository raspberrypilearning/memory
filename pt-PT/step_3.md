## Adicionar som

\--- task \---

Testa o teu projeto algumas vezes. Percebeste que às vezes o mesmo número é escolhido duas vezes (ou mais) seguidas, o que dificulta a memorização da sequência?

\--- /task \---

Consegues fazer tocar um som de bateria de todas as vezes que o actor mudar de traje? E que tal um som de bateria diferente para cada cor?

\--- task \---

Adiciona a extensão Música ao teu projeto para que possas utilizar o bloco `toca a percussāo`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

O código que toca a percussāo é **muito** semelhante ao código que faz mudar o traje do actor.

\--- hints \--- \--- hint \--- Basta adicionar dois blocos: um bloco `toca a percussāo durante (0.25) tempos`{:class="block3sound"} e um bloco `item (comprimento de sequência) de sequência`{:class="block3variables"}. \--- /hint \--- \--- hint \---

Aqui estão os blocos de que precisas:

![bailarina](images/ballerina.png)

```blocks3
toca a percussão ((1) Snare Drum v) durante (0.25) tempos

((o comprimento de [sequência v]) de [sequência v])
```

\--- /hint \---

\--- hint \--- Aqui está o aspeto que o teu código final deve ter:

![bailarina](images/ballerina.png)

```blocks3
Quando alguém clicar na bandeira verde
remove (tudo v) de [sequência v]
repete (5) vezes 
  acrescenta (um valor ao acaso entre (1) e (4)) a [sequência v]
  toca a percussão ((o comprimento de [sequência v]) de [sequência v]) durante (0.25) tempos
  muda o teu traje para ((o comprimento de [sequência v]) de [sequência v])
  espera (1) s
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---