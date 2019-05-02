## Dodaj dźwięk

\--- task \---

Test your project a few times. Do you notice that sometimes the same number is chosen twice (or more) in a row, which makes the sequence harder to memorise?

\--- /task \---

Can you make a drum sound play each time the character sprite changes costume? And how about a different drum sound for each colour?

\--- task \---

Add the Music extension to your project so you can use the `play drum`{:class="block3extensions"} block.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

The code that plays the drum is **very** similar to the code that changes the character's costume.

\--- hints \--- \--- hint \--- You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block. -- /hint \--- \--- hint \---

Oto bloki, których potrzebujesz:

![balerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \--- Here is how your finished code should look:

![balerina](images/ballerina.png)

```blocks3
gdy kliknięto flagę
usuń (wszystkie v) z [sekwencja v]
powtórz (5)
    dodaj (wybierz losowo (1) do (4)) na [sekwencja v]
    zagraj bęben (element (długość [sekwencja v]) of [sekwencja v]) dla (0.25) uderzeń
    przełącz strój na (element (długość [sekwencja v]) z [sekwencja v])
    czekaj (1) sekund/y
koniec
```

\--- /hint \---

\--- /hints \---

\--- /task \---