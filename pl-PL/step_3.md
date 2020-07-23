## Dodaj dźwięk

\--- task \---

Przetestuj swój projekt kilka razy. Czy zauważasz, że czasami ta sama liczba jest wybierana dwukrotnie (lub więcej) razy z rzędu, co utrudnia zapamiętanie sekwencji?

\--- /task \---

Czy możesz odtworzyć dźwięk bębna za każdym razem, gdy duszek postaci zmienia kostium? Może nawet inny dźwięk bębna dla każdego koloru?

\--- task \---

Dodaj rozszerzenie Muzyka do swojego projektu, aby móc użyć bloku `graj na bębnie`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

Kod odtwarzający bęben to **bardzo** podobny do kodu zmieniającego kostium postaci.

\--- hints \---

\--- hint \---

Musisz tylko dodać dwa bloki: `graj na bębnie przez (0.25) uderzeń`{:class="block3sound"} i blok `element (długość sekwencji) z sekwencji`{:class="block3variables"}.

\--- /hint \---

\--- hint \---

Oto bloki, których potrzebujesz:

![balerina](images/ballerina.png)

```blocks3
graj na (\(1\) Werbel v) przez (0.25) taktów

(element (długość [sekwencji v]) z [sekwencji v])
```

\--- /hint \---

\--- hint \---

Oto, jak powinien wyglądać gotowy kod:

![balerina](images/ballerina.png)

```blocks3
kiedy kliknięto flagę
usuń (wszystko v) z [sekwencja v]
powtarzaj (5)
    dodaj (losuj liczbę od (1) do (4)) do [sekwencja v]
    graj na (element (długość [sekwencja v]) z [sekwencja v]) przez (0.25) taktów
    zmień kostium na (element (długość [sekwencja v]) z [sekwencja v])
    czekaj (1) sekund/y
koniec
```

\--- /hint \---

\--- /hints \---

\--- /task \---