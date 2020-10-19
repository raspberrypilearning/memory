## Kolejne poziomy

Jak dotąd gracz musi zapamiętać tylko sekwencję pięciu kolorów. Popraw swoją grę dodając wynik i dodając kod, tak aby gracz zdobywał punkty, gra przenosi się na następny poziom, a sekwencja kolorów do zapamiętania staje się dłuższa.

--- task ---

Utwórz nową zmienną o nazwie `wynik`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

--- /task ---

W oparciu o `wynik`{:class="block3variables"}, gra będzie decydować o długości sekwencji kolorów. Zacznij od wyniku (i długości sekwencji) `3`.

--- task ---

Dodaj blok na początku twojej postaci `kiedy kliknięto flagę`{:class="block3events"}, aby ustawić kod `wynik`{:class="block3variables"} na `3`.

--- /task ---

Zamiast zawsze tworzyć sekwencję pięciu kolorów, teraz chcesz żeby `wynik`{:class="block3variables"} określał długość sekwencji.

--- task ---

Zmień pętlę `powtarzaj`{:class="block3control"} dla postaci (dla utworzenia sekwencji kolorów), aby powtórzyć `wynik`{:class="block3variables"} razy:

![duszek](images/ballerina.png)

```blocks3
repeat (wynik :: variables)
end
```

--- /task ---

--- task ---

Jeśli gracz powtarza prawidłową sekwencję, powinieneś dodać `1` do `wyniku`{:class="block3variables"}, aby zwiększyć długość następnej sekwencji. Dodaj następujący blok do kodu postaci **w punkcie, w którym wiesz, że sekwencja jest poprawna**:

![duszek](images/ballerina.png)

```blocks3
change [wynik v] by (1)
```

--- hints ---


--- hint ---

Wiesz, że sekwencja jest poprawna w momencie, w którym gra `nadaje`{:class="block3events"} wiadomość "wygrana".

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

Na koniec dodaj pętlę `zawsze`{:class="block3control"} wokół kodu, który generuje sekwencję, aby gra stworzyła nową sekwencję kolorów dla każdego poziomu. Tak może wyglądać kod twojej postaci:

![balerina](images/ballerina.png)

```blocks3
when flag clicked
set [wynik v] to [3]
forever
    delete (all v) of [sekwencja v]
    repeat (wynik)
        add (pick random (1) to (4)) to [sekwencja v]
        switch costume to (item (length of [sekwencja v]) of [sekwencja v]
        wait (1) seconds
    end
    wait until < (length of [sekwencja v]) = [0]>
    broadcast (wygrana v) and wait
    change [wynik v] by (1)
end
```

--- /task ---

--- task ---

Zaproś znajomych do przetestowania swojej gry. Pamiętaj, aby ukryć listę `sekwencji`{:class="block3variables"}, zanim w nią zagrają!

--- /task ---