## Topscore

Sla nu de hoogste score op zodat je tegen je vrienden kunt spelen.

--- task --- Voeg twee nieuwe variabelen toe met de naam `topscore`{:class="blockdata"} en `naam`{:class="blockdata"}. --- /task ---

Wanneer het spel eindigt omdat de speler de reeks verkeerd heeft, moet het spel controleren of de score hoger is dan de huidige topscore. Als dat zo is, moet het spel de score opslaan als topscore en ook de naam van de speler opslaan.

--- task --- Voeg code toe aan je personage-sprite om de `topscore`{:class="block3variables"} op te slaan. Vraag ook om de naam van de speler, en sla deze op in de `naam`{:class="block3variables"} variabele.

[[[generic-scratch3-high-score]]]

--- hints ---
 --- hint --- Je nieuwe code moet dit patroon volgen:

Na het `Game over`{:class="block3looks"} bericht `Als`{:class="block3control"} de `score`{:class="block3variables"} is `groter dan`{:class="block3operators"} de `topscore`{:class="block3variables"} `Maak`{:class="block3variables"} de `topscore`{:class="block3variables"} gelijk aan de `score`{:class="block3variables"} `Vraag`{:class="block3sensing"} naar de naam van de speler `Maak`{:class="block3variables"} de `naam`{:class="block3variables"} gelijk aan het `antwoord`{:class="block3sensing"}
--- /hint ---
 --- hint ---

Je hebt de volgende blokken nodig:

![balletdanseres](images/ballerina.png)

```blocks3
if <> then
end

(score)

(score)

<[] > [ ]>

(answer)

(topscore)

ask [Topscore! Wat is je naam?] and wait

set [topscore v] to [ ]

set [naam v] to [ ]
```

--- /hint --- --- hint --- Zo zou de code eruit moeten zien voor als op de rode knop is gedrukt:

![balletdanseres](images/ballerina.png)

```blocks3
when I receive [rood v]
if <(item (1 v) of [reeks v]) = [1]> then 
  play drum (item (1 v) of [reeks v]) for (0.25) beats
  delete (1 v) of [reeks v]
else 
  say [Game over!] for (1) seconds
  if <(score :: variables) > (topscore)> then 
    set [topscore v] to (score :: variables)
    ask [Topscore! Wat is je naam?] and wait
    set [naam v] to (answer)
    stop [alle v]
  end
end
```

--- /hint --- --- /hints --- --- /task ---

Je moet deze nieuwe code ook aan de personage-sprite toevoegen voor de andere drie kleuren!

Zie je dat de 'Game over'-code voor elk van de vier kleuren exact hetzelfde is?

![balletdanseres](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if <(score :: variables) > (topscore)> then 
  set [topscore v] to (score :: variables)
  ask [Topscore! Wat is je naam?] and wait
  set [naam v] to (answer)
end
stop [alle v]
```

Als je een van de 'Game over'-codes moet veranderen, bijvoorbeeld om een geluid toe te voegen of het 'Game over'-bericht te veranderen, moet je het vier keer wijzigen. Dat is vervelend en verspilt veel tijd.

In plaats daarvan kunt je je eigen codeblokken maken en die steeds opnieuw in het project gebruiken.

--- task --- Klik op `Mijn blokken`{:class="block3myblocks"} en vervolgens op **Maak een blok**. Noem dit nieuwe blok `Game over`{:class="block3myblocks"}.

--- /task ---

--- task --- Voeg de code van het `anders`{:class="block3control"} blok verbonden met het `rood`{:class="block3events"} signaal toe aan het `Game over`{:class="block3myblocks"} blok zodat het er zo uitziet:

![balletdanseres](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if <(score :: variables) > (topscore)> then 
  set [topscore v] to (score :: variables)
  ask [Topscore! Wat is je naam?] and wait
  set [naam v] to (answer)
end
stop [alle v]
```

--- /task ---

--- task --- Verwijder nu de code die in het `anders`{:class="block3control"}-blok staat dat is verbonden met het `rood`{:class="block3events"} signaal en voeg het `Game over`{:class="block3myblocks"}-blok in plaats daarvan toe:

![balletdanseres](images/ballerina.png)

```blocks3
when I receive [rood v]
if <(item (1 v) of [reeks v]) = [1]> then 
  play drum (\(1\) Snarentrom v) for (0.25) beats
  delete (1 v) of [reeks v]
else 
  Game over :: custom
end
```

--- /task ---

--- task --- Test je nieuwe blok door het spel te spelen en op de rode knop op het verkeerde moment in de kleurenreeks te klikken. --- /task ---

Je nieuwe `Game over`{:class="block3myblocks"}-blok is een **functie**, een klein script dat je overal kunt gebruiken in je code door het `Game over`{:class="block3myblocks"}-blok toe te voegen.

--- task --- Vervang ook de code in het `anders`{:class "block3control"}-blok dat is verbonden met de `signalen`{:class="block3events"} voor de andere kleuren door je nieuwe `Game over`{:class="block3myblocks"}-blok. Hier is hoe de code voor het `blauw`{:class="block3events"} bericht eruit zou moeten zien

![balletdanseres](images/ballerina.png)

```blocks3
when I receive [blauw v]
if <(item (1 v) of [reeks v]) = [1]> then 
  play drum (\(2\) Basdrum v) for (0.25) beats
  delete (1 v) of [reeks v]
else 
  Game over :: custom
end
```

--- /task ---

--- task --- Voeg nu een geluid toe dat wordt afgespeeld als op de verkeerde knop wordt gedrukt. Je hoeft deze code maar één keer toe te voegen in het `Game over`{:class="block3myblocks"}-blok dat je hebt gemaakt en dus niet vier keer apart!

![balletdanseres](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if <(score :: variables) > (topscore)> then 
  start sound (trumpet1 v)
  set [topscore v] to (score)
  ask [Topscore! Wat is je naam?] and wait
  set [naam v] to (answer)
end
stop [alle v]
```

--- /task ---