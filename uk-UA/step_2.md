## Створи послідовність кольорів

Спочатку створи персонажа, який може відображати випадкову послідовність кольорів.

\--- task \---

Відкрий новий проєкт Скретч.

**Онлайн**: відкрий новий онлайн проєкт Скретч на [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Офлайн**: відкрий новий проєкт в офлайн-редакторі.

Якщо тобі треба завантажити та встановити офлайн-редактор Скретч, то ти можеш його знайти на [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}.

\--- /task \---

\--- task \---

Вибери спрайт та тло. Ти можеш використовувати балерину, але твій персонаж не обов’язково повинен бути людиною, все, що вимагається, — мати можливість показувати різні кольори.

![screenshot](images/colour-sprite.png)

\--- /task \---

+ Твоя гра повинна використовувати різні числа для кожного із кольорів:
    
    + 1 = червоний
    + 2 = синій
    + 3 = зелений
    + 4 = жовтий

\--- task \---

Створи своєму персонажу чотири різнокольорові образи, по одному для кожного із чотирьох кольорів, вказаних вище. Переконайся, що кольорові образи йдуть в тому ж порядку, що й кольори у вищенаведеному списку.

![screenshot](images/colour-costume.png)

\--- /task \---

Ти можеш використовувати інструмент **заповнення**, щоб заливати частини образу певним кольором.

![color-a-shape](images/color-a-shape.png)

Далі додай список для зберігання випадкової послідовності кольорів, яку необхідно запам’ятати гравцеві.

\--- task \---

Створи список із назвою `послідовність`{:class="block3variables"}. Твій список має бути видимим лише для спрайта персонажа, тому при створенні списку ти можеш вибрати **Тільки для цього спрайту**.

[[[generic-scratch3-make-list]]]

\--- /task \---

Тепер ти маєш побачити багато нових блоків для списків. А сам порожній список має відображатися в лівому верхньому куті Сцени.

![screenshot](images/colour-list-blocks-annotated.png)

Кожен колір має свій номер, тому ти можеш вибирати випадкові кольори, вибираючи випадково числа і додаючи їх до списку.

\--- task \---

Додай наступний код до спрайта персонажа, щоб вибрати випадкове число і додати його до `послідовності`{:class="block3variables"}:

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