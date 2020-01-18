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

\--- hints \--- \--- hint \--- Sólo necesitas añadir dos bloques: un bloque `tocar tambor durante (0.25) tiempos `{:class="block3sound"} y un bloque `elemento (longitud de secuencia) de secuencia`{:class="block3variables"}. \--- /hint \--- \--- hint \---

Aquí están los bloques que necesitas:

![ballerina](images/ballerina.png)

```blocks3
tocar tambor (\(1\) Caja v) durante (0.25) tiempos 

(elemento (longitud de [secuencia v]) de [secuencia v])
```

\--- /hint \---

\--- hint \--- Así es como debería verse tu código terminado:

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