## Geluid toevoegen

\--- task \---

Test je project een paar keer. Merk je dat soms hetzelfde nummer twee keer (of meer) achter elkaar wordt gekozen, waardoor de volgorde moeilijker te onthouden is?

\--- /task \---

Kun je een drumgeluid laten spelen telkens als de personagesprite van kostuum verandert? En wat dacht je van een ander drumgeluid voor elke kleur?

\--- task \---

Voeg de Muziek-extensie toe aan je project zodat je het `drum afspelen`{:class="block3extensions"} blok kunt gebruiken.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

De code die de drum speelt is **erg** vergelijkbaar met de code die het kostuum van het personage verandert.

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /hint \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
speel drum (\(1\) Snarentrom v) gedurende (0.25) maten

(item (lengte van [reeks v]) van [reeks v])
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

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