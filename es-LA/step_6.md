## High score

Now save the high score so that you can play against your friends.

\--- task \---

Agrega dos nuevas variables llamadas `puntaje mayor`{:class="block3variables"} y `nombre`{:class="block3variables"} a tu proyecto.

\--- /task \---

Cuando el juego termina porque el jugador se equivoca de secuencia, el juego debe verificar si la puntuación es más alta que el mejor resultado actual. Si es así, el juego debe guardar la puntuación como la puntuación más alta (mejor resultado), y también guardar el nombre del jugador.

\--- task \---

Añade código al objeto del personaje para almacenar el `puntaje mayor`{:class="block3variables"}. Pregunta también por el nombre del jugador y guárdalo en la variable `nombre`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Tu nuevo código debe seguir este patrón:

Después del mensaje `Fin del juego`{:class="block3looks"} `Si`{:class="block3control"} `puntaje`{:class="block3variables"} es `mayor que`{:class="block3operators"} el `puntaje mayor`{:class="block3variables"} `Dar`{:class="block3variables"} a `puntaje mayor`{:class="block3variables"} el valor de `puntaje`{:class="block3variables"} `Preguntar`{:class="block3sensing"} el nombre del jugador `Dar`{:class="block3variables"} a `nombre`{:class="block3variables"} el valor de `respuesta`{:class="block3sensing"}

\--- /hint \---

\--- hint \---

Necesitas los bloques siguientes:

![bailarina](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```

\--- /hint \---

\--- hint \---

Así es como debe verse tu código al presionar el botón rojo:

![bailarina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (high score) > then
        set [high score v] to (score :: variables)
        ask [High score! What is your name?] and wait
        set [name v] to (answer)
    end
    stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

¡También necesitas añadir este nuevo código al objeto del personaje para los otros tres colores!

¿Te has fijado que el código 'Fin del juego' para cada uno de los cuatro colores es exactamente el mismo?

![bailarina](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

Si necesitas cambiar cualquiera de los códigos de 'Fin del juego', por ejemplo para agregar un sonido o cambiar el mensaje '¡Fin del juego!', tienes que cambiarlo cuatro veces. Eso es molesto y lleva mucho tiempo.

En cambio, puedes definir tu propio bloque de código y usarlo en cualquier lugar de tu proyecto.

\--- task \---

Haz clic en `Mis bloques`{:class="block3myblocks"}, y luego en **Crear un bloque**. Llama a este nuevo bloque `Fin del juego`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Añade el código del bloque `si no`{:class="block3control"} conectado al enviar `rojo`{:class="block3events"} al bloque `Fin del juego`{:class="block3myblocks"} para que se vea así:

![bailarina](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---

\--- task \---

Ahora quita el código del bloque `si no`{:class="block3control"} conectado al enviar `rojo`{:class="block3events"} y añádelo al bloque `Fin del juego`{:class="block3myblocks"}:

![bailarina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

Prueba tu nuevo bloque jugando el juego y haciendo clic en el botón rojo en el punto equivocado de la secuencia de colores.

\--- /task \---

Tu nuevo bloque `Fin del juego`{:class="block3myblocks"} es un bloque **función**, un pequeño programa que puedes usar en cualquier lugar de tu código agregando dicho bloque `Fin del juego`{:class="block3myblocks"}.

\--- task \---

Reemplaza también el código del bloque `si no`{:class="block3control"} conectado al bloque `enviar`{:class="block3events"} para los otros colores con el nuevo bloque `Fin del juego`{:class="block3myblocks"}. Así es como el código para el enviar `azul`{:class="block3events"} debería verse

![bailarina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

Ahora añade un sonido que suene cuando se presiona el botón equivocado. ¡Sólo necesitas añadir este código una vez en el bloque `Fin del juego`{:class="block3myblocks"} que has hecho, y no cuatro veces separadas!

![bailarina](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---