## Powtórz sekwencję

Teraz dodasz cztery przyciski, które gracz musi nacisnąć, aby powtórzyć sekwencję kolorów.

--- task ---

Dodaj cztery nowe duszki do swojego projektu, aby reprezentowały cztery przyciski.

+ Edytuj kostiumy nowych duszków tak, aby był duszek był w każdym z czterech kolorów
+ Na scenie umieść duszki na w tej samej kolejności, co kostiumy: czerwony, niebieski, zielony, żółty

![zrzut ekranu](images/colour-drums.png)

--- /task ---

--- task ---

Dodaj kod do czerwonego duszka, tak aby po kliknięciu duszka `nadawał`{:class="block3events"} komunikat „czerwony” do duszka postaci:

![czerwony bęben](images/red_drum.png)

```blocks3
    when this sprite clicked
	broadcast (czerwony v)
```

--- /task ---

`Nadaj komunikat`{:class="block3events"} przypomina wiadomość ogłaszaną przez głośnik, którą można usłyszeć na przykład w szkołach lub supermarketach. Wszystkie duszki słyszą `nadawany komunikat`{:class="block3events"}, ale tylko duszek, którego zadaniem jest odpowiadać, zrobi coś.

--- task ---

Dodaj podobny kod do niebieskiego, zielonego i żółtego duszka, aby wszystkie `nadawały`{:class="block3events"} wiadomości o własnym kolorze.

--- /task ---

Pamiętasz, że `nadawanie komunikatu`{:class="block3events"} jest jak wiadomość z głośnika? Dodasz kod, aby zadaniem duszka było odpowiadanie na wiadomości z `nadawanych komunikatów`{:class="block3events"}.

--- task ---

Gdy duszek twojej postaci otrzyma komunikat `czerwony`{:class="block3events"}, kod powinien sprawdzić, czy liczba `1` znajduje się na początku listy `sekwencji`{:class="block3variables"} (co oznacza, że `czerwony`{:class="block3events"} to kolejny kolor w sekwencji).

Jeśli `1` znajduje się na początku listy, kod powinien usunąć numer z listy, ponieważ gracz zapamiętał poprawny kolor. W przeciwnym razie gra skończona, a kod musi `zatrzymać wszystko`{:class="block3control"}, aby zakończyć grę.

![balerina](images/ballerina.png)

```blocks3
when I receive [czerwony v]
if <(item (1 v) of [sekwencja v])=[1]> then
delete (1 v) of [sekwencja v]
else
say [Koniec gry!] for (1) seconds
stop [all v]
end
```

--- /task ---

--- task ---

Dodaj do kodu, który właśnie napisałeś, aby bęben grał również wtedy, gdy duszek postaci otrzyma poprawny `komunikat`{:class="block3events"}.

--- hints ---


--- hint ---

Czy możesz użyć liczb, które odpowiadają każdemu kolorowi, aby zagrać na właściwym bębnie?

+ 1 = czerwony
+ 2 = niebieski
+ 3 = zielony
+ 4 = żółty

--- /hint ---

--- hint ---

Powyżej bloku `usuń 1 z sekwencji`{:class="block3variables"}, dodaj blok `zagraj na bębnie`{:class="block3sound"}, aby odtworzyć pierwszy dźwięk na liście `sekwencja`{:class="block3variables"}.

--- /hint ---

--- hint ---

Oto kod, który musisz dodać:

```blocks3
when I receive [czerwony v]
if <(item (1 v) of [sekwencja v])=[1]> then
+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sekwencja v]
else
say [Koniec gry!] for (1) seconds
stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

Zduplikuj kod, który użyłeś, aby twój duszek postaci odpowiadał na wiadomość `czerwony`{:class="block3events"}. Zmień zduplikowany kod, aby wysyłał wiadomość `niebieski`{:class="block3events"}.

--- /task ---

Kiedy duszek odpowiada na wiadomość `niebieski`{:class="block3events"}, który bit kodu powinien pozostać taki sam, a który bit powinien się zmienić? Pamiętaj, że każdy kolor ma odpowiedni numer.

--- task ---

Zmień kod duszka postaci tak, aby znak odpowiadał poprawnie na komunikat `niebieski`{:class="block3events"}.

--- hints ---


--- hint ---

Zachowaj te bloki, ale musisz je zmienić w jakiś sposób:

![balerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sekwencja v]) = [1]>

when I receive [czerwony v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

--- /hint ---

--- hint ---

Oto jak twój kod powinien szukać nadawania komunikatu `niebieski`{:class="block3events"}.

![balerina](images/ballerina.png)

```blocks3
when I receive [niebieski v]
if <(item (1 v) of [sekwencja v])=[2]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [sekwencja v]
else
	say [Koniec gry!] for (1) seconds
	stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

Ponownie skopiuj dwukrotnie kod (dla zielonych i żółtych przycisków), i zmień niezbędne części tak, aby znak odpowiadał poprawnie nowemu `nadawaniu`{:class="block3events"}.

--- /task ---

Pamiętaj, aby przetestować kod! Czy możesz zapamiętać sekwencję pięciu kolorów? Czy kolejność jest inna za każdym razem?

Gdy gracz powtarza poprawnie sekwencję całego koloru, lista `sekwencji`{:class="block3variables"} jest pusta i gracz wygrywa. Jeśli chcesz, możesz również wyświetlić niektóre migające światła jako nagrodę, gdy lista `sekwencji`{:class="block3variables"} jest pusta.

--- task ---

Dodaj ten kod na koniec skryptu twojej postaci `kiedy kliknięto flagę`{:class="block3events"}:

![balerina](images/ballerina.png)

```blocks3
    wait until < (length of [sekwencja v]) = [0]>
	broadcast (wygrana v) and wait
```

--- /task ---

--- task ---

Przełącz na scenę i zaimportuj dźwięk `perkusji` lub inny dźwięk, jaki chcesz.

[[[generic-scratch3-sound-from-library]]]

--- /task ---

--- task ---

Dodaj ten kod, aby odtworzyć dźwięk i zmienić kolor tła, gdy gracz wygra.

![balerina](images/stage.png)

```blocks3
    when I receive [wygrana v]
	start sound (drum machine v)
	repeat (50)
		change [color v] effect by (25)
		wait (0.1) seconds
	end
	clear graphic effects
```

--- /task ---