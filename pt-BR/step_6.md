## Recorde

Agora salve a pontuação mais alta para poder jogar contra seus amigos.

--- task ---

Adicione duas novas variáveis chamadas `pontuação mais alta`{:class="block3variables"} e `nome`{:class="block3variables"} ao seu projeto.

--- /task ---

Quando o jogo termina porque o jogador errou a sequência, o jogo deve verificar se a pontuação é maior que a melhor pontuação atual. Se for, o jogo deve salvar a pontuação como a pontuação mais alta e também guardar o nome do jogador.

--- task ---

Adicione um código ao seu ator para guardar a `pontuação mais alta`{:class="block3variables"}. Peça também o nome do jogador e guarde-o na variável `nome`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

--- hints ---


--- hint ---

Seu novo código precisa seguir este padrão:

Depois da mensagem `Fim do jogo`{:class="block3looks"} `Se`{:class="block3control"} a `pontuação`{:class="block3variables"} é `maior que`{:class="block3operators"} a `pontuação mais alta`{:class="block3variables"} `Define`{:class="block3variables"} a `pontuação mais alta`{:class="block3variables"} como a `pontuação`{:class="block3variables"} `Perguntar`{:class="block3sensing"} pelo nome do jogador `Define`{:class="block3variables"} o `nome`{:class="block3variables"} como a `resposta`{:class="block3sensing"}

--- /hint ---

--- hint ---

Você precisa dos seguintes blocos:

![bailarina](images/ballerina.png)

```blocks3
se < > então
fim

(pontuação)

(pontuação)

[ ] > [ ]

resposta

(pontuação mais alta)

pergunte [Qual é o seu nome?] e espere

mude [pontuação mais alta v] para [ ]

mude [nome v] para [ ] 
```

--- /hint ---

--- hint ---

Veja como o seu código deve ficar para quando o tambor vermelho for pressionado:

![bailarina](images/ballerina.png)

```blocks3
quando eu receber [vermelho v]
se <(item (1 v) de [sequência v]) = [1]> então 
  toque instrumento (item (1 v) de [sequência v]) por (0.25) batidas
  apague (1 v) de [sequência v]
senão 
  diga [Fim de jogo!] por (1) segundos
  se <(pontuação :: variáveis) > (pontuação mais alta) > então 
    mude [pontuação mais alta v] para (pontuação :: variáveis)
    pergunte [Maior pontuação! Qual é o seu nome?] e espere
    mude [nome v] para (resposta)
  fim
  pare [todos v]
fim
```

--- /hint ---

--- /hints ---

--- /task ---

Você precisa adicionar esse novo código ao ator para as outras três cores também!

Você consegue ver que o código 'Fim de jogo' para cada uma das quatro cores é exatamente o mesmo?

![bailarina](images/ballerina.png)

```blocks3
diga [Fim de jogo!] por (1) segundos
se < (pontuação :: variáveis) > (pontuação mais alta) > então 
  mude [pontuação mais alta v] para (pontuação :: variáveis)
  pergunte [Pontuação mais alta! Qual é o seu nome?] e espere
mude [nome v] para (resposta)
fim
pare [todos v]
```

Se precisar alterar alguma parte do código por exemplo, do 'Fim de jogo' para adicionar um som ou alterar a mensagem 'Fim de jogo', terá que alterá-lo quatro vezes. Isto é chato e desperdiça muito tempo.

Em vez disso, você pode criar o teu próprio bloco de código e utilizá-lo em qualquer lugar do seu projeto.

--- task ---

Clique em `Meus blocos`{:class="block3myblocks"}, em seguida em **Criar um bloco**. Chame esse novo bloco de `Fim de jogo`{:class="block3myblocks"}.

--- /task ---

--- task ---

Adicione o código do bloco `senão`{:class="block3control"} ligado à transmissão da mensagem `vermelho`{:class="block3events"} ao bloco `Fim de jogo`{:class="block3myblocks"} para que fique assim:

![bailarina](images/ballerina.png)

```blocks3
defina Fim de jogo
diga [Fim de jogo!] por (1) segundos
se < (pontuação :: variáveis) > (pontuação mais alta) > então 
  mude [pontuação mais alta v] para (pontuação :: variáveis)
  pergunte [Maior pontuação! Qual é o seu nome?] e espere
    mude [nome v] para (resposta)
  fim
  pare [todos v]
```

--- /task ---

--- task ---

Agora remova o código que está no bloco `senão`{:class="block3control"} ligado à transmissão da mensagem `vermelho`{:class="block3control"} e em vez dele adicione o bloco `Fim de jogo`{:class="block3control"}:

![bailarina](images/ballerina.png)

```blocks3
quando eu receber [vermelho v]
se < (item (1 v) de [sequência v]) = [1] > então 
  toque instrumento ((1) Tarol v) por (0.25) batidas
  apague (1 v) de [sequência v]
senão 
  Fim de jogo :: personalizado
fim
```

--- /task ---

--- task ---

Teste seu novo bloco jogando o jogo e clicando no botão vermelho no ponto errado na sequência de cores.

--- /task ---

Seu novo bloco`Fim de jogo`{:class="block3myblocks"} é uma **função**, um pequeno conjunto de instruções que podes utilizar onde quiser no seu código, acrescentado o bloco `Fim de jogo`{:class="block3myblocks"}.

--- task ---

Substitua também o código que está no bloco `senão`{:class="block3control"} ligado à `transmissão de mensagem`{:class="block3control"} para as outras cores com o seu novo bloco `Fim de jogo`{:class="block3control"}. Aqui está o código de como a mensagem `azul`{:class="block3events"} deve parecer

![bailarina](images/ballerina.png)

```blocks3
quando eu receber [azul v]
se < (item (1 v) de [sequência v]) = [1] > então 
  toque instrumento ((2) Bumbo v) por (0.25) batidas
  apague (1 v) de [sequência v]
senão 
  Fim de jogo :: personalizado
fim
```

--- /task ---

--- task ---

Agora adicione um som que toque quando o botão errado é pressionado. Você só precisa adicionar este código uma vez no bloco `Fim de jogo`{:class="block3myblocks"} que você fez, e não quatro vezes separadas!

![bailarina](images/ballerina.png)

```blocks3
defina Fim de jogo
toque o som [Cough1 v]
diga [Fim de jogo!] por (1) segundos
se < (pontuação :: variáveis) > (pontuação mais alta) > então 
  toque o som (trumpet1 v)
  mude [pontuação mais alta v] para (pontuação)
  pergunte [Pontuação mais alta! Qual é o seu nome?] e espere
mude [nome v] para (resposta)
fim
pare [todos v]
```

--- /task ---