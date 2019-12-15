## Múltiples niveles

Hasta ahora, el jugador solo tiene que recordar una secuencia de cinco colores. Mejora tu juego añadiendo una puntuación, y agregando código para que a medida que el jugador consigue puntos, el juego se mueve al siguiente nivel y la secuencia de color para recordar se vuelve más larga.

\--- Crea una nueva variable llamada ` puntaje` {: class = "blockdata"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

Basado en la `puntuaci'on`{:class="block3variables"}, el juego decidirá sobre la longitud de la secuencia de color. Empieza con una puntuación (y una longitud de secuencia) de `3`.

\--- tarea \--- Agrega un bloque al comienzo de tu personaje` cuando se hace clic en la bandera ` {: class = "block3events"} programa para establecer la puntuación ` ` {: class = "block3variables"} a ` 3 `. \--- /task \---

En lugar de crear siempre una secuencia de cinco colores, ahora quiere la puntuación ` ` {: class = "block3variables"} para determinar la longitud de la secuencia.

\--- tarea \--- Cambia el bucle `repetir`{:class="block3control"} para crear la secuencia de color) para repetir `score`{:class="block3variables"} veces:

![sprite](images/ballerina.png)

```blocks3
repetir (puntuación :: variables)
final
```

\--- /task \---

\--- tarea \--- Si el jugador repite la secuencia correcta, debes agregar ` 1 ` a ` puntuación ` {: class = "block3variables"}, y al hacerlo aumenta la duraci'on de la siguiente secuencia. Agregue el siguiente bloque al código del personaje ** en el punto en que sabe que la secuencia es correcta **:

![sprite](images/ballerina.png)

```blocks3
cambiar [puntuación v] por (1)
```

\--- pistas \--- \--- pista \--- Sabes que la secuencia es correcta en el momento en que el juego `emite`{:class="block3events"} el mensaje 'ganador'. \--- /hint \--- \--- /hints \---

\--- /task \---

\--- tarea \--- Finalmente, agrega un ` siempre ` {: class = "block3control"} da vueltas al código que genera la secuencia, de modo que el juego cree una nueva secuencia de colores para cada nivel. Así es como se ve el código de tu personaje:

![bailarina](images/ballerina.png)

```blocks3
cuando se hace clic en la bandera
establece [puntuación v] en [3]
para siempre
    elimina (toda v) de [secuencia v]
    repite (puntúa)
        agrega (elige al azar (1) a (4)) a [secuencia v]
        cambiar traje a (elemento (longitud de [secuencia v]) de [secuencia v]
        espere (1) segundos
    finalice
    espere hasta < (longitud de [secuencia v]) = [0]>
    transmisión (ganada v) y espere
    cambios [ puntuación v] por (1)
final
```

\--- /task \---

\--- tarea \--- Consigue que tus amigos prueben tu juego. Recuerda ocultar la secuencia ` ` {: class = "block3variables"} lista antes de que lo jueguen! \--- / tarea \---