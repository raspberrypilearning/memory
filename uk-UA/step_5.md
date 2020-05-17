## Багаторівнева гра

Дотепер гравець мав запам’ятовувати послідовність лише з п'яти кольорів. Вдоскональ свою гру, ввівши рахунок і додавши код, щоб при набиранні гравцем очків, гра переходила на наступний рівень, і послідовність кольорів для запам’ятовування ставала довшою.

\--- task \---

Створи нову змінну з назвою `рахунок`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

На основі `рахунку`{:class="block3variables"} гра визначатиме довжину послідовності кольорів. Розпочнімо із рахунку (і довжини послідовності) `3`.

\--- task \---

Додай блок на початку коду персонажа `коли прапор натиснуто`{:class="block3events"}, щоб встановити значення `рахунку`{:class="block3variables"} рівним `3`.

\--- /task \---

Замість того, щоб кожного разу створювати послідовність п’яти кольорів, тепер ти можеш використовувати `рахунок`{:class="block3variables"}, щоб визначати довжину послідовності.

\--- task \---

Зміни цикл персонажа `повторити`{:class="block3control"} (для створення послідовності кольорів), щоб він повторювався стільки разів, скільки дорівнює `рахунок`{:class="block3variables"}:

![sprite](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
change [score v] by (1)
```

\--- hints \---

\--- hint \---

You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
set [score v] to [3]
forever
    delete (all v) of [sequence v]
    repeat (score)
        add (pick random (1) to (4)) to [sequence v]
        switch costume to (item (length of [sequence v]) of [sequence v]
        wait (1) seconds
    end
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
    change [score v] by (1)
end
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---