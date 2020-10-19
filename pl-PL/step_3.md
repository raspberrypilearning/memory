## Dodaj dźwięk

--- task ---

Przetestuj swój projekt kilka razy. Czy zauważasz, że czasami ta sama liczba jest wybierana dwukrotnie (lub więcej) razy z rzędu, co utrudnia zapamiętanie sekwencji?

--- /task ---

Czy możesz odtworzyć dźwięk bębna za każdym razem, gdy duszek postaci zmienia kostium? Może nawet inny dźwięk bębna dla każdego koloru?

--- task ---

Dodaj rozszerzenie Muzyka do swojego projektu, aby móc użyć bloku `graj na bębnie`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

Kod odtwarzający bęben to **bardzo** podobny do kodu zmieniającego kostium postaci.

--- hints ---


--- hint ---

Musisz tylko dodać dwa bloki: `graj na bębnie przez (0.25) uderzeń`{:class="block3sound"} i blok `element (długość sekwencji) z sekwencji`{:class="block3variables"}.

--- /hint ---

--- hint ---

Oto bloki, których potrzebujesz:

![balerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sekwencja v]) of [sekwencja v])
```

--- /hint ---

--- hint ---

Oto, jak powinien wyglądać gotowy kod:

![balerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sekwencja v]
repeat (5)
	add (pick random (1) to (4)) to [sekwencja v]
    play drum (item (length of [sekwencja v]) of [sekwencja v]) for (0.25) beats
    switch costume to (item (length of [sekwencja v]) of [sekwencja v])
    wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---