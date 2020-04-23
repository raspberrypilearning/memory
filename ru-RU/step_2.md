## Создай последовательность цветов

Сначала создай персонажа, который сможет отображать случайную последовательность цветов.

\--- task \---

Открой новый проект Scratch.

**Онлайн**: открой новый онлайн проект Scratch [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Оффлайн**: Создай новый проект в оффлайн редакторе.

Если тебе нужно скачать и установить оффлайн редактор Scratch, ты можешь найти его по адресу [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}.

\--- /task \---

\--- task \---

Выбери спрайт и фон персонажа. Ты можешь использовать балерину, но твой персонаж не обязательно должен быть человеком, а только способный показывать разные цвета.

![screenshot](images/colour-sprite.png)

\--- /task \---

+ Используй в игре разные числа для каждого цвета:
    
    + 1 = красный
    + 2 = синий
    + 3 = зеленый
    + 4 = желтый

\--- task \---

Добавь своему персонажу четыре костюма разных цветов, по одному на каждый из четырех цветов, указанных раньше. Убедись, что твои цветные костюмы находятся в том же порядке, что и список.

![screenshot](images/colour-costume.png)

\--- /task \---

Если хочешь, можешь использовать инструмент **заливка** для заливки частей костюма другим цветом.

![color-a-shape](images/color-a-shape.png)

Затем добавь список для хранения случайной последовательности цветов, которую игрок должен запомнить.

\--- task \---

Create a list called `sequence`{:class="block3variables"}. Только спрайту персонажа нужно видеть этот список, поэтому ты можешь выбрать **Только для этого спрайта** при создании списка.

[[[generic-scratch3-make-list]]]

\--- /task \---

Теперь ты видишь много новых блоков кода для списков. Пустой список должен быть виден в верхнем левом углу Cцены.

![screenshot](images/colour-list-blocks-annotated.png)

Каждый цвет имеет свой номер, поэтому ты можешь выбрать случайный цвет, случайным образом выбрав номер и добавив его в список.

\--- task \---

Add this code to the character sprite to choose a random number and add it to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
add (pick random (1) to (4)) to [sequence v]
```

\--- /task \---

\--- task \---

Test your code. Check that, each time you click the flag, a random number between 1 and 4 gets added to the list.

\--- /task \---

\--- task \---

Can you add code to your program to generate five random numbers at once?

\--- hints \---

\--- hint \---

Add a `delete all of sequence`{:class="block3variables"} to first delete all the items on the list, and then add a `repeat`{:class="block3control"} block that adds five random numbers to the list.

\--- /hint \---

\--- hint \---

This is what your code should look like:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Each time a number gets added to the list, the character should change its costume so the costume's colour matches the number. Put these blocks into your code immediately below where a random number is added to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
switch costume to (item (length of [sequence v]) of [sequence v])
wait (1) seconds
```

\--- /task \---