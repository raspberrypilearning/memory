## Adicione um som

--- task ---

Teste o seu projeto algumas vezes. Percebeu que às vezes o mesmo número é escolhido duas vezes seguidas (ou mais), o que dificulta a memorização da sequência?

--- /task ---

Você consegue fazer tocar um som de bateria todas as vezes que o ator mudar a fantasia? E que tal um som de bateria diferente para cada cor?

--- task ---

Adicione a extensão Música ao seu projeto para que você possa utilizar o bloco `toca a percussāo`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

O código que toca a percussāo é **muito** semelhante ao código que faz mudar a fantasia do ator.

--- hints ---


--- hint ---

Você precisa apenas adicionar dois blocos: um bloco `toque tambor durante (0.25) batidas`{:class="block3sound"} e um bloco `item (tamanho de sequência) de sequência`{:class="block3variables"}.

--- /hint ---

--- hint ---

Aqui estão os blocos que você precisa:

![bailarina](images/ballerina.png)

```blocks3
play drum (\(1\) Tarol v) for (0.25) beats

(item (length of [sequência v]) of [sequência v])
```

--- /hint ---

--- hint ---

Aqui está como o seu código deve ficar:

![bailarina](images/ballerina.png)

```blocks3
when flag clicked
delete (todos v) of [sequência v]
repeat (5) 
  change [sequência v] by (pick random (1) to (4))
  play drum (item (length of [sequência v]) of [sequência v]) for (0.25) beats
  switch costume to (item (length of [sequência v]) of [sequência v])
  wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---