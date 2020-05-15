## Añadir sonido

\--- task \---

Test your project a few times. Do you notice that sometimes the same number is chosen twice (or more) in a row, which makes the sequence harder to memorise?

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

Sólo necesitas añadir dos bloques: un bloque `tocar tambor durante (0.25) tiempos `{:class="block3sound"} y un bloque `elemento (longitud de secuencia) de secuencia`{:class="block3variables"}.

\--- /hint \---

\--- hint \---

Aquí están los bloques que necesitas:

![bailarina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \---

Así es como debería verse tu código terminado:

![bailarina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
    play drum (item (length of [sequence v]) of [sequence v]) for (0.25) beats
    switch costume to (item (length of [sequence v]) of [sequence v])
    wait (1) seconds
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---