## Najlepszy wynik

Teraz zapisz najlepszy wynik, abyś mogła grać przeciwko swoim znajomym.

\--- task \---

Dodaj dwie nowe zmienne o nazwie `najlepszy wynik`{:class="block3variables"} i `imię`{:class="block3variables"} do swojego projektu.

\--- /task \---

Kiedy gra kończy się, ponieważ gracz pomyli sekwencję, gra powinna sprawdzić, czy wynik jest wyższy niż bieżący najlepszy wynik. Jeśli jest, gra powinna zapisać wynik jako najlepszy wynik, a także przechowywać nazwę gracza.

\--- task \---

Dodaj kod do duszka postaci, aby przechowywać `najlepszy wynik`{:class="block3variables"}. Zapytaj również o imię gracza i zapisz ją w zmiennej `imię`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Twój nowy kod musi być zgodny z tym wzorem:

Po wiadomości `Gra skończona`{:class="block3looks"} `Jeżeli`{:class="block3control"} `wynik`{:class="block3variables"} jest `większy niż`{:class="block3operators"} `najlepszy wynik`{:class="block3variables"} `Ustaw`{:class="block3variables"} `najlepszy wynik`{:class="block3variables"} na `wynik<code>{:class="block3variables"}
<code>Zapytaj`{:class="block3sensing"} o imię gracza `Ustaw`{:class="block3variables"} `imię`{:class="block3variables"} na <0>odpowiedź</code>{:class="block3sensing"}

\--- /hint \---

\--- hint \---

Potrzebujesz następujących bloków:

![balerina](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```

\--- /hint \---

\--- hint \---

Oto jak twój kod po naciśnięciu czerwonego przycisku powinien wyglądać:

![balerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (high score) > then
        set [high score v] to (score :: variables)
        ask [High score! Jak masz na imię?] I czekać
        ustawić [imię v] na (odpowiedź)
    koniec
    zatrzymać [wszystkie v]
koniec
```

\--- /hint \---

\--- /hints \---

\--- /task \---

Musisz dodać ten nowy kod do duszka postaci również dla pozostałych trzech kolorów!

Czy widzisz, że kod "Koniec gry" dla każdego z czterech kolorów jest dokładnie taki sam?

![balerina](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

Jeśli chcesz zmienić dowolny kod 'Koniec gry', na przykład aby dodać dźwięk lub zmienić wiadomość "Koniec gry", musisz ją zmienić cztery razy. To denerwujące i marnuje dużo czasu.

Zamiast tego możesz zdefiniować własny blok kodu i używać go w dowolnym miejscu projektu.

\--- task \---

Kliknij `Moje bloki`{:class="block3myblocks"}, a następnie **Utwórz blok**. Nazwij ten nowy blok `Koniec gry`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Dodaj kod z bloku `w przeciwnym razie`{:class="block3control"} połączonego z blokiem nadawania komunikatu `czerwony`{:class="block3events"} do bloku `Koniec gry`{:class="block3myblocks"}, tak aby wyglądało to tak:

![balerina](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---

\--- task \---

Teraz usuń kod, który znajduje się w bloku `w przeciwnym razie`{:class="block3control"} podłączonym do bloku nadawania komunikatu `czerwony`{:class="block3events"} i dodaj w to miejsce blok `Koniec gry`{:class="block3myblocks"}:

![balerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

Przetestuj swój nowy blok, grając w grę i klikając czerwony przycisk w niewłaściwym punkcie sekwencji kolorów.

\--- /task \---

Twój nowy blok `Koniec gry`{:class="block3myblocks"} to mały skrypt **funkcja**, którą możesz użyć gdziekolwiek chcesz w swoim kodzie dodając blok `Koniec gry`{:class="block3myblocks"}.

\--- task \---

Zamień również kod w bloku `w przeciwnym razie`{:class="block3control"} połączonym z blokiem `nadawania komunikatu`{:class="block3events"} dla innych kolorów z twoim nowym blokiem `Koniec gry`{:class="block3myblocks"}. Oto jak powinien wyglądać kod `niebieski`{:class="block3events"}

![balerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

Teraz dodaj dźwięk, który odtwarza po naciśnięciu nieprawidłowego przycisku. Musisz dodać ten kod tylko raz w bloku `Koniec gry`{:class="block3myblocks"}, który stworzyłeś, a nie cztery oddzielne razy!

![balerina](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---