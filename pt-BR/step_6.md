## Múltiplos níveis

Até agora, o jogador só precisava lembrar de uma sequência de cinco cores. Vamos melhorar o jogo, implementando um placar, e adicionando código para que enquanto aumenta a pontuação, a quantidade de cores que o jogador precisa lembrar vai aumentando também.

+ Crie uma nova variável chamada `placar`{:class="blockdata"}.

[[[generic-scratch-add-variable]]]

O `placar`{:class="blockdata"} será usado para determinar o tamanho da sequência que o jogador deve memorizar. Vamos começar com um placar (e tamanho da sequência) de `3`.

+ Adicione este código no início do bloco de código `quando clicar em bandeira verde`{:class="blockevents"} do seu personagem, este código vai definir o `placar`{:class="blockdata"} inicial do jogo em `3`.

Em vez de sempre criar uma sequência de cinco cores, agora você terá o `placar`{:class="blockdata"} para determinar o tamanho da sequência.

+ Alterar o bloco de repetição `repita (5) vezes`{:class="blockcontrol"} usado na personagem bailarina que cria a atual sequência, pelo bloco `repita (placar) vezes`{:class="blockdata"}:

```blocks
    repita (placar) vezes
   fim
```

+ Se a sequência for lembrada corretamente, você deve adicionar `1` para o placar para aumentar o comprimento da próxima seqüência. Adicione este bloco ao código do personagem **quando a sequência for lembrada corretamente**.

```blocks
    adicione a [placar v] (1)
```

\--- hints \--- \--- hint \--- Se a sequência foi lembrada corretamente, você deve transmitir a mensagem de vitória `VITÓRIA!!!`. \--- /hint \--- \--- /hints \---

+ Finalmente, você precisa adicionar o bloco `sempre`{:class="blockcontrol"} englobando todo o código que gera a sequência, para que uma nova sequência seja criada para cada nível. É assim que o código do seu personagem deve ficar:
    
    ```blocks
        quando clicar em bandeira verde
       mude [placar v] para [3]
       sempre
          apague (todos v) de [sequencia v]
          repita (placar) vezes
             insira (número aleatório entre (1) e (4)) a [sequencia v]
             mude para a fantasia (item (último v) de [sequencia v])
             espere (1) seg
          fim
          espere até <(tamanho de [sequencia v]:: list)=[0]>
          envie [VITÓRIA!!! v] a todos e espere
          adicione a [placar v] (1)
       fim
    ```

+ Chame seus amigos para testar seu jogo. Lembre-se de esconder a lista `sequencia`{:class="blockdata"} antes de jogar!