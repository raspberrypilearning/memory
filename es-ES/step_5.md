## Múltiples niveles

Hasta ahora, el jugador solo tiene que recordar una secuencia de cinco colores. Mejora tu juego añadiendo una puntuación, y agregando código para que a medida que el jugador consigue puntos, el juego se mueve al siguiente nivel y la secuencia de color para recordar se vuelve más larga.

\--- Crea una nueva variable llamada ` puntaje` {: class = "blockdata"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

Basado en el `puntaje`{:class="block3variables"}, el juego decidirá sobre la longitud de la secuencia de color. Empieza con un puntaje (y una longitud de secuencia) de `3`.

\--- task \--- En el código de tu personaje, agrega un bloque al principio del código `al hacer clic en la bandera`{:class="block3events"} para dar a `puntaje`{:class="block3variables"} el valor `3`. \--- /task \---

En lugar de crear siempre una secuencia de cinco colores, ahora quieres que el ` puntaje ` {: class = "block3variables"} determine la longitud de la secuencia.

\--- task \--- Cambia el bucle `repetir`{:class="block3control"} (para crear la secuencia de color) para repetir `puntaje`{:class="block3variables"} veces:

![objeto](images/ballerina.png)

```blocks3
repetir (puntuación :: variables)
final
```

\--- /task \---

\--- tarea \--- Si el jugador repite la secuencia correcta, debes agregar ` 1 ` a ` puntaje` {: class = "block3variables"}, y al hacerlo aumenta la longitud de la siguiente secuencia. Agrega el siguiente bloque al código del personaje ** en el punto en que sabes que la secuencia es correcta **:

![objeto](images/ballerina.png)

```blocks3
sumar a [puntuación v] (1)
```

\--- hints \--- \--- hint \--- Sabes que la secuencia es correcta en el punto donde el juego `envía`{:class="block3events"} el mensaje "ganar". \--- /hint \--- \--- /hints \---

\--- /task \---

\--- tarea \--- Finalmente, agrega un bucle ` por siempre ` {: class = "block3control"} al código que genera la secuencia, de modo que el juego cree una nueva secuencia de colores para cada nivel. Así es como se ve el código de tu personaje:

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