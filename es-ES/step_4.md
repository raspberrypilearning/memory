## Repite la secuencia

Ahora vas a añadir cuatro botones que el jugador tiene que presionar para repetir la secuencia de colores.

\--- task \---

Add four new sprites to your project to represent the four buttons.

+ Edita los disfraces de los nuevos sprites (objetos) para que haya uno en cada uno de los cuatro colores
+ Pon los sprites (objetos) en el escenario en el mismo orden que los trajes: rojo, azul, verde, amarillo

![screenshot](images/colour-drums.png)

\--- /task \---

\--- task \---

Add code to the red sprite so that, when the sprite is clicked, it `broadcasts`{:class="block3events"} a 'red' message to the character sprite:

![red-drum](images/red_drum.png)

```blocks3
    cuando  haces clic en este objeto
enviar (rojo v)
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
al recibir [rojo v]
si <(elemento (1 v) de [secuencia v])=[1]> entonces
eliminar (1 v) de [secuencia v]
si no
decir [¡Has perdido!] durante (1) segundos
detener [todos v]
end
```

\--- /task \---

\--- task \---

Add to the code you just wrote so that a drum beat also plays when the character sprite receives the correct `broadcast`{:class="block3events"}.

\--- hints \---

\--- hint \---

Can you use the numbers that correspond to each colour to play the correct drum beat?

+ 1 = rojo
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
al recibir [rojo v]
si <(elemento (1 v) de [secuencia v])=[1]> entonces
+ tocar tambor (\(1\) Caja v) durante (0.25) tiempos
eliminar (1 v) de [secuencia v]
si no
decir [¡Has perdido!] durante (1) segundos
detener [todos v]
end
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
<(elemento (1 v) de [secuencia v]) = [1]>

al recibir [rojo v]

tocar tambor (\(1\) Caja v) durante (0.25) tiempos
```

\--- /hint \---

\--- hint \---

Here is how your code should look for the `blue`{:class="block3events"} broadcast.

![ballerina](images/ballerina.png)

```blocks3
al recibir [azul v]
si <(elemento (1 v) de [secuencia v])=[2]> entonces 
tocar tambor (\(2\) Bombo v) durante (0.25) tiempos
eliminar (1 v) de [secuencia v]
si no
decir [¡Has perdido!] durante (1) segundos
detener [todos v]
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
    esperar hasta que < (longitud de [secuencia v]) = [0]>
enviar (¡Tu ganas! v) y esperar
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
    al recibir  [¡Tu ganas! v]
iniciar sonido (drum machine v)
repetir (50)
sumar al efecto [color v] (25)
esperar (0.1) segundos
end
quitar efectos gráficos
```

\--- /task \---