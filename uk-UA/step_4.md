## Відтвори послідовність

Тепер ти додаси чотири кнопки, які гравець зможе натискати для відтворення послідовності кольорів.

\--- task \---

Додай чотири нових спрайти до свого проєкту, які й будуть чотирма кнопками.

+ Відредагуй образи нових спрайтів так, щоб кожен спрайт був одного із чотирьох кольорів
+ Розмісти спрайти в тому ж порядку на сцені, як і кольорові образи персонажа: червоний, синій, зелений, жовтий

![screenshot](images/colour-drums.png)

\--- /task \---

\--- task \---

Додай код до червоного спрайта, щоб коли на нього клацають, він `оповіщував`{:class="block3events"} спрайт персонажа повідомленням "червоний":

![red-drum](images/red_drum.png)

```blocks3
    when this sprite clicked
    broadcast (red v)
```

\--- /task \---

`Оповіщення`{:class="block3events"} — це ніби трансляція повідомлення через гучномовець, які бувають в школах або супермаркетах. Усі спрайти можуть чути `оповіщення`{:class="block3events"}, але лише ті, які повинні відповідати, будуть щось виконувати.

\--- task \---

Додай аналогічний код до синього, зеленого та жовтого спрайтів, щоб вони `оповіщували`{:class="block3events"} повідомленнями з відповідними кольорами.

\--- /task \---

Ти ж пам’ятаєш, що `оповіщення`{:class="block3events"} — це все одно, що повідомлення через гучномовець? Ти додаси код, щоб змусити спрайт персонажа реагувати на повідомлення `оповіщень`{:class="block3events"}.

\--- task \---

Коли твій спрайт персонажу отримує повідомлення `червоний`{:class="block3events"}, код має перевіряти, чи число `1` знаходиться на початку списку `послідовність`{:class="block3variables"} (що означає, що `червоний`{:class="block3events"} є наступним кольором послідовності).

Якщо `1` йде на початку списку, код має видалити звідти це число, бо гравець назвав правильний колір. Інакше гра завершується, і код має `зупинити все`{:class="block3control"} для закінчення гри.

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /task \---

\--- task \---

Додай до коду, який ти щойно написав, удар у барабан, коли спрайт персонажу отримує правильне `оповіщення`{:class="block3events"}.

\--- hints \---

\--- hint \---

Чи можеш ти використати числа, що відповідають кожному з кольорів, щоб зіграти правильний звук барабана?

+ 1 = червоний
+ 2 = синій
+ 3 = зелений
+ 4 = жовтий

\--- /hint \---

\--- hint \---

Над блоком `вилучити 1 з послідовності`{:class="block3variables"} додай `прогарти на барабані`{:class="block3extensions"}, щоб зіграти перший звук в списку `послідовність`{:class="block3variables"}.

\--- /hint \---

\--- hint \---

Ось код, який тобі треба буде додати:

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then

+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Продублюй код, який ти використовував для того, щоб спрайт персонажа зреагував на повідомлення `червоний`{:class="block3events"}. Зміни продубльований код так, що він реагував на повідомлення `синій`{:class="block3events"}.

\--- /task \---

Коли спрайт обробляє повідомлення `синій`{:class="block3events"}, які частини коду мають залишитися такими ж, а які повинні змінитися? Пам’ятай, що кожен із кольорів має відповідний номер.

\--- task \---

Change the character sprite's code so that the character responds correctly to the `blue`{:class="block3events"} message.

\--- hints \---

\--- hint \---

Keep these blocks, but you need to change them in some way:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

\--- /hint \---

\--- hint \---

Here is how your code should look for the `blue`{:class="block3events"} broadcast.

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[2]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code again twice (for the green and yellow buttons), and change the necessary parts so that the character responds correctly to the new `broadcasts`{:class="block3events"}.

\--- /task \---

Remember to test the code! Can you memorise a sequence of five colours? Is the sequence different each time?

When the player repeats the whole colour sequence correctly, the `sequence`{:class="block3variables"} list emtpy and the player wins. If you want, you can also display some flashing lights as a reward once the `sequence`{:class="block3variables"} list is empty.

\--- task \---

Add this code to the end of your character's `when flag clicked`{:class="block3events"} script:

![ballerina](images/ballerina.png)

```blocks3
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
```

\--- /task \---

\--- task \---

Switch to the Stage, and import the `drum machine` sound or another sound you like.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \---

Add this code to play a sound and make the backdrop change colour when the player wins.

![ballerina](images/stage.png)

```blocks3
    when I receive [won v]
    start sound (drum machine v)
    repeat (50)
        change [color v] effect by (25)
        wait (0.1) seconds
    end
    clear graphic effects
```

\--- /task \---