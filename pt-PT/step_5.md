## Múltiplos níveis

Até agora, o jogador só necessita de se lembrar de uma sequência de cinco cores. Melhora o teu jogo acrescentando uma pontuação e adicionando código para que, à medida que o jogador marcar pontos, o jogo avance para o próximo nível e a sequência de cores para lembrar se torne mais longa.

\--- task \--- Cria uma nova variável chamada `pontuaçāo`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

Baseado na `pontuação`{:class="block3variables"}, o jogo decidirá o comprimento da sequência de cores. Começa com uma pontuação (e um comprimento de sequência) de ` 3 `.

\--- task \--- Acrescentar um bloco no início do código do seu personagem `quando a bandeira é clicada ` {:class = "block3events"} para definir a `pontuação` {:class = "block3variables"} como ` 3 `. \--- /task \---

Em vez criar sempre uma sequência de cinco cores, agora queres que a `pontuação` {:class = "block3variables"} determine o tamanho da sequência.

\--- task \--- Altera o ciclo de `repetição` {:class = "block3control"} do personagem (para criar a sequência de cores) a repetir ` pontuação ` {:class = "block3variables"} vezes:

![actor](images/ballerina.png)

```blocks3
repete (pontuação :: variáveis) vezes
end
```

\--- /task \---

\--- task \--- Se o jogador repetir a sequência correctamente, deves adicionar ` 1 ` à ` pontuação ` {:class = "block3variables"}, e ao fazê-lo aumenta também o comprimento da próxima sequência. Adiciona o seguinte bloco ao código do personagem ** no ponto em que sabes que a sequência está correta **:

![actor](images/ballerina.png)

```blocks3
adiciona a [pontuação v] o valor (1)
```

\--- hints \--- \--- hint \--- Sabes que a sequência está correta quando o jogo ` difundir ` {:class = "block3events"} a mensagem de 'ganhou'. \--- /hint \--- \--- /hints \---

\--- /task \---

\--- task \--- Finalmente, adiciona um ` para sempre ` {:class = "block3control"} em volta do código que gera a sequência, para que o jogo crie uma nova sequência de cores em cada nível. É assim que o código do teu personagem pode ficar:

![bailarina](images/ballerina.png)

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

\--- task \--- Diz os teus amigos para testarem o teu jogo. Lembra-te de esconder a lista da `sequência` {:class = "block3variables"} antes de jogarem! \--- /task \---