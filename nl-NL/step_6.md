## Topscore

Sla nu de hoogste score op zodat je tegen je vrienden kunt spelen.

\--- task \---

Voeg twee nieuwe variabelen toe met de naam `topscore`{:class="blockdata"} en `naam`{:class="blockdata"}.

\--- /task \---

Wanneer het spel eindigt omdat de speler de reeks verkeerd heeft, moet het spel controleren of de score hoger is dan de huidige topscore. Als dat zo is, moet het spel de score opslaan als topscore en ook de naam van de speler opslaan.

\--- task \---

Voeg code toe aan je personage-sprite om de `topscore`{:class="block3variables"} op te slaan. Vraag ook om de naam van de speler, en sla deze op in de `naam`{:class="block3variables"} variabele.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Je nieuwe code moet dit patroon volgen:

Na het `Game over`{:class="block3looks"} bericht `Als`{:class="block3control"} de `score`{:class="block3variables"} is `groter dan`{:class="block3operators"} de `topscore`{:class="block3variables"} `Maak`{:class="block3variables"} de `topscore`{:class="block3variables"} gelijk aan de `score`{:class="block3variables"} `Vraag`{:class="block3sensing"} naar de naam van de speler `Maak`{:class="block3variables"} de `naam`{:class="block3variables"} gelijk aan het `antwoord`{:class="block3sensing"}

\--- /hint \---

\--- hint \---

Je hebt de volgende blokken nodig:

![balletdanseres](images/ballerina.png)

```blocks3
als < > dan
einde

(score)

(score)

[] > [ ]

antwoord

(topscore)

vraag [Topscore! Wat is je naam?] en wacht

maak [topscore v] [ ] 

maak [naam v] [ ] 
```

\--- /hint \---

\--- hint \---

Zo zou de code eruit moeten zien voor als op de rode knop is gedrukt:

![balletdanseres](images/ballerina.png)

```blocks3
wanneer ik signaal [rood v] ontvang
als <(item (1 v) of [reeks v]) = [1]> dan 
  speel drum (item (1 v) van [reeks v]) gedurende (0.25) maten
  verwijder (1 v) van [reeks v]
anders
  zeg [Game over!] (1) sec.
  als < (score :: variables) > (topscore) > dan 
    maak [topscore v] (score :: variables)
    vraag [Topscore! Wat is je naam?] en wacht vraag [Topscore! Wat is je naam?] en wacht
        maak [naam v] (antwoord)
    stop [alle v]
einde
```

\--- /hint \---

\--- /hints \---

\--- /task \---

Je moet deze nieuwe code ook aan de personage-sprite toevoegen voor de andere drie kleuren!

Zie je dat de 'Game over'-code voor elk van de vier kleuren exact hetzelfde is?

![balletdanseres](images/ballerina.png)

```blocks3
zeg [Game over!] (1) sec.
als < (score :: variables) > (topscore) > dan
    maak [topscore v] (score :: variables)
    vraag [Topscore! Wat is je naam?] en wacht	 vraag [Topscore! Wat is je naam?] en wacht
    maak [naam v] (antwoord)
    einde
    stop [alle v]
```

Als je een van de 'Game over'-codes moet veranderen, bijvoorbeeld om een geluid toe te voegen of het 'Game over'-bericht te veranderen, moet je het vier keer wijzigen. Dat is vervelend en verspilt veel tijd.

In plaats daarvan kunt je je eigen codeblokken maken en die steeds opnieuw in het project gebruiken.

\--- task \---

Klik op `Mijn blokken`{:class="block3myblocks"} en vervolgens op **Maak een blok**. Noem dit nieuwe blok `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Voeg de code van het `anders`{:class="block3control"} blok verbonden met het `rood`{:class="block3events"} signaal toe aan het `Game over`{:class="block3myblocks"} blok zodat het er zo uitziet:

![balletdanseres](images/ballerina.png)

```blocks3
definieer Game over
zeg [Game over!] (1) sec.
als < (score :: variables) > (topscore) > dan
    maak [topscore v] (score :: variables)
    vraag [Topscore! Wat is je naam?] en wacht vraag [Topscore! Wat is je naam?] en wacht
        maak [Wat is je naam? v] (antwoord)
    einde
    stop [alle v]
einde
```

\--- /task \---

\--- task \---

Verwijder nu de code die in het `anders`{:class="block3control"}-blok staat dat is verbonden met het `rood`{:class="block3events"} signaal en voeg het `Game over`{:class="block3myblocks"}-blok in plaats daarvan toe:

![balletdanseres](images/ballerina.png)

```blocks3
wanneer ik signaal [rood v] ontvang
als <(item (1 v) van [reeks v]) = [1]> dan
  speel drum (\(1\) Snarentrom v) gedurende (0.25) maten
  verwijder (1 v) van [reeks v]
anders
  Game over :: custom
einde
```

\--- /task \---

\--- task \---

Test je nieuwe blok door het spel te spelen en op de rode knop op het verkeerde moment in de kleurenreeks te klikken.

\--- /task \---

Je nieuwe `Game over`{:class="block3myblocks"}-blok is een **functie**, een klein script dat je overal kunt gebruiken in je code door het `Game over`{:class="block3myblocks"}-blok toe te voegen.

\--- task \---

Vervang ook de code in het `anders`{:class "block3control"}-blok dat is verbonden met de `signalen`{:class="block3events"} voor de andere kleuren door je nieuwe `Game over`{:class="block3myblocks"}-blok. Hier is hoe de code voor het `blauw`{:class="block3events"} bericht eruit zou moeten zien

![balletdanseres](images/ballerina.png)

```blocks3
wanneer ik signaal [blauw v] ontvang
als <(item (1 v) van [reeks v]) = [1]> dan
  speel drum (\(2\) Basdrum v) gedurende (0.25) maten
  verwijder (1 v) van [reeks v]
anders
  Game over :: custom
einde
```

\--- /task \---

\--- task \---

Voeg nu een geluid toe dat wordt afgespeeld als op de verkeerde knop wordt gedrukt. Je hoeft deze code maar één keer toe te voegen in het `Game over`{:class="block3myblocks"}-blok dat je hebt gemaakt en dus niet vier keer apart!

![balletdanseres](images/ballerina.png)

```blocks3
definieer Game over
start geluid [Cough1 v]
zeg [Game over!] (1) sec.
als < (score :: variables) > (topscore) > dan
    start geluid (trumpet1 v)
    maak [topscore v] (score)
    vraag [Topscore! Wat is je naam?] en wacht vraag [Topscore! Wat is je naam?] en wacht
    maak [naam v] (antwoord)
    einde
    stop [alle v]
```

\--- /task \---