## Melhor pontuação

Agora salva a pontuação mais alta para poderes jogar contra os teus amigos.

\--- task \--- Adiciona duas novas variáveis chamadas `melhor pontuação`{:class="block3variables"} e `nome`{:class="block3variables"} ao teu projeto \--- task \---

Quando o jogo termina porque o jogador errou a sequência, o jogo deve verificar se a pontuação é maior que a melhor pontuação atual. Se for, o jogo deve salvar a pontuação como a melhor pontuação e também guardar o nome do jogador.

\--- task \--- Adiciona código ao teu personagem actor para guardar a `melhor pontuação` {:class="block3variables"}. Pergunta também o nome do jogador e guarda-o na variável `nome`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- O teu novo código precisa seguir este padrão:

Depois da mensagem `Fim do jogo`{:class="block3looks"} `Se`{:class="block3control"} a `pontuação`{:class="block3variables"} é `maior que`{:class="block3operators"} a `melhor pontuação`{:class="block3variables"} `Define`{:class="block3variables"} a `melhor pontuação`{:class="block3variables"} como a `pontuação`{:class="block3variables"} `Perguntar`{:class="block3sensing"} pelo nome do jogador `Define`{:class="block3variables"} o `nome`{:class="block3variables"} como a `resposta`{:class="block3sensing"} \--- /hint \--- \--- hint \---

Vais precisar dos seguintes blocos:

![bailarina](images/ballerina.png)

```blocks3
se <> , então
end

(pontuaçāo)

(nome)

<[ ] > [ ]>

(a resposta)

(melhor pontuaçāo)

pergunta [Como te chamas?] e espera pela resposta

altera [melhor pontuaçāo v] para [ ]

altera [nome v] para [ ] 
```

\--- /hint \--- \--- hint \--- Aqui está o aspeto que o teu código, para quando o botão vermelho é pressionado, deve ter:

![bailarina](images/ballerina.png)

```blocks3
quando receberes a mensagem [vermelho v]
se <((1 v) de [sequência v]) = [1]> , então 
  toca a percussão ((1 v) de [sequência v]) durante (0.25) tempos
  remove (1 v) de [sequência v]
senão, 
  diz [Game over!] durante (1) s
  se <(pontuaçāo :: variables) > (melhor pontuaçāo)> , então 
    altera [melhor pontuaçāo v] para (pontuaçāo :: variables)
    pergunta [Melhor pontuaçāo! Como te chamas?] e espera
altera [nome v] para (a resposta)
end
pára [all v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

Também vais necessitar de adicionar este novo código ao personagem actor para as outras três cores!

Consegues ver que o código 'Game over' para cada uma das quatro cores é exatamente o mesmo?

![bailarina](images/ballerina.png)

```blocks3
diz [Game over!] durante (1) s
se <(pontuaçāo :: variables) > (melhor pontuaçāo)> , então 
  altera [melhor pontuaçāo v] para (pontuaçāo :: variables)
  pergunta [Melhor pontuaçāo! Como te chamas?] e espera pela resposta
altera [nome v] para (a resposta)
end
pára [all v]
```

Se precisares de alterar algum do código 'Game over', por exemplo para adicionar um som ou alterar a mensagem 'Game over', terás que alterá-lo quatro vezes. Isto é chato e desperdiça muito tempo.

Em vez disso, podes criar o teu próprio bloco de código e utilizá-lo em qualquer lugar do teu projeto.

\--- task \--- Clica em `Os meus blocos`{:class="block3myblocks"} e, de seguida, em **Criar um bloco**. Chama a este novo bloco `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \--- Adiciona o código do bloco `senão`{:class="block3control"} ligado à difusāo da mensagem `vermelho`{:class="block3events"} ao bloco `Game over `{:class="block3myblocks"} para que fique assim:

![bailarina](images/ballerina.png)

```blocks3
define Game over
diz [Game over!] durante (1) s
se <(pontuaçāo :: variables) > (melhor pontuaçāo)> , então 
  altera [melhor pontuaçāo v] para (pontuaçāo :: variables)
  pergunta [Melhor pontuaçāo! Como te chamas?] e espera pela resposta
altera [nome v] para (a resposta)
end
pára [all v]
```

\--- /task \---

\--- task \--- Agora retira o código que está no bloco `senão`{:class="block3control"} ligado à difusāo da mensagem `vermelho`{:class="block3control"} e em vez dele adiciona o bloco `Game over`{:class="block3control"}:

![bailarina](images/ballerina.png)

```blocks3
quando receberes a mensagem [vermelho v]
se <((1 v) de [sequência v]) = [1]> , então 
  toca a percussão ((1) Snare Drum v) durante (0.25) tempos
  remove (1 v) de [sequência v]
senão, 
  Game over :: custom
end
```

\--- /task \---

\--- task \--- Testa o teu novo bloco jogando o jogo e clicando no botão vermelho no ponto errado na sequência de cores. \--- /task \---

O teu novo bloco`Game over!`{:class="block3myblocks"} é uma **função**, um pequeno guiāo que podes utilizar onde quer que queiras no teu código, acrescentado o bloco `Game over!`{:class="block3myblocks"}.

\--- task \--- Substitui também o código que está no bloco `senão`{:class="block3control"} ligado à `difusāo de mensagem`{:class="block3control"} para as outras cores com o teu novo bloco `Game over!`{:class="block3control"}. Aqui está o aspeto que o código para a mensagem `azul`{:class="block3events"} deve ter

![bailarina](images/ballerina.png)

```blocks3
quando receberes a mensagem [azul v]
se <((1 v) de [sequência v]) = [1]> , então 
  toca a percussão ((1) Bass Drum v) durante (0.25) tempos
  remove (1 v) de [sequência v]
senão, 
  Game over :: custom
end
```

\--- /task \---

\--- task \--- Agora acrescenta um som que toque quando o botão errado é pressionado. Só vais necessitar acrescentar este código uma vez no bloco `Game over`{:class="block3myblocks"} que fizeste, e não quatro vezes separadas!

![bailarina](images/ballerina.png)

```blocks3
define Game over
toca o som [Cough1 v]
diz [Game over!] durante (1) s
se <(pontuaçāo :: variables) > (melhor pontuaçāo)> , então 
  toca o som (trumpet1 v)
  altera [melhor pontuaçāo v] para (pontuaçāo :: variables)
  pergunta [Melhor pontuaçāo! Como te chamas?] e espera pela resposta
altera [nome v] para (a resposta)
end
pára [all v]
```

\--- /task \---