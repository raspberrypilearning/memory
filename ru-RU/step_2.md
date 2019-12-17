## Создай последовательность цветов

Сначала создай персонажа, который смоежт отображать случайную последовательность цветов.

\--- task \--- Создай новый проект Scratch.

**Онлайн**: Создай новый онлан проект на [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Оффлайн**: Создай новый проект в редакторе оффлайн.

Оффлайн редактор Scratch можно найти тут [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}.

\--- /task \---

\--- task \--- Выбери спрайт персонажа и фон. Ты можешь использовать балерину, но твой персонаж не обязан быть человеком, о должен только уметь показывать разные цвета.

![screenshot](images/colour-sprite.png) \--- /task \---

+ Твоя игра должна использовать раличные числа, чтобы представлять каждый цвет:
    
    + 1 = красный
    + 2 = синий
    + 3 = зеленый
    + 4 = желтый

\--- task \--- Создай своему персонажу четыре костюма разных цветов - один костюм для каждого цвета. Убедись, что твои цветные костюмы перечислены в том же порядке, что и список выше.

![screenshot](images/colour-costume.png) \--- /task \---

Если вы хотите, вы можете использовать ** цвет фигуры ** инструмент для заливки частей костюма другим цветом.

![color-a-shape](images/color-a-shape.png)

Затем добавьте список для хранения случайной последовательности цветов, которую игрок должен запомнить.

\--- task \--- Создай список с именем `sequence`{:class="block3variables"}. Только спрайт персонажа должен видеть этот список, поэтому вы можете выбрать **Только для этого спрайта **при создании списка.

[[[generic-scratch3-make-list]]]

\--- /task \---

Теперь ты увидишь много новых блоков кода для использования списков. Пустой список должен быть виден в верхнем левом углу рабочей области.

![screenshot](images/colour-list-blocks-annotated.png)

Каждый цвет имеет свой номер, поэтому ты можешь выбрать случайный цвет, случайным образом выбрав номер и добавив его в список.

\--- task \--- Добавьте этот код в спрайт персонажа, чтобы выбрать случайное число и добавить его в последовательность `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
add (pick random (1) to (4)) to [sequence v]
```

\--- /task \---

\--- task \--- Протестируй свой код. Проверь, что каждый раз, когда ты нажимаешь на флаг, случайное число от 1 до 4 добавляется к списку. \--- /task \---

\--- task \--- Can you add code to your program to generate five random numbers at once?

\--- hints \--- \--- hint \--- Add a `delete all of sequence`{:class="block3variables"} to first delete all the items on the list, and then add a `repeat`{:class="block3control"} block that adds five random numbers to the list. \--- /hint \--- \--- hint \---

This is what your code should look like:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Each time a number gets added to the list, the character should change its costume so the costume's colour matches the number. Put these blocks into your code immediately below where a random number is added to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
switch costume to (item (length of [sequence v]) of [sequence v])
wait (1) seconds
```

\--- /task \---