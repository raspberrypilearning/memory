## Utwórz sekwencję kolorów

Najpierw utwórz postać, która może wyświetlać losową sekwencję kolorów.

\--- task \--- Otwórz nowy projekt Scratcha.

**Online**: open a new online Scratch project at [rpf.io/scratch-new](https://rpf.io/scratchon).

**Offline**: otwórz nowy projekt w edytorze offline.

Jeśli musisz pobrać i zainstalować edytor Scratcha, znajdziesz go na stronie [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank.

\--- /task \---

\--- task \--- Choose a character sprite and a backdrop. You could use the ballerina, but your character doesn't have to be a person, they only need to be able to show different colours.

![screenshot](images/colour-sprite.png) \--- /task \---

+ Twoja gra powinna używać innego numeru do reprezentowania każdego koloru:
    
    + 1 = czerwony
    + 2 = niebieski
    + 3 = zielony
    + 4 = żółty

Daj swojej postaci cztery stroje, które mają różne kolory, jeden strój dla każdego z czterech kolorów pokazanych powyżej. Upewnij się, że twoje kolorowe stroje są w tej samej kolejności, jak na powyższej liście.

![zrzut ekranu](images/colour-costume.png) \--- /task \---

If you want, you can use the **color a shape** tool to fill parts of the costume with a different colour.

![color-a-shape](images/color-a-shape.png)

Następnie dodaj listę do przechowywania losowej sekwencji kolorów, które gracz musi zapamiętać.

\--- task \--- Create a list called `sequence`{:class="block3variables"}. Only the character sprite needs to see this list, so you can select **For this sprite only** when you create the list.

[[[generic-scratch3-make-list]]]

\--- /task \---

You should now see lots of new code blocks for using lists. The empty list should be visible in the top left-hand corner of the Stage.

![zrzut ekranu](images/colour-list-blocks-annotated.png)

Each colour has a different number, so you can choose a random colour by randomly choosing a number and adding it to the list.

\--- task \--- Add this code to the character sprite to choose a random number and add it to `sequence`{:class="block3variables"}:

![balerina](images/ballerina.png)

```blocks3
kiedy flaga kliknęła
dodaj (wybierz losowo (1) do (4)) do [sekwencja v]
```

\--- /task \---

\--- task \--- Test your code. Check that, each time you click the flag, a random number between 1 and 4 gets added to the list. \--- /task \---

\--- task \--- Can you add code to your program to generate five random numbers at once?

\--- hints \--- \--- hint \--- Add a `delete all of sequence`{:class="block3variables"} to first delete all the items on the list, and then add a `repeat`{:class="block3control"} block that adds five random numbers to the list. -- /hint \--- \--- hint \---

This is what your code should look like:

![balerina](images/ballerina.png)

```blocks3
kiedy flaga kliknęła
usuń (wszystkie v) z [sekwencja v]
powtórz (5)
    dodaj (wybierz losowo (1) do (4)) do [sekwencja v]
koniec
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Za każdym razem, gdy liczba zostanie dodana do listy, postać powinna zmienić swój strój, aby kolor stroju pasował do liczby. Put these blocks into your code immediately below where a random number is added to `sequence`{:class="block3variables"}:

![balerina](images/ballerina.png)

```blocks3
zmień strój na (element (długość [sekwencja v]) z [sekwencja v]) czekać (1) sekund/y
```

\--- /task \---