## Repetir a sequência

Agora vais acrescentar quatro botões que o jogador deve usar para repetir a sequência de cores.

\--- task \--- Adiciona quatro novos actores ao teu projeto para representar os quatro botões.

+ Edita os trajes dos novos actores para que haja um actor trajado em cada uma das quatro cores
+ Coloca os actores no palco na mesma ordem que os figurinos: vermelho, azul, verde, amarelo

![captura de ecrã](images/colour-drums.png) \--- /task \---

\--- task \--- Adiciona código ao actor vermelho para que, quando o actor for clicado, ele `difunda a mensagem`{:class="block3events"} 'vermelho' ao personagem actor:

![tambor-vermelho](images/red_drum.png)

```blocks3
    Quando alguém clicar em ti
difunde a mensagem (vermelho v)
```

\--- /task \---

Uma `difusāo de mensagem`{:class="block3events"} é como uma informação anunciada num altifalante, que podes, por exemplo, ouvir em escolas ou supermercados. Todos os actores podem ouvir a `difusāo de mensagem`{:class="block3events"}, mas apenas o actor cujo papel é responder fará alguma coisa.

\--- task \---

Adiciona código semelhante aos actores azul, verde e amarelo para que enviem `difusões de mensagem`{:class="block3events"} com a sua própria cor.

\--- /task \---

Recordas-te que a `difusāo de mensagem`{:class="block3events"} é como uma mensagem de um altifalante? Vais acrescentar código para fazer com que seja o papel do actor personagem responder às mensagens da `difusāo de mensagem`{:class="block3events"}.

\--- task \---

Quando o teu actor personagem recebe a mensagem `vermelho`{:clas ="block3events"}, o código deve verificar se o número `1` está no início da lista da `sequência`{:class="block3variables"} ( o que significa que o `vermelho`{:class="block3events"} é a próxima cor na sequência).

Se estiver `1` no início da lista, o código deve remover o número da lista, porque o jogador acertou na cor. Caso contrário, o jogo acaba e o código necessita `parar tudo`{:class="block3control"} para terminar o jogo.

![bailarina](images/ballerina.png)

```blocks3
Quando receberes a mensagem [vermelho v]
se <((1 v) de [sequêcia v]) = [1]>, então 
 remove (1 v) de [sequêcia v]
senão, 
 diz [Game over!] durante (1) s
 pára [tudo v]
end
```

\--- /task \---

\--- task \--- Acrescenta ao código que acabaste de escrever o necessário para que também seja reproduzido o som de um tambor quando o sprite do personagem receber a correta `mensagem`{:class="block3events"}.

\--- hints \--- \--- hint \--- Pode utilizar os números que correspondem a cada cor para fazer tocar o som correto?

+ 1 = vermelho
+ 2 = azul
+ 3 = verde
+ 4 = amarelo \--- / hint \--- \--- hint \--- Acima do bloco `apaga o 1 da sequência`{:class="block3variables"}, acrescenta bloco `toca o tambor`{:class="block3variables"} para tocar o primeiro som da `sequência`{:class="block3variables"} lista.

\--- / hint \--- \--- hint \--- Aqui está o bloco de que necessitas:

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then

+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end

```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Duplica o código que utilizaste para fazer o sprite do seu personagem responder à mensagem `vermelho `{:class="block3events"}. Altera o código em duplicado de forma a que ele envie a mensagem `azul`{:class="block3events"}. \--- /task \---

Quando o sprite responde à mensagem `azul`{:class="block3events"}, qual o bit de código que deve permanecer na mesma, e qual o bit que deve mudar? Lembra-te de que cada cor tem um número correspondente.

\--- task \--- Altera o código do sprite do personagem para que o personagem responda corretamente à mensagem `azul` {:class="block3events"}.

\--- hints \--- \--- hint \---

Mantém estes blocos, mas necessitas alterá-los de alguma forma:

![bailarina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

\--- / hint \--- \--- hint \--- Aqui está o aspeto que o teu código deve ter para enviar a mensagem `azul`{:class="block3events"}.

![bailarina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[2]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    stop [all v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Duplica o código duas vezes (para os botões verde e amarelo) e altera as partes necessárias para que o personagem responda corretamente às novas `mensagens`{:class="block3events"}. \--- /task \---

Lembra-te de testar o código! Consegues memorizar uma sequência de cinco cores? A sequência é sempre diferente?

Quando o jogador repetea sequência de cores na totalidade corretamente, a lista da `sequência`{:class="block3variables"} esvazia e o jogador vence. Se quiseres, também podes acrescentar algumas luzes intermitentes como recompensa quando a lista da `sequência`{:class="block3variables"} fica vazia.

\--- task \--- Adiciona este código ao final do personagem `quando a bandeira for clicada` Script{:class="block3events"}:

![bailarina](images/ballerina.png)

```blocks3
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
```

\--- /task \---

\--- task \--- Mude para o Palco e importa a o som `drum machine` ou outro som de que gostes.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \--- Adiciona este código para reproduzir um som e fazer o cenário mudar de cor quando o jogador vence.

![bailarina](images/stage.png)

```blocks3
    when I receive [won v]
    start sound (drum machine v)
    repeat (50)
        change [color v] effect by (25)
        wait (0.1) seconds
    end
    clear graphic effects
```

\--- /task \---