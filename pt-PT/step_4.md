## Repetir a sequência

Agora vais acrescentar quatro botões que o jogador deve usar para repetir a sequência de cores.

\--- task \---

Add four new sprites to your project to represent the four buttons.

+ Edita os trajes dos novos actores para que haja um actor trajado em cada uma das quatro cores
+ Coloca os actores no palco na mesma ordem que os figurinos: vermelho, azul, verde, amarelo

![screenshot](images/colour-drums.png)

\--- /task \---

\--- task \---

Add code to the red sprite so that, when the sprite is clicked, it `broadcasts`{:class="block3events"} a 'red' message to the character sprite:

![red-drum](images/red_drum.png)

```blocks3
    quando alguém clicar em ti
difunde a mensagem (vermelho v)
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
quando receberes a mensagem [vermelho v]
se <((1 v) de [sequêcia v]) = [1]>, então 
 remove (1 v) de [sequêcia v]
senão, 
 diz [Game over!] durante (1) s
 pára [tudo v]
end
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
quando receberes a mensagem [red v]
se <(item (1 v) de [sequence v]) = [1]> então 
+ toca a percussão ((1) Snare Drum v) durante (0.25) tempos
remove (1 v) de [sequence v]
senão, 
diz [Game over!] durante (1) s
pára [all v]
end<
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
<((1 v) de [sequence v]) = [1]>

Quando receberes a mensagem [red v]

toca a percussão ((1) Snare Drum v) durante (0.25) tempos
```

\--- /hint \---

\--- hint \---

Here is how your code should look for the `blue`{:class="block3events"} broadcast.

![ballerina](images/ballerina.png)

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
    espera até que <(o comprimento de [sequence v]) = [0]>
difunde a mensagem (ganhou v) e espera
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
    quando receberes a mensagem [ganhou v]
toca o som (drum machine v)
repete (50) vezes 
  adiciona ao teu efeito [color v] o valor (25)
  espera (0.1) s
end
cancela os teus efeitos gráficos
```

\--- /task \---