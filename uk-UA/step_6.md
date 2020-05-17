## Рекорд

А тепер збережи рекорд, щоб можна було грати з друзями.

\--- task \---

Додай до свого проєкту дві нові змінні з назвами `рекорд`{:class="block3variables"} та `ім’я`{:class="block3variables"}.

\--- /task \---

Коли гра завершується через те, що гравець відтворив послідовність неправильно, гра повинна перевірити, чи рахунок більший за поточний рекорд. Якщо це так, то гра повинна зберегти рахунок як рекорд, а також зберегти ім’я гравця.

\--- task \---

Додай код до свого спрайта персонажа, щоб зберігати `рекорд`{:class="block3variables"}. Також запитай ім’я гравця і збережи його в змінній `ім’я`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Твій код має відповідати такій схемі:

Після повідомлення `Кінець гри!`{:class="block3looks"} `Якщо`{:class="block3control"} `рахунок`{:class="block3variables"} `більший за`{:class="block3operators"} `рекорд`{:class="block3variables"} `Надати`{:class="block3variables"} змінній `рекорд`{:class="block3variables"} значення `рахунок`{:class="block3variables"} `Запитати`{:class="block3sensing"} ім’я гравця `Надати`{:class="block3variables"} змінній `ім’я`{:class="block3variables"} значення `відповідь`{:class="block3sensing"}

\--- /hint \---

\--- hint \---

Тобі знадобляться наступні блоки:

![ballerina](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```

\--- /hint \---

\--- hint \---

Ось як має виглядати твій код для червоної кнопки:

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (high score) > then
        set [high score v] to (score :: variables)
        ask [High score! What is your name?] and wait
        set [name v] to (answer)
    end
    stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

Тобі треба додати цей новий код до спрайта персонажа також для трьох інших кольорів!

Ти бачиш, що код "Кінець гри" такий самий для всіх чотирьох кольорів?

![ballerina](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

Якщо тобі треба буде щось змінити в коді "Кінець гри", наприклад, додати звук або змінити повідомлення, тобі доведеться робити це чотири рази. Це набридає і забирає багато часу.

Instead, you can define your own code block, and use it anywhere in your project.

\--- task \---

Click on `My blocks`{:class="block3myblocks"}, and then on **Make a Block**. Call this new block `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Add the code from the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast to the `Game over`{:class="block3myblocks"} block so that it looks like this:

![ballerina](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence.

\--- /task \---

Your new `Game over`{:class="block3myblocks"} block is a **function**, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="block3myblocks"} block in.

\--- task \---

Also replace the code in the `else`{:class="block3control"} block connected to the `broadcasts`{:class="block3events"} for the other colours with your new `Game over`{:class="block3myblocks"} block. Here is what the code for the `blue`{:class="block3events"} message should look like

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---