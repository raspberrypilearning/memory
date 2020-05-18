## Varios niveles

Hasta ahora, el jugador solo tiene que recordar una secuencia de cinco colores. Mejora tu juego añadiendo una puntuación, y agregando código para que a medida que el jugador consiga puntos, el juego avance al siguiente nivel y la secuencia de color para recordar se vuelva más larga.

--- task ---

Crea una nueva variable llamada `puntaje`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

--- /task ---

Basado en el `puntaje`{:class="block3variables"}, el juego decidirá la longitud de la secuencia de colores. Empieza con una puntuación (y una longitud de secuencia) de `3`.

--- task ---

Añade un bloque al principio del código del personaje (objeto) `al hacer clic en bandera verde`{:class="block3events"} para asignar a la variable `puntaje`{:class="block3variables"} el valor `3`.

--- /task ---

En lugar de crear siempre una secuencia de cinco colores, ahora quieres que los `puntaje`{:class="block3variables"} determinen la longitud de la secuencia.

--- task ---

Cambia el bucle `repetir`{:class="block3control"} (que crea la secuencia de color) para que se repita las mismas veces que el número de `puntaje`{:class="block3variables"}:

![objeto](images/ballerina.png)

```blocks3
repeat (puntaje :: variables)
end
```

--- /task ---

--- task ---

Si el jugador repite la secuencia correcta, debes sumar `1` a la variable `puntaje`{:class="block3variables"}, y al hacerlo aumentará la longitud de la siguiente secuencia. Agrega el siguiente bloque al código del personaje **en el punto en que sabes que la secuencia es correcta**:

![objeto](images/ballerina.png)

```blocks3
change [puntaje v] by (1)
```

--- hints ---

--- hint ---

Sabrás que la secuencia es correcta cuando el juego `envíe`{:class="block3events"} el mensaje "¡Tu ganas!".

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

Finalmente, añade un bucle `por siempre`{:class="block3control"} al código que genera la secuencia, de modo que el juego cree una nueva secuencia de colores para cada nivel. Así es como se debería ver el código de tu personaje:

![bailarina](images/ballerina.png)

```blocks3
when flag clicked
set [puntaje v] to [3]
forever
    delete (all v) of [secuencia v]
    repeat (puntaje)
        add (pick random (1) to (4)) to [secuencia v]
        switch costume to (item (length of [secuencia v]) of [secuencia v]
        wait (1) seconds
    end
    wait until < (length of [secuencia v]) = [0]>
    broadcast (¡Tu ganas! v) and wait
    change [puntaje v] by (1)
end
```

--- /task ---

--- task ---

Haz que tus amigos prueben tu juego. ¡Recuerda ocultar la lista `secuencia`{:class="block3variables"} antes de que lo jueguen!

--- /task ---