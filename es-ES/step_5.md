## Varios niveles

Hasta ahora, el jugador solo tiene que recordar una secuencia de cinco colores. Mejora tu juego añadiendo una puntuación, y agregando código para que a medida que el jugador consiga puntos, el juego avance al siguiente nivel y la secuencia de color para recordar se vuelva más larga.

\--- task \--- Crea una nueva variable llamada `puntos`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

En base a los `puntos`{:class="block3variables"}, el juego decidirá la longitud de la secuencia de color. Empieza con una puntuación (y una longitud de secuencia) de `3`.

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
al hacer clic en la bandera
dar a [puntaje v] el valor [3]
por siempre
    eliminar (todos v) de [secuencia v]
    repetir (puntaje)
        agregar (número aleatorio entre  (1) y (4)) a [secuencia v]
        cambiar disfraz a (elemento (longitud de [secuencia v]) de [secuencia v]
        esperar (1) segundos
    fin
    esperar hasta que < (longitud de [secuencia v]) = [0]>
    enviar (ganar v) y esperar
    sumar a [ puntaje v] (1)
final
```

\--- /task \---

\--- task \--- Consigue que tus amigos prueben tu juego. Recuerda ocultar la lista ` secuencia ` {: class = "block3variables"} antes de que lo jueguen. \--- /task \---