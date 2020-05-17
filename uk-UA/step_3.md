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

Код для гри на барабані **дуже** схожий на код, що змінює образи спрайта.

\--- hints \---

\--- hint \---

Тобі треба додати лише два блоки: `програти на барабані (0.25) ударів`{:class="block3extensions"} та `елемент (довжина послідовності) з послідовності`{:class="block3variables"}.

\--- /hint \---

\--- hint \---

Тобі знадобляться ці блоки:

![балерина](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \---

Ось як має виглядати твій завершений код:

![балерина](images/ballerina.png)

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