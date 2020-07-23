## Utwórz sekwencję kolorów

Najpierw utwórz postać, która może wyświetlać losową sekwencję kolorów.

\--- task \---

Otwórz nowy projekt Scratch.

**Online**: otwórz nowy projekt Scratch online na stronie [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Offline**: otwórz nowy projekt w edytorze offline.

Jeśli chcesz pobrać i zainstalować edytor Scratch, znajdziesz go na stronie [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}.

\--- /task \---

\--- task \---

Wybierz duszka postaci i tło. Możesz użyć baleriny, ale Twoja postać nie musi być osobą, tylko musi być w stanie pokazać różne kolory.

![zrzut ekranu](images/colour-sprite.png)

\--- /task \---

+ W Twojej grze każdy kolor powinien być reprezentowany przez liczbę:
    
    + 1 = czerwony
    + 2 = niebieski
    + 3 = zielony
    + 4 = żółty

\--- task \---

Daj swojej postaci cztery kostiumy, które mają różne kolory, po jednym kostiumie na każdy z czterech kolorów pokazanych powyżej. Upewnij się, że twoje kolorowe kostiumy są w takiej samej kolejności, jak powyższa lista.

![zrzut ekranu](images/colour-costume.png)

\--- /task \---

Jeśli chcesz, możesz użyć narzędzia do **wypełniania kształtu kolorem**, aby wypełnić części kostiumu innym kolorem.

![wypełnij kształt kolorem](images/color-a-shape.png)

Następnie dodaj listę do przechowywania losowej sekwencji kolorów, które gracz musi zapamiętać.

\--- task \---

Utwórz listę o nazwie `sekwencja`{:class="block3variables"}. Tylko duszek postaci powinien widzieć tę listę, więc możesz wybrać **Tylko dla tego duszka** podczas tworzenia listy.

[[[generic-scratch3-make-list]]]

\--- /task \---

Powinieneś teraz zobaczyć wiele nowych bloków kodu do korzystania z list. Pusta lista powinna być widoczna w lewym górnym rogu planszy.

![zrzut ekranu](images/colour-list-blocks-annotated.png)

Każdy kolor ma przypisaną inną liczbę, więc losowy kolor możesz wybrać poprzez losowe wybranie liczby i dodanie jej do listy.

\--- task \---

Dodaj ten kod do duszka postaci, aby wybrać losową liczbę i dodać ją do `sekwencji`{:class="block3variables"}:

![balerina](images/ballerina.png)

```blocks3
kiedy kliknięto flagę
dodaj (losuj liczbę od (1) do (4)) do [sekwencja v]
```

\--- /task \---

\--- task \---

Przetestuj swój kod. Sprawdź, czy za każdym razem, gdy klikniesz flagę, do listy zostanie dodana losowa liczba od 1 do 4.

\--- /task \---

\--- task \---

Czy do swojego programu możesz dodać kod, który jednocześnie wygeneruje pięć losowych liczb?

\--- hints \---

\--- hint \---

Dodaj blok `usuń wszystkie z sekwencji`{:class="block3variables"}, aby najpierw usunąć wszystkie elementy z listy, a następnie dodaj blok `powtórz`{:class="block3control"}, który dodaje pięć losowych liczb do listy.

\--- /hint \---

\--- hint \---

Tak powinien wyglądać Twój kod:

![balerina](images/ballerina.png)

```blocks3
kiedy kliknięto flagę
usuń (wszystkie v) z [sekwencja v]
powtarzaj (5)
    dodaj (losuj liczbę od (1) do (4)) do [sekwencja v]
koniec
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Za każdym razem, gdy liczba zostanie dodana do listy, postać powinna zmienić swój kostium tak, aby jego kolor pasował do liczby. Umieść te bloki w swoim programie bezpośrednio poniżej kodu, gdzie losowa liczba jest dodawana do `sekwencji`{:class="block3variables"}:

![balerina](images/ballerina.png)

```blocks3
zmień kostium na (element (długość [sekwencja v]) z [sekwencja v]) 
czekaj (1) sekund
```

\--- /task \---