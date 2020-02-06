## Múltiplos níveis

Até agora, o jogador só precisava lembrar de uma sequência de cinco cores. Melhore seu jogo adicionando uma pontuação e adicionando código para que, à medida que o jogador ganha pontos, o jogo vai para o próximo nível e a sequência de cores para lembrar se torne mais longa.

\--- task \---

Crie uma nova variável chamada de `pontuação`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Com base na `pontuação`{:class="block3variables"}, o jogo decidirá o comprimento da sequência de cores. Comece com uma pontuação (e um comprimento de sequência) de `3`.

\--- task \---

Acrescentar um bloco no início do código do seu personagem `quando a bandeira é clicada`{:class="block3events"} para definir a `pontuação`{:class="block3variables"} como `3`.

\--- /task \---

Em vez criar sempre uma sequência de cinco cores, agora você quer que a `pontuação`{:class="block3variables"} determine o tamanho da sequência.

\--- task \---

Mude o laço de `repetição`{:class="block3control"} do ator (para criar a sequência de cores) para repetir `pontuação`{:class="block3variables"} vezes:

![ator](images/ballerina.png)

```blocks3
repita (pontuação :: variáveis) vezes
fim
```

\--- /task \---

\--- task \---

Se o jogador repetir a sequência corretamente, você deve adicionar `1` a `pontuação`{:class="block3variables"}, e ao fazê-lo aumenta também o comprimento da próxima sequência. Adicione o seguinte bloco ao código do personagem **no ponto em que sabes que a sequência está correta**:

![ator](images/ballerina.png)

```blocks3
adicione a [placar v] (1)
```

\--- hints \---

\--- hint \---

Você sabe que a sequência está correta quando o jogo `transmitir`{:class="block3events"} a mensagem de 'ganhou'.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Finalmente, adicione um `para sempre`{:class="block3control"} em volta do código que gera a sequência, para que o jogo crie uma nova sequência de cores em cada nível. É assim que o código do seu personagem deve ficar:

![bailarina](images/ballerina.png)

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

Chame seus amigos para testarem o seu jogo. Lembre-se de esconder a lista da `sequência`{:class="block3variables"} antes de jogarem!

\--- /task \---