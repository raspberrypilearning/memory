## Ponovi zaporedje

Sedaj boš dodal štiri gumbe, ki jih mora igralec pritisniti, da ponovi barvno zaporedje.

\--- task \--- Projektu dodaj štiri nove figure, ki bodo predstavljale štiri gumbe.

+ Uredi videze novih figur, da bo vsak ustrezal eni od štirih barv
+ Figure postavi na oder v enakem zaporedju, kot si sledijo videzi: rdeča, modra, zelena, rumena

![posnetek zaslona](images/colour-drums.png) \--- /task \---

\--- task \--- Rdeči figuri dodaj kodo, da bo ob kliku na njo `objavila`{:class="block3events"} sporočilo 'rdeča' za figuro lika:

![rdeči boben](images/red_drum.png)

```blocks3
    ko kliknemo na to figuro
  objavi (rdeča v)
```

\--- /task \---

`Objava`{:class="block3events"} je kot sporočilo, ki je posredovano preko zvočnika, kot ga lahko denimo slišiš v šoli ali v trgovskih centrih. Vse figure lahko slišijo `objavo`{:class="block3events"}, vendar se bo nanjo odzvala le tista figura, ki ji je namenjena.

\--- task \---

Dodaj podobno kodo modri, zeleni in rumeni figuri, da bodo `objavile`{:class="block3events"} sporočila o svoji barvi.

\--- /task \---

Še veš, da je `objava`{:class="block3events"} kot sporočilo posredovano preko zvočnika? Dodaj kodo, ki bo poskrbela, da se bo figura lika odzvala na sporočilo `objave`{:class="block3events"}.

\--- task \---

Ko tvoja figura lika prejme sporočilo `rdeča`{:class="block3events"}, naj koda preveri ali je številka `1` na začetku seznama `zaporedje`{:class="block3variables"} (kar pomeni, da je `rdeča`{:class="block3events"} naslednja barva v zaporedju).

Če je `1` na začetku seznama, naj koda odstrani številko iz seznama, ker si je igralec zapomnil pravo barvo. V nasprotnem primeru pa je igre konec in koda mora `ustvaviti vse`{:class="block3control"}, da se igra konča.

![balerina](images/ballerina.png)

```blocks3
ko prejmem [rdeča v]
če <(element (1 v) v [zaporedje v])=(1)> potem
zbriši (1 v) v [zaporedje v]
sicer
reci [Konec igre!] za (1) sekund
ustavi [vse v]
konec
```

\--- /task \---

\--- task \--- Pravkar spisano kodo dopolni. da bo zazvenel boben tudi tedaj, ko figura lika prejme pravilno `objavo`{:class="block3events"}.

\--- hints \--- \--- hint \--- Ali lahko uporabiš številke, ki ustrezajo vsaki od barv, da zaigraš pravilno zaporedje bobnov?

+ 1 = rdeča
+ 1 = modra
+ 3 = zelena
+ 4 = rumena \--- /hint \--- \--- hint \--- Nad blok `zbriši 1 v zaporedju`{:class="block3variables"} dodaj blok `zaigraj na boben`{:class="block3sound"}, ki zaigra prvi zvok iz seznama `zaporedje`{:class="block3variables"}.

\--- /hint \--- \--- hint \--- To je koda, ki jo moraš dodati:

```blocks3
ko prejmem [rdeča v]
če <(element (1 v) v [zaporedje v])=(1)> potem

+ zaigraj na boben (\(1\) Mali boben v) za (0.25) utripov
zbriši (1 v) v [zaporedje v]
sicer
reci [Konec igre!] za (1) sekund
ustavi [vse v]
konec

```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Podvoji kodo, ki skrbi za odziv tvoje figure lika na sporočilo `rdeča`{:class="block3events"}. Podvojeno kodo spremeni na tak način, da se bo odzvala na sporočilo `modra`{:class="block3events"}. \--- /task \---

Kateri del kode bo spremenjen in kateri del bo ostal enak, ko figura prejme sporočilo `modra`{:class="block3events"}? Zapomni si, da ima vsaka barva svojo številko.

\--- task \--- Spremeni kodo lika figure, da se bo lik pravilno odzval na sporočilo `modra`{:class="block3events"}.

\--- hints \--- \--- hint \---

Obdrži te bloke, vendar jih ustrezno spremeni:

![balerina](images/ballerina.png)

```blocks3
<(element (1 v) v [zaporedje v])=(1)>

ko prejmem [rdeča v]

zaigraj na boben (\(1\) Mali boben v) za (0.25) utripov
```

\--- /hint \--- \--- hint \--- Tako bi morala izgledati tvoja koda za objavo `modra`{:class="block3events"}.

![balerina](images/ballerina.png)

```blocks3
ko prejmem [rdeča v]
če <(element (1 v) v [zaporedje v])=(2)> potem
zaigraj na boben (\(2\) Mali boben v) za (0.25) utripov
zbriši (1 v) v [zaporedje v]
sicer
reci [Konec igre!] za (1) sekund
ustavi [vse v]
konec
```

\--- /hint \--- \--- /hints \--- \--- /task \---

Podvoji kodo še dvakrat (za zeleni in rumeni gumb) in spremeni ustrezne dele, da se bosta lika ustrezno odzvala za novi `objavi`{:class="block3events"} . \--- /task \---

Ne pozabi preizkusiti kode! Ali si lahko zapomniš zaporedje petih barv? Ali je zaporedje vsakič drugačno?

Ko igralec pravilno ponovi zaporedje, je seznam `zaporedje`{:class="block3variables"} prazno in igralec zmaga. Če želiš, lahko za nagrado prikažeš kakšne utripajoče luči, potem ko je seznam `zaporedje`{:class="block3variables"} prazen.

\--- task \--- Na konec zaporedja ukazov pod blokom `ko kliknemo na zastavico`{:class="block3events"} dodaj to kodo:

![balerina](images/ballerina.png)

```blocks3
    počakaj dokler ni < (dolžina [zaporedje v]) = (0)>
    objavi (zmaga v) in čakaj
```

\--- /task \---

\--- task \--- Zamenjaj oder in uvozi zvok `drum machine` (ritem mašina) ali drug zvok, ki ti je všeč.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \--- Dodaj to kodo, ki zaigra zvok in spremeni barvo ozadja, ko igralec zmaga.

![balerina](images/stage.png)

```blocks3
    ko prejmem [zmaga v]
  predvajaj zvok (drum machine v)
  ponovi (50) krat
    spremeni učinek [barva v] za (25)
    počakaj (0.25) sekund
  konec
  odstrani slikovne učinke
```

\--- /task \---