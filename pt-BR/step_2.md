## Crie uma sequência de cores

Primeiro, crie uma entidade que possa exibir uma sequência aleatória de cores.

\--- task \--- Abra um novo projeto do Scratch.

**Online**: abra um novo projeto online de Scratch em [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Offline**: abra um novo projeto no editor offline.

Se você precisa baixar e instalar o editor offline do Scratch, você pode encontra-lo em [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}.

\--- /task \---

\--- task \--- Escolhe um ator e um cenário. Você pode utilizar a bailarina, mas a entidade não tem que ser uma pessoa, só precisa ser capaz de mostrar cores diferentes.

![screenshot](images/colour-sprite.png) \--- /task \---

+ Seu jogo deve usar um número diferente para representar cada cor:
    
    + 1 = vermelho
    + 2 = azul
    + 3 = verde
    + 4 = amarelo

\--- task \--- Dê ao seu ator quatro fantasias que tenham cores diferentes, uma fantasia para cada uma das quatro cores mostradas acima. Certifique-se de que suas fantasias coloridas estão na mesma ordem que a lista acima.

![screenshot](images/colour-costume.png) \--- /task \---

Se você quiser, você pode usar a ferramenta **preencher** para colorir partes da fantasia com uma cor diferente.

![colorir-uma-forma](images/color-a-shape.png)

Em seguida, adicione uma lista para armazenar a sequência aleatória de cores que o jogador tem que lembrar.

\--- task \--- Crie uma lista chamada `sequência`{:class="block3variables"}. Apenas o ator precisa ver a lista, então você pode selecionar **Para este ator apenas** quando você criar a lista.

[[[generic-scratch3-make-list]]]

\--- /task \---

Agora você já deve ver muitos blocos novos de código para utilizar com listas. A lista vazia deve estar visível no canto superior esquerdo do Palco.

![screenshot](images/colour-list-blocks-annotated.png)

Cada cor tem um número diferente, você pode escolher uma cor aleatória escolhendo aleatoriamente um número e adicionando-a à lista.

\--- task \--- Adiciona este código ao ator para escolher um número aleatório e adicioná-lo a `sequência`{:class="block3variables"}:

![bailarina](images/ballerina.png)

```blocks3
quando clicar em bandeira verde
insira (número aleatório entre (1) e (4)) a [sequência v]
```

\--- /task \---

\--- task \--- Teste seu código. Verifique que, a cada vez que você clica na bandeira, um número aleatório entre 1 e 4 é adicionado à lista. \--- /task \---

\--- task \--- Você consegue adicionar código ao seu programa para gerar cinco números aleatórios de uma só vez?

\--- hints \--- \--- hint \--- Adicione um `apague todos os itens da sequência`{:class="block3variables"} para primeiro apagar todos os itens na lista, depois adicione um bloco `repetir`{:class="block3control"} que acrescente cinco números aleatórios à lista. \--- /hint \--- \--- hint \---

É assim que seu código deve parecer:

![bailarina](images/ballerina.png)

```blocks3
quando clicar em bandeira verde
apague (todos v) de [sequência v]
repita (5) vezes
   insira (número aleatório entre (1) e (4)) a [sequência v]
fim
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Cada vez que um número é adicionado à lista, o personagem deve mudar sua fantasia para que a cor da fantasia corresponda ao número. Coloque estes blocos no seu código imediatamente abaixo onde um número aleatório é adicionado a `sequência`{:class="block3Varible"}:

![bailarina](images/ballerina.png)

```blocks3
mude para a fantasia (item (tamanho de [sequência v]) de [sequência v])
espere (1) seg
```

\--- /task \---