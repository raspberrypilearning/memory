## Melhor pontuação

Agora salva a pontuação mais alta para poderes jogar contra os teus amigos.

\--- task \--- Cria duas novas variáveis chamadas `melhor pontuação`{:class="block3variables"} e `nome`{:class="block3variables"} ao teu projeto \--- task \---

Quando o jogo termina porque o jogador percebe a sequência de forma errada, o jogo deve verificar se a pontuação é maior do que a melhor pontuação atual. Se for, o jogo deve salvar a pontuação como a melhor pontuação e também armazenar o nome do jogador.

\--- task \--- Adiciona o código ao sprite do seu personagem para armazenar o `melhor pontuação` {:class="block3variables"}. Pede também o nome do jogador e guarda-o na variável `nome`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- O teu novo código precisa seguir este padrão:

Depois da mensagem `Fim do jogo`{:class="block3looks"} `Se`{:class="block3control"} a `pontuação`{:class="block3variables"} é `maior que`{:class="block3operators"} a `melhor pontuação`{:class="block3variables"} `Define`{:class="block3variables"} a `melhor pontuação`{:class="block3variables"} como a `pontuação`{:class="block3variables"} `Perguntar`{:class="block3sensing"} pelo nome do jogador `Define`{:class="block3variables"} o `nome`{:class="block3variables"} como a `resposta`{:class="block3sensing"} \--- /hint \--- \--- hint \---

Vais precisar dos seguintes blocos:

![bailarina](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```

\--- / hint \--- \--- hint \--- Aqui está o aspeto que o teu código para quando o botão vermelho é pressionado deve ter:

![bailarina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (high score) > then
        set [high score v] to (score :: variables)
        ask [High score! What is your name?] and wait
        set [name v] to (answer)
    end
    stop [all v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

Vais necessitar de adicionar este novo código ao sprite do personagem para as outras três cores também!

Consegues ver que o código 'Game over' para cada uma das quatro cores é exatamente o mesmo?

![bailarina](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

Se precisares de alterar qualquer código 'Game over', por exemplo, para adicionar um som ou alterar a mensagem 'Fim do jogo', terás que alterá-lo quatro vezes. Isto é chato e desperdiça muito tempo.

Em vez disso, podes criar o teu próprio bloco de código e utilizá-lo em qualquer lugar do teu projeto.

\--- task \--- Clique em `Os meus blocos`{:class="block3myblocks"} e, de seguida, em **Fazer um bloco**. Chama a este novo bloco `Fim do jogo`{:class="block3myblocks"}.

\--- /task \---

\--- task \--- Adiciona o código do bloco `senão`{:class="block3control"} ligado à mensagem `vermelho`{:class="block3events"} ao bloco `Fim do jogo`{:class="block3myblocks"} para que fique assim:

![bailarina](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---

\--- task \--- Agora retira o código que está no bloco `senão`{:class="block3control"} ligado à mensagem `vermelho`{:class="block3control"} e acrescenta-o ao bloco `Fim do jogo`{:class="block3control"} para que fique assim:

![bailarina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \--- Testa o teu novo bloco jogando o jogo e clicando no botão vermelho no ponto errado na sequência de cores. \--- / task \---

O teu novo bloco`Fim do Jogo`{:class="block3myblocks"} é uma **função**, um pequeno script que você podes utilizar onde quer que queiras no teu código, acrescentado o bloco `Fim do Jogo`{:class="block3myblocks"}.

\--- task \--- Substutui também o código que está no bloco `senão`{:class="block3control"} ligado à mensagem `vermelho`{:class="block3control"} e acrescenta-o ao bloco `Fim do jogo`{:class="block3control"} para que fique assim. Aqui está o aspeto que o código para a mensagem `azul`{:class="block3events"} deve ter

![bailarina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \--- Agora acrescenta um som que toque quando o botão errado é pressionado. Só vais necessitar acrescentar este código uma vez no bloco `Fim do Jogo`{:class="block3myblocks"} que fizeste, e não quatro vezes separadas!

![bailarina](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---