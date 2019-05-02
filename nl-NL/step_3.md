## Geluid toevoegen

\--- task \---

Test je project een paar keer. Merk je dat soms hetzelfde nummer twee keer (of meer) achter elkaar wordt gekozen, waardoor de volgorde moeilijker te onthouden is?

\---/task\---

Kun je een drumgeluid laten spelen telkens als de personagesprite van kostuum verandert? En wat dacht je van een ander drumgeluid voor elke kleur?

\--- task \----

Voeg de Muziek-extensie toe aan je project zodat je het `drum afspelen`{:class="block3extensions"} blok kunt gebruiken.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \----

De code die de drum speelt is **erg** vergelijkbaar met de code die het kostuum van het personage verandert.

\--- hints \--- \--- hint \--- Je hoeft slechts twee blokken toe te voegen: een `speel drum voor (0.25) beats`{:class="block3sound"} blok en een `item (lengte van reeks) van reeks`{:class="block3variabees"} blok. \--- /hint \--- \--- hint \---

Dit zijn de blokken die je nodig hebt:

![balletdanseres](images/ballerina.png)

```blocks3
speel drum (\(1\) Snarentrom v) gedurende (0.25) maten

(item (lengte van [reeks v]) van [reeks v])
```

\--- /hint \---

\--- hint \--- Zo zou het voltooide programma eruit moeten zien:

![balletdanseres](images/ballerina.png)

```blocks3
wanneer groene vlag wordt aangeklikt
verwijder (alle v) van [reeks v]
herhaal  (5) 
  voeg (willekeurig getal tussen (1) en (4)) toe aan [reeks v]
  speel drum (item (laatste v) van [reeks v]) gedurende (0.25) maten
  verander uiterlijk naar (item (laatste v) van [reeks v])
  wacht (1) sec.
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---