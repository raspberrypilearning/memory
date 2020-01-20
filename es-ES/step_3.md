## Añadir sonido

\--- task \---

Prueba tu proyecto unas cuantas veces. ¿Te has dado cuenta que a veces se elige el mismo número dos veces (o más) en una fila, lo que hace que la secuencia sea más difícil de memorizar?

\--- /task \---

¿Puedes hacer que suene un tambor cada vez que el personaje cambie de disfraz? ¿Y qué tal un sonido de tambor diferente para cada color?

\--- task \---

Añade la extensión de Música a tu proyecto para que puedas usar el bloque `tocar tambor`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

El código que toca el tambor es **muy** similar al código que cambia el disfraz del personaje.

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /hint \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
tocar tambor (\(1\) Caja v) durante (0.25) tiempos 

(elemento (longitud de [secuencia v]) de [secuencia v])
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

```blocks3
al hacer clic en bandera
eliminar (todos v) de [secuencia v]
repetir (5)
Añadir (número aleatorio entre (1) y (4)) a [secuencia v]
tocar tambor (elemento (longitud de [secuencia v]) de [secuencia v]) durante (0.25) tiempos
cambiar disfraz a (elemento (longitud de [secuencia v]) de [secuencia v])
esperar (1) segundos
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---