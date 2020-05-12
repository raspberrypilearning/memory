## Добавление звука

--- task ---

Проверь свой проект несколько раз. Ты замечал, что иногда одно и то же число попадается два (или больше) раза подряд, из-за чего последовательность сложнее запомнить?

--- /task ---

Можешь ли ты сделать так, чтобы звук барабана воспроизводился каждый раз, когда персонаж спрайта меняет костюм? А как насчет разных звуков барабана для каждого цвета?

--- task ---

Добавь расширение "Музыка" в свой проект, чтобы ты мог использовать блок `играть барабан`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

Код, который воспроизводит барабан **очень** похож на код, который меняет костюм персонажа.

--- hints ---

--- hint ---

Тебе нужно только добавить два блока: блок `играть барабан (0,25) бита`{:class="block3sound"} и блок `элемент (длина списка последовательность) в последовательность`{:class="block3variables"}.

--- /hint ---

--- hint ---

Вот блоки, которые тебе понадобятся:

![балерина](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

--- /hint ---

--- hint ---

Вот как должен выглядеть твой код:

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

--- /hint ---

--- /hints ---

--- /task ---