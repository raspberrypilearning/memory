## Meerdere levels

Tot nu toe hoeft de speler maar een reeks van vijf kleuren te onthouden. Laten we het spel verbeteren door een score toe te voegen en code toe te voegen zodat de lengte van de reeks die ze moeten onthouden langer wordt naarmate de score van de speler toeneemt.

+ Maak een nieuwe variabele met de naam `score`{:class="blockdata"}.

[[[generic-scratch-add-variable]]]

De `score`{:class="blockdata"} zal worden gebruikt om te bepalen wat de lengte van de reeks moet worden die de speler moet gaan onthouden. We beginnen met een score (en lengte van de reeks) `3`.

+ Voeg een blok toe aan het begin van de code van het personage met `wanneer op de groene vlag is geklikt`{:class="blockevents"} om de `score`{:class="blockdata"} op `3` te zetten.

In plaats van de vaste reeks van 5 kleuren willen we nu dat `score`{:class="blockdata"} bepaalt hoe lang de reeks moet worden.

+ Verander de `herhaal`{:class="blockcontrol"}-lus van het personage (om de reeks te maken) om `score`{:class="blockdata"} keer te herhalen:

```blocks
    herhaal (score) keer
end
```

+ Als de reeks goed is geraden zou `1` bij de score moeten worden opgeteld om de lengte van de volgende reeks te verhogen. Voeg dit blok toe aan de code van het personage **op de plaats waarvan je weet dat de reeks goed geraden is**.

```blocks
    verander [score v] met (1)
```

--- hints --- --- hint --- Je weet dat de reeks goed geraden is op de plaats waar het signaal `gewonnen` wordt gezonden. --- /hint --- --- /hints ---

+ Tenslotte moet er nog een `herhaal`{:class="blockcontrol"} -lus om de code worden gezet die de reeks maakt, zodat er voor elk level een nieuwe reeks wordt gemaakt. Zo zou de code van het personage eruit kunnen zien:
    
    ```blocks
    wanneer groene vlag wordt aangeklikt
maak [score v] [3]
herhaal 
  verwijder item (alle v) van [reeks v]
  herhaal (score) keer 
    voeg (willekeurig getal tussen (1) en (4)) toe aan [reeks v]
    verander uiterlijk naar (item (laatste v) van [reeks v] :: list)
    wacht (1) sec.
  end
  wacht tot <(length of [reeks v] :: list) = [0]>
  zend signaal [gewonnen v] en wacht
  verander [score v] met (1)
end
```

+ Laat je vrienden je spel testen. Vergeet niet om de `reeks`{:class="blockdata"}-lijst te verbergen voordat ze gaan spelen!
