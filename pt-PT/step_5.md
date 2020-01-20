## Múltiplos níveis

Até agora, o jogador só necessita de se lembrar de uma sequência de cinco cores. Melhora o teu jogo acrescentando uma pontuação e adicionando código para que, à medida que o jogador marcar pontos, o jogo avance para o próximo nível e a sequência de cores para lembrar se torne mais longa.

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
repete (pontuação :: variáveis) vezes
end
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
adiciona a [pontuação v] o valor (1)
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
quando alguém clicar na bandeira verde
altera [pontuaçāo v] para [3]
repete para sempre 
  remove (all v) de [sequência v]
  repete (pontuaçāo) vezes 
    acrescenta (um valor ao acaso entre (1) e (4)) a [sequência v]
    muda o teu traje para ((o comprimento de [sequência v]) de [sequência v])
    espera (1) s
  end
  espera até que <(o comprimento de [sequência v]) = [0]>
  difunde a mensagem (ganhou v) e espera
  adiciona a [pontuaçāo v] o valor (1)
end
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---