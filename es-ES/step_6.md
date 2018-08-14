## Múltiples niveles

Hasta ahora, el jugador solo tiene que recordar una secuencia de cinco colores. Mejoremos el juego agregando puntuaciones y agregando código para que a medida que aumenta la puntuación del jugador, la duración de la secuencia que tienen que recordar se alargue.

+ Crea una nueva variable llamada ` puntuación ` {: class = "blockdata"}.

[[[generic-scratch-add-variable]]]

La `puntuación` {: class = "blockdata"} se usará para decidir la duración de la secuencia que el jugador debe memorizar. Comencemos con una puntuación (y una longitud de secuencia) de ` 3 `.

+ Agregue un bloque al comienzo de su personaje cuando se hace `clic en la bandera` {: class = "blockevents"} el código para establecer la `Puntuación` {: class = "blockdata"} a ` 3 `.

En lugar de crear siempre una secuencia de cinco colores, vamos a hacer que la`Puntuación ` {: class = "blockdata"} determine la longitud de la secuencia.

+ Change the character's `repeat`{:class="blockcontrol"} loop (for creating the sequence) to repeat `score`{:class="blockdata"} times:

```blocks
    repeat (score)
    end
```

+ If the sequence is guessed correctly, you should add `1` to the score to increase the length of the next sequence. Add this block to the character's code **at the point you know the sequence was guessed correctly**.

```blocks
    change [score v] by (1)
```

\--- hints \--- \--- hint \--- You know the sequence was guessed correctly at the point you broadcast the `win` message. \--- /hint \--- \--- /hints \---

+ Finally, you need to add a `forever`{:class="blockcontrol"} loop around the code which generates the sequence, so that a new sequence is created for each level. This is how your character's code might look:
    
    ```blocks
        when flag clicked
        set [score v] to [3]
        forever
            delete (all v) of [sequence v]
            repeat (score)
                add (pick random (1) to (4)) to [sequence v]
                switch costume to (item (last v) of [sequence v]
                wait (1) secs
            end
            wait until < (length of [sequence v]) = [0]>
            broadcast [won v] and wait
            change [score v] by (1)
        end
    ```

+ Get your friends to test out your game. Remember to hide the `sequence`{:class="blockdata"} list before they play it!