## Meerdere levels

Tot nu toe hoeft de speler maar een reeks van vijf kleuren te onthouden. Verbeter je spel door een score toe te voegen en code toe te voegen, zodat wanneer de speler punten scoort, het spel naar het volgende niveau gaat en de te onthouden kleurenreeks langer wordt.

--- task --- Maak een nieuwe variabele met de naam `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]] --- /task ---

Op basis van de `score`{:class="block3variables"}, zal het spel beslissen over de lengte van de kleurenreeks. Begin met een score (en een lengte van de kleurenreeks) van `3`.

--- task --- Voeg een blok toe aan het begin van de code van je personage met `wanneer op de groene vlag wordt geklikt`{:class="blockevents"} om de `score`{:class="blockdata"} op `3`te zetten. --- /task ---

In plaats van altijd een reeks van vijf kleuren te maken, gebruik je nu de `score`{:class="block3variables"} om de lengte van de reeks te bepalen.

--- task --- Verander de `herhaal`{:class="blockcontrol"}-lus van het personage (om de kleuren reeks te maken) om `score`{:class="blockdata"} keer te herhalen:

![sprite](images/ballerina.png)

```blocks3
herhaal (score)
einde
```

--- /task ---

--- task --- Als de speler de juiste volgorde herhaalt, moet je `1` aan `score`{:class="block3variabelen"} toevoegen, en daarmee verhoog je de lengte van de volgende reeks. Voeg het volgende blok toe aan de code van het personage **op het punt waar je weet dat de reeks correct is**:

![sprite](images/ballerina.png)

```blocks3
verander [score v] met (1)
```

--- hints ---
 --- hint --- Je weet dat de volgorde correct is op het moment dat het spel het 'gewonnen'-bericht `uitzendt`{:class="block3events"}. --- /hint --- --- /hints ---

--- /task ---

--- task --- Tenslotte moet er nog een `herhaal`{:class="blockcontrol"}-lus om de code worden gezet die de reeks maakt, zodat er voor elk niveua een nieuwe reeks wordt gemaakt. Zo zou de code van het personage eruit kunnen zien:

![balletdanseres](images/ballerina.png)

```blocks3
wanneer groene vlag wordt aangeklikt
maak [score v] [3]
herhaal 
  verwijder (alle v) van [reeks v]
  herhaal (score)
    voeg (willekeurig getal tussen (1) en (4)) toe aan [reeks v]
    verander uiterlijk naar (item (lengte van [reeks v]) van [reeks v]
    wacht (1) sec.
  einde
  wacht tot <(lengte van [reeks v]) = [0]>
  zend signaal (gewonnen v) en wacht
  verander [score v] met (1)
einde
```

--- /task ---

--- task --- Laat je vrienden je spel testen. Vergeet niet om de `reeks`{:class="block3variables"} lijst te verbergen voordat ze het spelen! --- /task ---