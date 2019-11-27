## Repetir a sequência

Agora vais acrescentar quatro botões que o jogador deve usar para repetir a sequência de cores.

\--- task \--- Adiciona quatro novos actores ao teu projeto para representar os quatro botões.

+ Edita os trajes dos novos actores para que haja um actor trajado em cada uma das quatro cores
+ Coloca os actores no palco na mesma ordem que os figurinos: vermelho, azul, verde, amarelo

![captura de ecrã](images/colour-drums.png) \--- /task \---

\--- task \--- Adiciona código ao actor vermelho para que, quando o actor for clicado, ele `difunda a mensagem`{:class="block3events"} 'vermelho' ao personagem actor:

![tambor-vermelho](images/red_drum.png)

```blocks3
    quando alguém clicar em ti
difunde a mensagem (vermelho v)
```

\--- /task \---

Uma `difusāo de mensagem`{:class="block3events"} é como uma informação anunciada num altifalante, que podes, por exemplo, ouvir em escolas ou supermercados. Todos os actores podem ouvir a `difusāo de mensagem`{:class="block3events"}, mas apenas o actor cujo papel é responder fará alguma coisa.

\--- task \---

Adiciona código semelhante aos actores azul, verde e amarelo para que enviem `difusões de mensagem`{:class="block3events"} com a sua própria cor.

\--- /task \---

Recordas-te que a `difusāo de mensagem`{:class="block3events"} é como uma mensagem de um altifalante? Vais acrescentar código para fazer com que seja o papel do actor personagem responder às mensagens da `difusāo de mensagem`{:class="block3events"}.

\--- task \---

Quando o teu actor personagem recebe a mensagem `vermelho`{:class ="block3events"}, o código deve verificar se o número `1` está no início da lista da `sequência`{:class="block3variables"} ( o que significa que o `vermelho`{:class="block3events"} é a próxima cor na sequência).

Se estiver `1` no início da lista, o código deve remover o número da lista, porque o jogador acertou na cor. Caso contrário, o jogo acaba e o código necessita `parar tudo`{:class="block3control"} para terminar o jogo.

![bailarina](images/ballerina.png)

```blocks3
quando receberes a mensagem [vermelho v]
se <((1 v) de [sequêcia v]) = [1]>, então 
 remove (1 v) de [sequêcia v]
senão, 
 diz [Game over!] durante (1) s
 pára [tudo v]
end
```

\--- /task \---

\--- task \--- Acrescenta ao código que acabaste de escrever o necessário para que também seja reproduzido o som de um tambor quando o personagem do actor receber a `difusāo de mensagem`{:class="block3events"} correta.

\--- hints \--- \--- hint \--- Podes utilizar os números que correspondem a cada cor para fazer tocar o som correto?

+ 1 = vermelho
+ 2 = azul
+ 3 = verde
+ 4 = amarelo \--- / hint \--- \--- hint \--- Acima do bloco `apaga o 1 da sequência`{:class="block3variables"}, acrescenta o bloco `toca o tambor`{:class="block3variables"} para tocar o primeiro som da lista `sequência`{:class="block3variables"}.

\--- / hint \--- \--- hint \--- Aqui está o código de que necessitas:

```blocks3
quando receberes a mensagem [red v]
se <(item (1 v) de [sequence v]) = [1]> então 
+ toca a percussão ((1) Snare Drum v) durante (0.25) tempos
remove (1 v) de [sequence v]
senão, 
diz [Game over!] durante (1) s
pára [all v]
end<

```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Duplica o código que utilizaste para fazer o actor do teu personagem responder à mensagem `vermelho `{:class="block3events"}. Altera o código duplicado de forma a que ele envie a mensagem `azul`{:class="block3events"}. \--- /task \---

Quando o actor responde à mensagem `azul`{:class="block3events"}, qual a parte do código deve permanecer a mesma, e qual o código que deve mudar? Lembra-te de que cada cor tem um número correspondente.

\--- task \--- Altera o código do personagem do actor para que o personagem responda corretamente à mensagem `azul` {:class="block3events"}.

\--- hints \--- \--- hint \---

Mantém estes blocos, mas necessitas alterá-los de alguma forma:

![bailarina](images/ballerina.png)

```blocks3
<((1 v) de [sequence v]) = [1]>

Quando receberes a mensagem [red v]

toca a percussão ((1) Snare Drum v) durante (0.25) tempos
```

\--- /hint \--- \--- hint \--- Aqui está o aspeto que o teu código deve ter para difundir a mensagem `azul`{:class="block3events"}.

![bailarina](images/ballerina.png)

```blocks3
quando receberes a mensagem [blue v]
se <((1 v) de [sequence v]) = [2]>, então 
  toca a percussão ((2) Bass Drum v) durante (0.25) tempos
  remove (1 v) de [sequence v]
senão, 
  diz [Game over!] durante (1) s
  pára [all v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Duplica o código mais duas vezes (para os botões verde e amarelo) e altera as partes necessárias para que o personagem responda corretamente às novas `difusões de mensagem`{:class="block3events"}. \--- /task \---

Lembra-te de testar o código! Consegues memorizar uma sequência de cinco cores? A sequência é sempre diferente?

Quando o jogador repete corretamente a sequência de cores na totalidade, a lista da `sequência`{:class="block3variables"} esvazia e o jogador vence. Se quiseres, também podes acrescentar algumas luzes intermitentes como recompensa quando a lista da `sequência`{:class="block3variables"} fica vazia.

\--- task \--- Adiciona este código ao final do guiāo `quando a bandeira for clicada`{:class="block3events"} do teu personagem:

![bailarina](images/ballerina.png)

```blocks3
    espera até que <(o comprimento de [sequence v]) = [0]>
difunde a mensagem (ganhou v) e espera
```

\--- /task \---

\--- task \--- Muda para o Palco e importa o som `drum machine` ou outro som de que gostes.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \--- Adiciona este código para reproduzir um som e fazer o cenário mudar de cor quando o jogador vence.

![bailarina](images/stage.png)

```blocks3
    quando receberes a mensagem [ganhou v]
toca o som (drum machine v)
repete (50) vezes 
  adiciona ao teu efeito [color v] o valor (25)
  espera (0.1) s
end
cancela os teus efeitos gráficos
```

\--- /task \---