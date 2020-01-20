## Herhaal de reeks

Nu ga je vier knoppen toevoegen die de speler moet indrukken om de volgorde van de kleuren te herhalen.

\--- task \---

Add four new sprites to your project to represent the four buttons.

+ Bewerk de uiterlijken van de nieuwe sprites zodat er één sprite in elk van de vier kleuren is
+ Zet de sprites in dezelfde volgorde op het podium als de uiterlijken: rood, blauw, groen, geel

![screenshot](images/colour-drums.png)

\--- /task \---

\--- task \---

Add code to the red sprite so that, when the sprite is clicked, it `broadcasts`{:class="block3events"} a 'red' message to the character sprite:

![red-drum](images/red_drum.png)

```blocks3
    wanneer op deze sprite wordt geklikt
    zend signaal (rood v)
```

\--- /task \---

A `broadcast`{:class="block3events"} is like a message announced over a loudspeaker, which you can for example hear in schools or supermarkets. All of the sprites can hear the `broadcast`{:class="block3events"}, but only the sprite whose job it is to respond will do something.

\--- task \---

Add similar code to the blue, green, and yellow sprites to make them `broadcast`{:class="block3events"} messages about their own colour.

\--- /task \---

Do you remember that the `broadcast`{:class="block3events"} is like a loudspeaker message? You will add code to make it the character sprite's job to respond to the `broadcast`{:class="block3events"} messages.

\--- task \---

When your character sprite receives the message `red`{:class="block3events"}, the code should check whether the number `1` is at the start of the `sequence`{:class="block3variables"} list (which means that `red`{:class="block3events"} is the next colour in the sequence).

If `1` is at the start of the list, the code should remove the number from the list, because the player remembered the correct colour. Otherwise it's game over, and the code needs to `stop all`{:class="block3control"} to end the game.

![ballerina](images/ballerina.png)

```blocks3
wanneer ik signaal [rood v] ontvang
als <(item(1 v) van [reeks v]) = [1]> dan 
 verwijder (1 v) van [reeks v]
anders
 zeg [Game over!] (1) sec.
 stop [alle v]
einde
```

\--- /task \---

\--- task \---

Add to the code you just wrote so that a drum beat also plays when the character sprite receives the correct `broadcast`{:class="block3events"}.

\--- hints \---

\--- hint \---

Can you use the numbers that correspond to each colour to play the correct drum beat?

+ 1 = rood
+ 2 = blauw
+ 3 = groen
+ 4 = yellow

\--- /hint \---

\--- hint \---

Above the `delete 1 of sequence`{:class="block3variables"} block, add the `play drum`{:class="block3sound"} block to play the first sound in the `sequence`{:class="block3variables"} list.

\--- /hint \---

\--- hint \---

Here is the code you will need to add:

```blocks3
wanneer ik signaal [rood v] ontvang
als <(item (1 v) van [reeks v]) = [1]> dan

speel drum (\(1\) Snarentrom v) gedurende (0.25) maten
  verwijder (1 v) van [reeks v]
anders
  zeg [Game over!] (1) sec.
  stop [alle v]
einde
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code you used to make your character sprite respond to the message `red`{:class="block3events"}. Change the duplicated code so that it sends the message `blue`{:class="block3events"}.

\--- /task \---

When the sprite responds to the message `blue`{:class="block3events"}, which bit of code should stay the same, and which bit should change? Remember that each colour has a corresponding number.

\--- task \---

Change the character sprite's code so that the character responds correctly to the `blue`{:class="block3events"} message.

\--- hints \---

\--- hint \---

Keep these blocks, but you need to change them in some way:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) van [reeks v]) = [1]>

wanneer ik signaal [rood v] ontvang

speel drum (\(1\) Snarentrom v) gedurende (0.25) maten
```

\--- /hint \---

\--- hint \---

Here is how your code should look for the `blue`{:class="block3events"} broadcast.

![ballerina](images/ballerina.png)

```blocks3
wanneer ik signaal [blauw v] ontvang
als <(item (1 v) van [reeks v]) = [2]> dan 
  speel drum (item (1 v) van [reeks v]) gedurende (0.25) maten
  verwijder (1 v) van [reeks v]
anders
  zeg [Game over!] (1) sec.
  stop [alle v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code again twice (for the green and yellow buttons), and change the necessary parts so that the character responds correctly to the new `broadcasts`{:class="block3events"}.

\--- /task \---

Remember to test the code! Can you memorise a sequence of five colours? Is the sequence different each time?

When the player repeats the whole colour sequence correctly, the `sequence`{:class="block3variables"} list emtpy and the player wins. If you want, you can also display some flashing lights as a reward once the `sequence`{:class="block3variables"} list is empty.

\--- task \---

Add this code to the end of your character's `when flag clicked`{:class="block3events"} script:

![ballerina](images/ballerina.png)

```blocks3
    wacht tot < (lengte van [reeks v]) = [0]>
    zend signaal (gewonnen v) en wacht
```

\--- /task \---

\--- task \---

Switch to the Stage, and import the `drum machine` sound or another sound you like.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \---

Add this code to play a sound and make the backdrop change colour when the player wins.

![ballerina](images/stage.png)

```blocks3
    wanneer ik signaal [gewonnen v] ontvang
start geluid [Drum machine v]
herhaal (50) keer 
  verander [kleur v] effect met (25)
  wacht (0.1) sec.
einde
zet alle effecten uit
```

\--- /task \---