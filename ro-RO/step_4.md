## Repetați secvența

Acum veți adăuga patru butoane pe care playerul trebuie să le apese pentru a repeta secvența de culori.

\--- task \--- Adăugați patru sprites noi în proiect pentru a reprezenta cele patru butoane.

+ Editați costumele noi sprites, astfel încât să existe un sprite în fiecare dintre cele patru culori
+ Puneți spritele în aceeași ordine pe scenă ca și costumele: roșu, albastru, verde, galben

![captură de ecran](images/colour-drums.png) \--- /task \---

\--- task \--- Adăugați codul la sprite roșu, astfel încât, atunci când clicul este sprite, acesta `transmite`{: class = "block3events"} un mesaj "roșu" către caracterul sprite:

![roșu-tambur](images/red_drum.png)

```blocks3
    când acest sprite a dat clic pe
    difuzat (roșu v)
```

\--- /task \---

A `difuzat`{: class = "block3events"} este ca un mesaj anunțat pe un difuzor, pe care îl puteți auzi, de exemplu, în școli sau supermarketuri. Toți spritele pot auzi emisiunea `{`= class = "block3events"}, dar numai sprite-ul a cărui sarcină este să răspundă va face ceva.

\--- task \---

Adăugați un cod similar cu spritele albastre, verzi și galbene, pentru a le face `difuzeze mesajele despre culoarea proprie`{: class = "block3events"}.

\--- /task \---

Vă amintiți că difuzarea `{`= class = "block3events"} este ca un mesaj difuzor? Veți adăuga un cod pentru a face ca sarcina sprite să răspundă la mesajele `{`= 'block3events'} de difuzare.

\--- task \---

Când sprite personaj primește mesajul `roșu`{: class = „block3events“}, codul trebuie să verifice dacă numărul `1` este la începutul `secvenței`{: class = „block3variables“} listă (ceea ce înseamnă că `roșu`{: class = "block3events"} este următoarea culoare din secvență).

Dacă numărul `1` se află la începutul listei, codul trebuie să elimine numărul din listă, deoarece playerul și-a amintit culoarea corectă. În caz contrar , este de peste joc, iar codul trebuie să `oprire toate`{: class = „block3control“} pentru a termina jocul.

![balerină](images/ballerina.png)

```blocks3
atunci când primesc [v red]
dacă <(punctul (1 v) din [secvența v]) =[1]> , apoi
șterge (1 v) din [secvența v]
altceva
spun [Joc de peste!] pentru (1) secunde
stop [toate v]

```

\--- /task \---

\--- task \--- Adăugați la codul pe care tocmai l-ați scris astfel încât un batere de tambur să joace, de asemenea, atunci când personajul sprite primește `difuzare corectă`{: class = "block3events"}.

\--- Sugestii \--- \--- Indicație \--- Puteți folosi numerele care corespund fiecărei culori pentru a reda baterea corectă a tobei?

+ 1 = roșu
+ 2 = albastru
+ 3 = verde
+ 4 = galben \--- / indiciu \--- \--- sugestie \--- Mai mult de `ștergeți 1 din blocul secvență`{: class = "block3variables"}, adăugați tamburul `redare`{: class = " block3sound "} bloc pentru a juca primul sunet din `secvența`{: class =" block3variables "} listă.

\--- / hint \--- \--- indiciu \--- Aici este codul de care va trebui să adăugați:

```blocks3
atunci când primesc [v red]
dacă <(punctul (1 v) din [secvență v]) =[1]> , apoi

+ joacă tambur (\ (1 \) Snare Drum v) pentru (0,25) bate
șterge (1 v ) din [secventa v]
altceva
spune [Joc peste!] pentru (1) secunde
stop [toate v]


```

\--- / indiciu \--- \--- / sugestii \--- \--- / sarcina \---

\--- task \--- Duplicați codul pe care l-ați folosit pentru a vă face sprite de caractere să răspundă la mesajul `roșu`{: class = "block3events"}. Modificați codul duplicat astfel încât acesta să trimită mesajul `albastru`{: class = "block3events"}. \--- /task \---

Când sprite răspunde la mesajul `albastru`{: class = "block3events"}, care bit de cod ar trebui să rămână același și care bit ar trebui să se schimbe? Rețineți că fiecare culoare are un număr corespunzător.

\--- task \--- Modificați codul sprite al caracterelor astfel încât caracterul să răspundă corect la mesajul `albastru`{: class = "block3events"}.

\--- Sugestii \--- \--- Indicație \---

Păstrați aceste blocuri, dar trebuie să le schimbați într-un fel:

![balerină](images/ballerina.png)

```blocks3
<(punctul (1 v) din [secvență v]) = [1]>

atunci când primesc [v red]

redare tambur (\ (1 \) Snare Drum v) pentru (0,25) bătăi
```

\--- / hint \--- \--- sugestie \--- Aici este modul în care codul dvs. ar trebui să caute `albastru`{: class = "block3events"} difuzare.

![balerină](images/ballerina.png)

```blocks3
atunci când primesc [v blue]
dacă <(punctul (1 v) din [secvență v]) =[2]> , apoi
    tambur joc (\ (2 \) Bass Drum v) pentru (0,25) bate
    șterge (1 v) din [secventa v]
altceva
    spune [Joc peste!] pentru (1) secunde
    stop [toate v]

```

\--- / indiciu \--- \--- / sugestii \--- \--- / sarcina \---

\--- task \--- Duplicați din nou codul de două ori (pentru butoanele verde și galben) și schimbați părțile necesare astfel încât caracterul să răspundă corect la noile `emisiuni`{: class = "block3events"}. \--- /task \---

Nu uitați să testați codul! Puteți memora o secvență de cinci culori? Este secvența diferită de fiecare dată?

Când player -ul repetă în mod corect secvența de culoare întreg, `secvența`{: class = „block3variables“} lista emtpy și jucătorul câștigă. Dacă doriți, puteți afișa , de asemenea , unele lumini intermitente ca o recompensă dată pe `secvența`{: class = „block3variables“} lista este goală.

\--- task \--- Adăugați acest cod la sfârșitul caracterului dvs. `când faceți clic pe pictograma`{: class = "block3events"} script:

![balerină](images/ballerina.png)

```blocks3
    așteptați până când < (lungimea secvenței v]) = [0]>
    difuzat (câștigat v) și așteptați
```

\--- /task \---

\--- sarcină \--- Comutarea la scenă, și importați `tambur mașină` sunet sau alt sunet vă place.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \--- Adăugați acest cod pentru a reda un sunet și pentru a schimba culoarea fundalului atunci când jucătorul câștigă.

![balerină](images/stage.png)

```blocks3
    când am primit [castigat v]
    sunet de pornire (mașină cu tambur v)
    repeat (50)
        schimbare [culoare v] efect de (25)
        wait (0,1) secunde
    end
    efecte grafice clare
```

\--- /task \---