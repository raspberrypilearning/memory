## Cria uma sequência de cores

Primeiro cria um personagem que possa exibir uma sequência aleatória de cores.

\--- Abre um projeto Scratch novo.

**Online:** abre um novo projeto online Scratch em [rpf.io/scratch-new](https://rpf.io/scratchon){:target="_blank.

**Offline:** abre um novo projeto no editor offline.

Se precisares de descarregar e instalar o editor offline do Scratch, podes encontrá-lo em [rpf.io/scratchoff](https://rpf.io/scratchoff).

\--- /task \---

\--- task \--- Escolhe um ator e um palco. Podes utilizar a bailarina, mas o personagem não tem que ser uma pessoa, só precisa ser capaz de mostrar cores diferentes.

![captura de ecrã](images/colour-sprite.png) \--- /task \---

+ O teu jogo deve usar um número diferente para representar cada cor:
    
    + 1 = vermelho
    + 2 = azul
    + 3 = verde
    + 4 = amarelo

\--- task \--- Dá ao teu personagem quatro trajes com cores diferentes, um traje para cada uma das quatro cores acima indicadas. Certifica-te que as roupas coloridas estão na mesma ordem da lista acima.

![captura de ecrã](images/colour-costume.png) \--- /task \---

Se quiseres, podes utilizar a ferramenta ** color a shape ** para preencher partes do traje com uma cor diferente.

![preenche-a-forma](images/color-a-shape.png)

De seguida, acrescenta uma lista para armazenar a sequência aleatória de cores que o jogador deve memorizar.

\--- task \--- Cria uma lista chamada ` sequência ` {: class = "block3variables"}. Apenas o actor necessita ver esta lista, por isso seleciona **Apenas para este actor** quando criares a lista.

[[[generic-scratch3-make-list]]]

\--- /task \---

Agora já deves ver muitos novos blocos de código para utilizar com listas. A lista vazia deve estar visível no canto superior esquerdo do Palco.

![captura de ecrã](images/colour-list-blocks-annotated.png)

Como cada cor tem um número diferente, podes escolher uma cor aleatória escolhendo aleatoriamente um número e adicionando-o à lista.

\--- task \--- Adicione este código ao sprite para escolher um número aleatório e adicioná-lo à `sequência` {: class = "block3variables"}:

![bailarina](images/ballerina.png)

```blocks3
Quando alguém clicar na bandeira verde
acrescenta (um valor ao acaso entre (1) e (4)) a [sequencia v]
```

\--- /task \---

\--- task \--- Testa o teu código. Verifica se, de cada vez que clicas na bandeira, um número aleatório entre 1 e 4 é adicionado à lista. \--- / task \---

\--- task \--- Consegues adicionar código ao teu programa para gerar cinco números aleatórios de uma só vez?

\--- hints \--- \--- hint \--- Acrescenta `apaga a sequência`{:class="block3variables"} para primeiro apagar todos os itens na lista, e depois um bloco `repetir`{:class="block3control"} que acrescente cinco números aleatórios à lista. \--- /hint \--- \--- hint \---

Este é o aspeto que o teu código deve ter:

![bailarina](images/ballerina.png)

```blocks3
Quando alguém clicar na bandeira verde
remove (tudo v) de [sequência v]
repete (5) vezes 
  acrescenta (um valor ao acaso entre (1) e (4)) a [sequência v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- De cada vez que um número é acrescentado à lista, o actor deve mudar o seu traje para que a cor do traje corresponda ao número acrescentado. Coloca estes blocos no teu código imediatamente abaixo de onde um número aleatório é adicionado à `sequência`{:class="block3variables"}:

![bailarina](images/ballerina.png)

```blocks3
muda o teu traje para ((o comprimento de [sequência v]) de [sequência v])
espera (1) s
```

\--- /task \---