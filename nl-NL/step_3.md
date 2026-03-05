## Geluid toevoegen

--- task ---

Test je project een paar keer. Merk je dat soms hetzelfde nummer twee keer (of meer) achter elkaar wordt gekozen, waardoor de volgorde moeilijker te onthouden is?

--- /task ---

Kun je een drumgeluid laten spelen telkens als de personagesprite van kostuum verandert? En wat dacht je van een ander drumgeluid voor elke kleur?

--- task ---

Voeg de Muziek-extensie toe aan je project zodat je het `drum afspelen`{:class="block3extensions"} blok kunt gebruiken.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

De code die de drum speelt is **erg** vergelijkbaar met de code die het kostuum van het personage verandert.

--- hints ---
 --- hint --- Je hoeft slechts twee blokken toe te voegen: een `speel drum voor (0.25) beats`{:class="block3sound"} blok en een `item (lengte van reeks) van reeks`{:class="block3variabees"} blok.
--- /hint ---
 --- hint ---

Dit zijn de blokken die je nodig hebt:

![balletdanseres](images/ballerina.png)

```blocks3
play drum (\(1\) Snarentrom v) for (0.25) beats

(item (length of [reeks v]) of [reeks v])
```

--- /hint ---

--- hint --- Zo zou het voltooide programma eruit moeten zien:

![balletdanseres](images/ballerina.png)

```blocks3
when flag clicked
delete (alle v) of [reeks v]
repeat (5) 
  add (pick random (1) to (4)) to [reeks v]
  play drum (item (laatste v) of [reeks v]) for (0.25) beats
  switch costume to (item (laatste v) of [reeks v])
  wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---