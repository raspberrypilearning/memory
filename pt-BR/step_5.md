## Múltiplos níveis

Até agora, o jogador só precisava lembrar de uma sequência de cinco cores. Melhore seu jogo adicionando uma pontuação e adicionando código para que, à medida que o jogador ganha pontos, o jogo vai para o próximo nível e a sequência de cores para lembrar se torne mais longa.

\--- task \---

Create a new variable called `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \---

Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`.

\--- /task \---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \---

Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
repita (pontuação :: variáveis) vezes
fim
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
adicione a [placar v] (1)
```

\--- hints \---

\--- hint \---

You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks3
quando ⚑ for clicado
mude [pontuação v] para [3]
sempre 
  apague (todos v) de [sequência v]
  repita (pontuação) vezes 
    adicione (número aleatório entre (1) e (4)) a [sequência v]
    mude para a fantasia (item (tamanho de [sequência v]) de [sequência v])
    espere (1) seg
  fim
  espere até que <(tamanho de [sequência v]) = [0]>
  transmita (ganhou v) e espere
  adicione (1) a [pontuação v]
fim
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---