## Wyzwanie: udoskonal swoją grę

### Make more blocks

Czy widzisz jakikolwiek inny kod, który jest taki sam dla wszystkich czterech przycisków?

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game Over :: custom
end

when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

Can you make another custom block that all buttons can use?

### Inny strój

Can you see that your game starts with your character showing one of the four colours, and that the character always displays the last colour in the sequence while the player is repeating the colour sequence?

Can you add another plain white costume to your character, and add code so that the character displays this costume at the start of the game and while the player is repeating the sequence?

![zrzut ekranu](images/colour-white.png)

### Poziom trudności

Can you allow your player to choose between playing the game in 'easy mode' (using just the red and blue colours) and 'normal mode' (which uses all four colours)?

Jeśli chcesz, możesz nawet dodać tryb „twardy”, który używa piątego bębna!