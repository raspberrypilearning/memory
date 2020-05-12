## Рекорд

Теперь сохраняй рекорд, чтобы ты мог играть против своих друзей.

--- task ---

Добавьте две новые переменные `рекорд`{:class="block3variables"} и `имя`{:class="block3variables"} в свой проект.

--- /task ---

Когда игра заканчивается из-за того, что игрок выбирает неправильную последовательность, игра должна проверить, является ли счёт выше, чем текущий рекорд. Если это так, игра должна сохранить счёт как рекорд, а также сохранить имя игрока.

--- task ---

Добавь код к спрайту персонажа, чтобы сохранить `рекорд`{:class="block3variables"}. Также запроси имя игрока и сохрани его в переменной `имя`{:class="block3variables"}.

[[[generic-scratch3-high-счёт]]]

--- hints ---

--- hint ---

Для своего нового кода следуй этому шаблону:

После сообщения `Конец игры`{:class="block3looks"} `если`{:class="block3control"} `счёт`{:class="block3variables"} `больше чем`{:class="block3operators"} `рекорд`{:class="block3variables"} `задать`{:class="block3variables"} `рекорд`{:class="block3variables"} значение `счёт`{:class="block3variables"} `спросить`{:class="block3sensing"} имя игрока `задать`{:class="block3variables"} `имя`{:class="block3variables"} значение `ответ`{:class="block3sensing"}

--- /hint ---

--- hint ---

Тебе нужны следующие блоки:

![балерина](images/ballerina.png)

```blocks3
if < > then
end

(счёт)

(счёт)

[ ] > [ ]

answer

(рекорд)

ask [Как тебя зовут?] and wait

set [рекорд v] to [ ] 

set [имя v] to [ ] 
```

--- /hint ---

--- hint ---

Твой код для красной кнопки должен выглядеть так:

![балерина](images/ballerina.png)

```blocks3
when I receive [красный v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	say [Конец игры!] for (1) seconds
	if < (счёт :: variables) > (рекорд) > then
		set [рекорд v] to (счёт :: variables)
		ask [Рекорд! Как тебя зовут?] and wait
		set [имя v] to (answer)
	end
	stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

Добавь этот новый код в спрайт персонажа и для остальных трех цветов!

Код «Конец игры» для каждого из четырех цветов одинаков?

![балерина](images/ballerina.png)

```blocks3
say [Конец игры!] for (1) seconds
if < (счёт :: variables) > (рекорд) > then
	set [рекорд v] to (счёт :: variables)
	ask [Рекорд! Как тебя зовут?] and wait
	set [имя v] to (answer)
end
stop [all v]
```

Если нужно изменить код «Конец игры» - например, добавить звук или изменить сообщение «Конец игры» - тебе нужно будет изменить его четыре раза. Это раздражает и тратиться много времени.

Вместо этого ты можешь определить свой собственный блок кода и использовать его в любой части своего проекта.

--- task ---

Нажми на `Мои блоки`{:class="block3myblocks"}, а затем на **Сделать Блок**. Назови этот новый блок `Конец игры`{:class="block3myblocks"}.

--- /task ---

--- task ---

Добавь код из блока `иначе`{:class="block3control"}, который связан с передачей `красного`{:class= "block3events"} сообщения в блок `Конец игры`{:class="block3myblocks"}, это должно выглядеть так:

![балерина](images/ballerina.png)

```blocks3
define Конец игры
say [Конец игры!] for (1) seconds
if < (счёт :: variables) > (рекорд) > then
	set [рекорд v] to (счёт :: variables)
	ask [Рекорд! Как тебя зовут?] and wait
	set [имя v] to (answer)
end
stop [all v]
```

--- /task ---

--- task ---

Теперь удали код, который находится в блоке `иначе`{:class="block3control"}, связанным с передачей `красного`{:class="block3events"} сообщения, и добавь вместо этого в блок `Конец игры`{:class="block3myblocks"}:

![балерина](images/ballerina.png)

```blocks3
when I receive [красный v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(1\) Snare Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Конец игры :: custom
end
```

--- /task ---

--- task ---

Проверь свой новый блок, сыграв в игру и нажав на красную кнопку в неправильном месте цветовой последовательности.

--- /task ---

Твой новый блок `Конец игры`{:class="block3myblocks"} является **функцией** - маленький скрипт, который ты можешь использовать в своем коде где угодно, добавив блок `Конец игры`{:class="block3myblocks"}.

--- task ---

Также замени код блока `иначе`{:class="block3control"}, связанный с `передачей`{:class="block3events"} сообщений другим цветам, блоком `Конец игры`{:class="block3myblocks"}. Вот как должен выглядеть код для `синего`{:class="block3events"} сообщения

![балерина](images/ballerina.png)

```blocks3
when I receive [синий v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Конец игры :: custom
end
```

--- /task ---

--- task ---

Теперь добавь звук, который воспроизводится при нажатии неправильной кнопки. Тебе нужно добавить этот код только один раз в блок `Конец игры`{:class="block3myblocks"}, а не четыре раза!

![балерина](images/ballerina.png)

```blocks3
define Конец игры
start sound [Cough1 v]
say [Конец игры!] for (1) seconds
if < (счёт :: variables) > (рекорд) > then
	play sound (trumpet1 v)
	set [рекорд v] to (счёт)
	ask [Рекорд! Как тебя зовут?] and wait
	set [имя v] to (answer)
end
stop [all v]
```

--- /task ---