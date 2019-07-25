## Múltiplos níveis

Até agora, o jogador só necessita lembrar-se de uma sequência de cinco cores. Melhora o teu jogo acrescentando uma pontuação e adicionando código para que, à medida que o jogador marcar pontos, o jogo avance para o próximo nível e a sequência de cores para lembrar se torne mais longa.

\--- task \--- Cria uma nova variável chamada `pontuaçāo`{:class="block3variables"}.

[[[generic-scratch3-add-variable] \---

Baseado na `pontuação`{: class = "block3variables"}, o jogo decidirá o comprimento da sequência de cores. Começa com uma pontuação (e um comprimento de sequência) de ` 3 `.

\--- task \--- Acrescentar um bloco no início do código do seu personagem `quando a bandeira é clicada ` {: class = "block3events"} para definir a `pontuação` {: class = "block3variables"} como ` 3 `. \--- /task \---

Em vez criar sempre uma sequência de cinco cores, agora queres que a `pontuação` {: class = "block3variables"} determine o tamanho da sequência.

\--- task \--- Altera o ciclo de `repetição` {: class = "block3control"} do personagem (para criar a sequência de cores) a repetir ` pontuação ` {: class = "block3variables"} vezes:

![sprite](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

\--- /task \---

\--- task \--- Se o jogador repetir a sequência correctamente, deves adicionar ` 1 ` à ` pontuação ` {: class = "block3variables"}, e aumenta também o comprimento da próxima sequência. Adiciona o seguinte bloco ao código do personagem ** no ponto em que sabes que a sequência está correta **:

![sprite](images/ballerina.png)

```blocks3
change [score v] by (1)
```

\--- / hints \--- \--- / hint \--- Vais saber que a sequência está correta no momento em que o jogo ` transmitir ` {: class = "block3events"} a mensagem de 'Vitória'. \--- / hint \--- \--- / hints \---

\--- /task \---

\--- task \--- Finalmente, adiciona um ` para sempre ` {: class = "block3control"} em volta do código que gera a sequência, para que o jogo crie uma nova sequência de cores em cada nível. É este o aspecto que o código do teu personagem pode ter:

![bailarina](images/ballerina.png)

```blocks3
when flag clicked
set [score v] to [3]
forever
    delete (all v) of [sequence v]
    repeat (score)
        add (pick random (1) to (4)) to [sequence v]
        switch costume to (item (length of [sequence v]) of [sequence v]
        wait (1) seconds
    end
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
    change [score v] by (1)
end
```

\--- /task \---

\--- task \--- Diz os teus amigos para testar o jogo. Lembra-te de esconder a lista da `sequência` {: class = "block3variables"} antes de jogarem! \--- / task \---