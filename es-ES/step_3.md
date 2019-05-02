## Reto: Añadir sonido

\--- task \---

Prueba tu proyecto unas cuantas veces. ¿Observa que a veces se elige el mismo número dos veces (o más) en una fila, lo que hace que la secuencia sea más difícil de memorizar?

\--- /task \---

¿Puedes hacer que suene un tambor cada vez que el personaje sprite cambia de traje? ¿Y qué tal un sonido de batería diferente para cada color?

\--- task \---

Añade la extensión de Música a tu proyecto para que puedas usar el bloque `toca la bateria`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

El código que toca el tambor es ** muy ** similar al código que cambia el traje del personaje.

\--- pistas \--- \--- pista \--- Sólo necesitas añadir dos bloques: un `play drum para (0.25) golpea`{:class="block3sound"} bloque y un elemento `item (longitud de secuencia) de la secuencia`{:class="block3variables"} bloque. \--- /pista \--- \--- pista \---

Aquí están los bloques que necesitas:

![bailarina](images/ballerina.png)

```blocks3
tocar el tambor (\ (1 \) redoble de tambor v) durante (0.25) 

(elemento (longitud de [secuencia v]) de [secuencia v])
```

\--- /hint \---

\--- hint \--- Así es como debería verse el código al final:

![bailarina](images/ballerina.png)

```blocks3
cuando se hace clic en la bandera
eliminar (todo v) de [secuencia v]
repetición (5)
    agregar (seleccionar aleatoriamente (1) a (4)) a [secuencia v]
    tocar el tambor (elemento (longitud de [secuencia v]) de [secuencia v]) para (0.25) beats
    cambia el traje a (elemento (longitud de [secuencia v]) de [secuencia v])
    espera (1) segundos
fin
```

\--- /hint \---

\--- /hints \---

\--- /task \---