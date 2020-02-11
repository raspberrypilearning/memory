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
toque instrumento (\(1\) Tarol v) por (0.25) batidas

(item (tamanho de [sequência v]) de [sequência v])
```

--- /hint ---

--- hint ---

Aqui está como o seu código deve ficar:

![bailarina](images/ballerina.png)

```blocks3
quando ⚑ for clicado
apague (todos v) de [sequência v]
repita (5) vezes 
  adicione (número aleatório entre (1) e (4)) a [sequência v]
  toque instrumento (item (tamanho de [sequência v]) de [sequência v]) por (0.25) batidas
  mude para a fantasia (item (tamanho de [sequência v]) de [sequência v])
  espere (1) seg
fim
```

--- /hint ---

--- /hints ---

--- /task ---