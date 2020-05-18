## Рекорд

А тепер збережи рекорд, щоб можна було грати з друзями.

--- task ---

Додай до свого проєкту дві нові змінні з назвами `рекорд`{:class="block3variables"} та `ім’я`{:class="block3variables"}.

--- /task ---

Коли гра завершується через те, що гравець відтворив послідовність неправильно, гра повинна перевірити, чи рахунок більший за поточний рекорд. Якщо це так, то гра повинна зберегти рахунок як рекорд, а також зберегти ім’я гравця.

--- task ---

Додай код до свого спрайта персонажа, щоб зберігати `рекорд`{:class="block3variables"}. Також запитай ім’я гравця і збережи його в змінній `ім’я`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

--- hints ---

--- hint ---

Твій код має відповідати такій схемі:

Після повідомлення `Кінець гри!`{:class="block3looks"} `Якщо`{:class="block3control"} `рахунок`{:class="block3variables"} `більший за`{:class="block3operators"} `рекорд`{:class="block3variables"} `Надати`{:class="block3variables"} змінній `рекорд`{:class="block3variables"} значення `рахунок`{:class="block3variables"} `Запитати`{:class="block3sensing"} ім’я гравця `Надати`{:class="block3variables"} змінній `ім’я`{:class="block3variables"} значення `відповідь`{:class="block3sensing"}

--- /hint ---

--- hint ---

Тобі знадобляться наступні блоки:

![балерина](images/ballerina.png)

```blocks3
if < > then
end

(рахунок)

(рахунок)

[ ] > [ ]

answer

(рекорд)

ask [Як тебе звати?] and wait

set [рекорд v] to [ ] 

set [ім’я v] to [ ] 
```

--- /hint ---

--- hint ---

Ось як має виглядати твій код для червоної кнопки:

![балерина](images/ballerina.png)

```blocks3
when I receive [червоний v]
if <(item (1 v) of [послідовність v])=[1]> then
    play drum (item (1 v) of [послідовність v]) for (0.25) beats
    delete (1 v) of [послідовність v]
else
    say [Кінець гри!] for (1) seconds
    if < (рахунок :: variables) > (рекорд) > then
        set [рекорд v] to (рахунок :: variables)
        ask [Pекорд! Як тебе звати?] and wait
        set [ім’я v] to (answer)
    end
    stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

Тобі треба додати цей новий код до спрайта персонажа також для трьох інших кольорів!

Ти бачиш, що код "Кінець гри" такий самий для всіх чотирьох кольорів?

![балерина](images/ballerina.png)

```blocks3
say [Кінець гри!] for (1) seconds
if < (рахунок :: variables) > (рекорд) > then
    set [рекорд v] to (рахунок :: variables)
    ask [Pекорд! Як тебе звати?] and wait
    set [ім’я v] to (answer)
end
stop [all v]
```

Якщо тобі треба буде щось змінити в коді "Кінець гри", наприклад, додати звук або змінити повідомлення, тобі доведеться робити це чотири рази. Це набридає і забирає багато часу.

Замість цього ти можеш визначити власний блок коду і використовувати його де завгодно в проєкті.

--- task ---

Клацни на `Мої блоки`{:class="block3myblocks"}, а далі — на **Створити блок**. Назви цей новий блок `Кінець гри`{:class="block3myblocks"}.

--- /task ---

--- task ---

Додай код із блоку `інакше`{:class="block3control"}, приєднаного до оповіщення `червоний`{:class="block3events"}, до блоку `Кінець гри`{:class="block3myblocks"}, щоб він виглядав таким чином:

![балерина](images/ballerina.png)

```blocks3
define Кінець гри
say [Кінець гри!] for (1) seconds
if < (рахунок :: variables) > (рекорд) > then
    set [рекорд v] to (рахунок :: variables)
    ask [Pекорд! Як тебе звати?] and wait
    set [ім’я v] to (answer)
end
stop [all v]
```

--- /task ---

--- task ---

Тепер видали цей код із блоку `інакше`{:class="block3control"}, приєднаного до оповіщення `червоний`{:class="block3events"}, і додай замість нього блок `Кінець гри`{:class="block3myblocks"}:

![балерина](images/ballerina.png)

```blocks3
when I receive [червоний v]
if <(item (1 v) of [послідовність v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [послідовність v]
else
    Кінець гри :: custom
end
```

--- /task ---

--- task ---

Протестуй новий блок, граючи у гру і клацнувши червону кнопку в неправильній послідовності кольорів.

--- /task ---

Твій новий блок `Кінець гри`{:class="block3myblocks"} є **функцією** — маленьким скриптом, який ти можеш використовувати будь-де в своєму коді.

--- task ---

Також заміни блоками `Кінець гри`{:class="block3myblocks"} код в блоках `інакше`{:class="block3control"}, які приєднані до `оповіщень`{:class="block3events"} для інших кольорів. Ось як має виглядати код для повідомлення `синій`{:class="block3events"}

![балерина](images/ballerina.png)

```blocks3
when I receive [синій v]
if <(item (1 v) of [послідовність v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [послідовність v]
else
    Кінець гри :: custom
end
```

--- /task ---

--- task ---

Тепер додай звук, який буде відтворюватися при натисканні неправильної кнопки. Тобі треба додати цей код лише один раз в блок `Кінець гри`{:class="block3myblocks"}, який ти зробив (-ла), а не в чотирьох різних місця!

![балерина](images/ballerina.png)

```blocks3
define Кінець гри
start sound [Cough1 v]
say [Кінець гри!] for (1) seconds
if < (рахунок :: variables) > (рекорд) > then
    play sound (trumpet1 v)
    set [рекорд v] to (рахунок)
    ask [Pекорд! Як тебе звати?] and wait
    set [ім’я v] to (answer)
end
stop [all v]
```

--- /task ---