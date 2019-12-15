## Najboljši rezultat

Sedaj poskrbi, da se bo najboljši rezultat shranil, da boste lahko prijatelji tekmovali med seboj.

\--- task \--- Projektu dodaj dve novi spremenljivki: `najboljši rezultat`{:class="block3variables"} in `ime`{:class="block3variables"}. \--- /task \---

Ko se igra konča, ker igralec ni ugotovil zaporedja, naj igra preveri, če je rezultat boljši od trenutno najboljšega rezultata. Če je, naj igra shrani točke kot najboljši rezultat, hkrati pa naj shrani tudi ime tekmovalca.

\--- task \--- Figuri lika dodaj kodo, ki shrani `najboljši rezultat`{:class="block3variables"}. Vprašaj igralca tudi za ime in ga shrani v spremenljivko `ime`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- Tvoja nova koda mora slediti temu vzorcu:

Ko je objavljeno sporočilo `konec igre`{:class="block3looks"} `Če`{:class="block3control"} so `točke`{:class="block3variables"} `večje od`{:class="block3operators"} `najboljšega rezultata`{:class="block3variables"} `nastavi`{:class="block3variables"} `najboljši rezultat`{:class="block3variables"} na `točke`{:class="block3variables"}. `Vprašaj`{:class="block3sensing"}, kako je igralcu ime in `nastavi`{:class="block3variables"} `ime`{:class="block3variables"} na `odgovor`{:class="block3sensing"} \--- /hint \--- \--- hint \---

Potrebuješ naslednje bloke:

![ballerina](images/ballerina.png)

```blocks3
če < > potem
konec

(točke)

(točke)

[ ] > [ ]

(odgovor)

(najboljši rezultat)

Vprašaj [Kako ti je ime?] in počakaj

nastavi [najboljši rezultat v] na ()

nastavi [ime v] na () 
```

\--- /hint \--- \--- hint \--- Tako bi morala izgledati koda za pritisk na rdeči gumb:

![ballerina](images/ballerina.png)

```blocks3
ko prejmem [rdeča v]
če <(element (1 v) v [zaporedje v])=(1)> potem
  zaigraj na boben (\(1\) Mali boben v) za (0.25) utripov
  zbriši (1 v) v [zaporedje v]
sicer
  reci [Konec igre!] za (1) sekund
  če < (točke :: variables) > (najboljši rezultat) > potem
        nastavi [najboljši rezultat v] na (točke :: variables)
        Vprašaj [Najboljši rezultat! Kako ti je ime?] in počakaj
    nastavi [ime v] na (odgovor)
  konec
  ustavi [vse v]
konec
```

\--- /hint \--- \--- /hints \--- \--- /task \---

To novo kodo moraš dodati figuri lika tudi za preostale tri barve!

Ali opaziš, da je koda 'konec igre' enaka za vse štiri barve?

![ballerina](images/ballerina.png)

```blocks3
reci [Konec igre!] za (1) sekund
  če < (točke :: variables) > (najboljši rezultat) > potem
        nastavi [najboljši rezultat v] na (točke :: variables)
        Vprašaj [Najboljši rezultat! Kako ti je ime?] in počakaj
    nastavi [ime v] na (odgovor)
  konec
  ustavi [vse v]
konec
```

Če želiš spremeniti kakšen del kode 'konec igre', da bi npr. dodal zvok ali spremenil napis, moraš to spremeniti štirikrat. To je zoprno in vzame precej časa.

Namesto tega lahko definiraš svoj lastni blok kode in ga uporabiš kjerkoli v projektu.

\--- task \--- Klikni na `Moji bloki`{:class="block3myblocks"}, nato pa na **Ustvari blok**. Novi blok poimenuj `Konec igre`{:class="block3myblocks"}.

\--- /task \---

\--- task \--- Dodaj kodo iz bloka `sicer`{:class="block3control"}, ki je povezan z objavo `rdeča`{:class="block3events"}, v blok `Konec igre`{:class="block3myblocks"} da bo ta videti tako:

![ballerina](images/ballerina.png)

```blocks3
definiraj Konec igre
reci [Konec igre!] za (1) sekund
  če < (točke :: variables) > (najboljši rezultat) > potem
        nastavi [najboljši rezultat v] na (točke :: variables)
        Vprašaj [Najboljši rezultat! Kako ti je ime?] in počakaj
    nastavi [ime v] na (odgovor)
  konec
  ustavi [vse v]
```

\--- /task \---

\--- task \--- Zdaj odstrani kodo iz bloka `sicer`{:class="block3control"}, ki je povezan z objavo `rdeča`{:class="block3events"}, in maesto nje dodaj blok `Konec igre`{:class="block3myblocks"}:

![ballerina](images/ballerina.png)

```blocks3
ko prejmem [rdeča v]
če <(element (1 v) v [zaporedje v])=(1)> potem
  zaigraj na boben (\(1\) Mali boben v) za (0.25) utripov
  zbriši (1 v) v [zaporedje v]
sicer
   Konec igre :: custom
konec
```

\--- /task \---

\--- task \--- Preizkusi svoj novi blok s klikom na rdeč gumb, ko ta ne ustreza zaporedju barv. \--- /task \---

Tvoj novi blok `Konec igre`{:class="block3myblocks"} je **funkcija**, kratko zaporedje ukazov, ki jo lahko uporabiš kjerkoli želiš, tako da dodaš blok `Konec igre`{:class="block3myblocks"}.

\--- task \--- Zamenjaj tudi kodo v bloku `sicer`{:class="block3control"}, ki je povezan z `objavami`{:class="block3events"} za druge barve, s tvojim `Konec igre`{:class="block3myblocks"} blokom. Tako mora izgledati tvoja koda za sporočilo `moda`{:class="block3events"}

![ballerina](images/ballerina.png)

```blocks3
ko prejmem [modra v]
če <(element (1 v) v [zaporedje v])=(2)> potem
  zaigraj na boben (\(2\) Mali boben v) za (0.25) utripov
  zbriši (1 v) v [zaporedje v]
sicer
   Konec igre :: custom
konec
```

\--- /task \---

\--- task \--- Sedaj dodaj zvok, ki zazveni, kadar je pritisnjen napačen gumb. Ta zvok je potrebno dodati le enkrat v blok `Konec igre`{:class="block3myblocks"}, ki si ga ustvaril-a in ne štirikrat!

![ballerina](images/ballerina.png)

```blocks3
definiraj Konec igre
predvajaj zvok (Cough1 v)
reci [Konec igre!] za (1) sekund
  če < (točke :: variables) > (najboljši rezultat) > potem
        predvajaj zvok (Trumpet1) do konca
        nastavi [najboljši rezultat v] na (točke :: variables)
        Vprašaj [Najboljši rezultat! Kako ti je ime?] in počakaj
    nastavi [ime v] na (odgovor)
  konec
  ustavi [vse v]
```

\--- /task \---