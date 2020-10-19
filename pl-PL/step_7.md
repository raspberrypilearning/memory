## Wyzwanie: udoskonal swoją grę

### Zrób więcej bloków

Czy widzisz jakikolwiek inny kod, który jest taki sam dla wszystkich czterech przycisków?

```blocks3
when I receive [czerwony v]
if <(item (1 v) of [sekwencja v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sekwencja v]
else
    Koniec gry :: custom
end

when I receive [niebieski v]
if <(item (1 v) of [sekwencja v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sekwencja v]
else
    Koniec gry :: custom
end
```

Czy potrafisz utworzyć kolejny niestandardowy blok, którego mogą używać wszystkie przyciski?

### Inny strój

Widzisz, że twoja gra zaczyna się od twojej postaci pokazującej jeden z czterech kolorów, i że postać zawsze wyświetla ostatni kolor w sekwencji, podczas gdy gracz powtarza sekwencję kolorów?

Możesz dodać kolejny zwykły biały kostium do swojej postaci, i dodać kod, aby postać wyświetliła ten kostium na początku gry i podczas gdy gracz powtarza sekwencję?

![zrzut ekranu](images/colour-white.png)

### Poziom trudności

Czy możesz pozwolić graczowi na wybór pomiędzy graniem w "tryb łatwy" (używając tylko czerwonych i niebieskich kolorów) a "trybem normalnym" (który używa wszystkich czterech kolorów)?

Jeśli chcesz, możesz nawet dodać tryb „trudny”, który używa piątego bębna!