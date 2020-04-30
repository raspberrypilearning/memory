## Varios niveles

Hasta ahora, el jugador solo tiene que recordar una secuencia de cinco colores. Mejora tu juego añadiendo una puntuación, y agregando código para que a medida que el jugador consiga puntos, el juego avance al siguiente nivel y la secuencia de color para recordar se vuelva más larga.

--- task ---

Crea una nueva variable llamada `puntos`{:class="blockdata"}.

[[[generic-scratch3-add-variable]]]

--- /task ---

En base a los `puntos`{:class="block3variables"}, el juego decidirá la longitud de la secuencia de color. Empieza con una puntuación (y una longitud de secuencia) de `3`.

--- task ---

Añade un bloque al principio del código del personaje (objeto) `al hacer clic en bandera verde`{:class="block3events"} para asignar a la variable `puntos`{:class="block3variables"} el valor `3`.

--- /task ---

En lugar de crear siempre una secuencia de cinco colores, ahora quieres que los `puntos`{:class="block3variables"} determinen la longitud de la secuencia.

--- task ---

Cambia el bucle `repetir`{:class="block3control"} (que crea la secuencia de color) para que se repita las mismas veces que el número de `puntos`{:class="block3variables"}:

![objeto](images/ballerina.png)

```blocks3
repetir (puntos :: variables)
end
```

--- /task ---

--- task ---

Si el jugador repite la secuencia correcta, debes sumar `1` a la variable `puntos`{:class="block3variables"}, y al hacerlo aumentará la longitud de la siguiente secuencia. Agrega el siguiente bloque al código del personaje **en el punto en que sabes que la secuencia es correcta**:

![objeto](images/ballerina.png)

```blocks3
sumar a [puntos v] (1)
```

--- hints ---



--- hint ---

Sabrás que la secuencia es correcta cuando el juego `envíe`{:class="block3events"} el mensaje "¡Tu ganas!".

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

Finalmente, añade un bucle `por siempre`{:class="block3control"} al código que genera la secuencia, de modo que el juego cree una nueva secuencia de colores para cada nivel. Así es como se debería ver el código de tu personaje:

![ballerina](images/ballerina.png)

```blocks3
when green flag clicked
dar a [puntos v] el valor [3]
por siempre
eliminar (todos v) de [secuencia v]
repetir (puntos)
añadir (número aleatorio entre (1) y (4)) a [secuencia v]
cambiar disfraz a (elemento (longitud de [secuencia v]) de [secuencia v]
esperar (1) segundos
end
esperar hasta que < (longitud de [secuencia v]) = [0]>
enviar (¡Tu ganas! v) y esperar
sumar a [ puntos v] (1)
end
```

--- /task ---

--- task ---

Haz que tus amigos prueben tu juego. ¡Recuerda ocultar la lista `secuencia`{:class="block3variables"} antes de que lo jueguen!

--- /task ---