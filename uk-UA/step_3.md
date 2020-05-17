## Додай звук

\--- task \---

Протестуй свій проєкт декілька разів. Ти помітив (-ла), що інколи одне й те саме число вибирається два (або більше) разів підряд, що робить послідовність складнішою для запам’ятовування?

\--- /task \---

Чи можеш ти видавати звук барабана кожного разу, коли спрайт змінює образ? А як щодо різних звуків для кожного з кольорів?

\--- task \---

Додай до свого проєкту розширення Музика, щоб використовувати блок `програти на барабані`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

The code that plays the drum is **very** similar to the code that changes the character's costume.

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /hint \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

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