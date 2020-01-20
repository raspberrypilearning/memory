## Desafio: Adicionando som

Agora você vai acrescentar quatro botões que o jogador deve usar para repetir a sequência de cores.

\--- task \---

Add four new sprites to your project to represent the four buttons.

+ Edite as fantasias dos novos atores para que haja um ator fantasiado em cada uma das quatro cores
+ Coloque os atores no palco na mesma ordem que as fantasias: vermelho, azul, verde, amarelo

![screenshot](images/colour-drums.png)

\--- /task \---

\--- task \---

Add code to the red sprite so that, when the sprite is clicked, it `broadcasts`{:class="block3events"} a 'red' message to the character sprite:

![red-drum](images/red_drum.png)

```blocks3
    quando este ator for clicado
transmita (vermelho v)
```

\--- /task \---

A `broadcast`{:class="block3events"} is like a message announced over a loudspeaker, which you can for example hear in schools or supermarkets. All of the sprites can hear the `broadcast`{:class="block3events"}, but only the sprite whose job it is to respond will do something.

\--- task \---

Add similar code to the blue, green, and yellow sprites to make them `broadcast`{:class="block3events"} messages about their own colour.

\--- /task \---

Do you remember that the `broadcast`{:class="block3events"} is like a loudspeaker message? You will add code to make it the character sprite's job to respond to the `broadcast`{:class="block3events"} messages.

\--- task \---

When your character sprite receives the message `red`{:class="block3events"}, the code should check whether the number `1` is at the start of the `sequence`{:class="block3variables"} list (which means that `red`{:class="block3events"} is the next colour in the sequence).

If `1` is at the start of the list, the code should remove the number from the list, because the player remembered the correct colour. Otherwise it's game over, and the code needs to `stop all`{:class="block3control"} to end the game.

![ballerina](images/ballerina.png)

```blocks3
quando eu receber [vermelho v]
se <(item (1 v) de [sequência v]) = [1]> então 
 apague (1 v) de [sequência v]
senão 
 diga [Fim de jogo!] por (1) segundos
 pare [todos v]
fim
```

\--- /task \---

\--- task \---

Add to the code you just wrote so that a drum beat also plays when the character sprite receives the correct `broadcast`{:class="block3events"}.

\--- hints \---

\--- hint \---

Can you use the numbers that correspond to each colour to play the correct drum beat?

+ 1 = vermelho
+ 2 = azul
+ 3 = verde
+ 4 = yellow

\--- /hint \---

\--- hint \---

Above the `delete 1 of sequence`{:class="block3variables"} block, add the `play drum`{:class="block3sound"} block to play the first sound in the `sequence`{:class="block3variables"} list.

\--- /hint \---

\--- hint \---

Here is the code you will need to add:

```blocks3
quando eu receber [vermelho v]
se <(item (1 v) de [sequência v]) = [1]> então 
 + toque instrumento ((1) Tarol v) por (0.25) batidas
 apague (1 v) de [sequência v]
senão 
 diga [Fim de jogo!] por (1) segundos
 pare [todos v]
fim
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code you used to make your character sprite respond to the message `red`{:class="block3events"}. Change the duplicated code so that it sends the message `blue`{:class="block3events"}.

\--- /task \---

When the sprite responds to the message `blue`{:class="block3events"}, which bit of code should stay the same, and which bit should change? Remember that each colour has a corresponding number.

\--- task \---

Change the character sprite's code so that the character responds correctly to the `blue`{:class="block3events"} message.

\--- hints \---

\--- hint \---

Keep these blocks, but you need to change them in some way:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) de [sequência v]) = [1]>

quando eu receber [vermelho v]

toque instrumento ((1) Tarol v) por (0.25) batidas
```

\--- /hint \---

\--- hint \---

Here is how your code should look for the `blue`{:class="block3events"} broadcast.

![ballerina](images/ballerina.png)

```blocks3
quando eu receber [azul v]
se <(item (1 v) de [sequência v]) = [2]> então 
  toque instrumento ((2) Bumbo v) por (0.25) batidas
  apague (1 v) de [sequência v]
senão 
  diga [Fim de jogo!] por (1) segundos
  pare [todos v]
fim
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code again twice (for the green and yellow buttons), and change the necessary parts so that the character responds correctly to the new `broadcasts`{:class="block3events"}.

\--- /task \---

Remember to test the code! Can you memorise a sequence of five colours? Is the sequence different each time?

When the player repeats the whole colour sequence correctly, the `sequence`{:class="block3variables"} list emtpy and the player wins. If you want, you can also display some flashing lights as a reward once the `sequence`{:class="block3variables"} list is empty.

\--- task \---

Add this code to the end of your character's `when flag clicked`{:class="block3events"} script:

![ballerina](images/ballerina.png)

```blocks3
    espere até que <(tamanho de [sequência v]) = [0]>
transmita (ganhou v) e espere
```

\--- /task \---

\--- task \---

Switch to the Stage, and import the `drum machine` sound or another sound you like.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \---

Add this code to play a sound and make the backdrop change colour when the player wins.

![ballerina](images/stage.png)

```blocks3
    quando eu receber [ganhou v]
toque o som (bateria eletrônica v)
repita (50) vezes 
  mude (25) no efeito [cor v]
  espere (0.1) seg
fim
remova os efeitos gráficos
```

\--- /task \---