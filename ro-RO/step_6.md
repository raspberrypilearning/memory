## Cel mai mare scor

Acum salva scorul mare pentru a putea juca impotriva prietenilor tai.

\--- task \---

Add two new variables called `high score`{:class="block3variables"} and `name`{:class="block3variables"} to your project.

\--- /task \---

When the game ends because the player gets the sequence wrong, the game should check whether the score is higher than the current high score. If it is, the game should save the score as the high score, and also store the name of the player.

\--- task \---

Add code to your character sprite to store the `high score`{:class="block3variables"}. Also ask for the player's name, and store it in the `name`{:class="block3variables"} variable.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Your new code needs to follow this pattern:

After the `Game over`{:class="block3looks"} message `If`{:class="block3control"} the `score`{:class="block3variables"} is `greater than`{:class="block3operators"} the `high score`{:class="block3variables"} `Set`{:class="block3variables"} the `high score`{:class="block3variables"} to the `score`{:class="block3variables"} `Ask`{:class="block3sensing"} for the player's name `Set`{:class="block3variables"} the `name`{:class="block3variables"} to the `answer`{:class="block3sensing"}

\--- /hint \---

\--- hint \---

You need the following blocks:

![ballerina](images/ballerina.png)

```blocks3
dacă < > apoi
final

(scor)

(scor)

[] > []

răspuns

(scor mare)

întrebați [Care este numele tau?] și așteptați

set de [scor v de mare] la [] 

set [ numele v] la [] 
```

\--- /hint \---

\--- hint \---

Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

```blocks3
atunci când primesc [v red]
dacă <(punctul (1 v) din [secvență v]) =[1]> , apoi
    tambur de redare (element (1 v) din [secvență v]) pentru (0,25) bate
    șterge (1 v) de la [secventa v]
altceva
    spune [Joc peste!] pentru (1) secunde
    daca < (scor :: variabile) > (scor mare) > apoi
        set [scor mare v] )
        cereți [Scor mare! Care este numele dvs.?] Și așteptați
        setați [nume v] la (răspuns)
    capăt
    oprire [toate v]

```

\--- /hint \---

\--- /hints \---

\--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks3
spun [Joc de peste!] pentru (1) secunde
dacă < (scor :: variabile) > (scor mare) > , apoi
    set [scor v mare] la (scor :: variabile)
    cere [scor mare! Care este numele dvs.?] Și așteptați
    setați [nume v] la (răspuns)
capăt
oprire [toate v]
```

If you need to change any of the 'Game over' code, for example to add a sound or change the 'Game over' message, you have to change it four times. That's annoying and wastes a lot of time.

Instead, you can define your own code block, and use it anywhere in your project.

\--- task \---

Click on `My blocks`{:class="block3myblocks"}, and then on **Make a Block**. Call this new block `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Add the code from the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast to the `Game over`{:class="block3myblocks"} block so that it looks like this:

![ballerina](images/ballerina.png)

```blocks3
defini Joc de peste
spun [Joc de peste!] pentru (1) secunde
în cazul în care < (scor :: variabile) > (scor ridicat) > apoi
    set [mare scor v] pentru a (scor :: variabile)
    cere [scor ridicat ! Care este numele dvs.?] Și așteptați
    setați [nume v] la (răspuns)
capăt
oprire [toate v]
```

\--- /task \---

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks3
atunci când primesc [v red]
dacă <(punctul (1 v) din [secvență v]) =[1]> , apoi
    tambur joc (\ (1 \) Snare Drum v) pentru (0,25) bate
    șterge (1 v) din [secventa v]
altfel
    Joc peste :: personalizat
sfarsit
```

\--- /task \---

\--- task \---

Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence.

\--- /task \---

Your new `Game over`{:class="block3myblocks"} block is a **function**, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="block3myblocks"} block in.

\--- task \---

Also replace the code in the `else`{:class="block3control"} block connected to the `broadcasts`{:class="block3events"} for the other colours with your new `Game over`{:class="block3myblocks"} block. Here is what the code for the `blue`{:class="block3events"} message should look like

![ballerina](images/ballerina.png)

```blocks3
atunci când primesc [v blue]
dacă <(punctul (1 v) din [secvență v]) =[1]> , apoi
    tambur joc (\ (2 \) Bass Drum v) pentru (0,25) bate
    șterge (1 v) din [secventa v]
altfel
    Joc peste :: personalizat
sfarsit
```

\--- /task \---

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks3
defini Joc de peste
de pornire a sunetului [Cough1 v]
spun [Joc de peste!] pentru (1) secunde
în cazul în care < (scor :: variabile) > (scor ridicat) > , apoi
    sunet redare (trumpet1 v)
    set [scor mare v] la (scor)
    cere [Scor mare! Care este numele dvs.?] Și așteptați
    setați [nume v] la (răspuns)
capăt
oprire [toate v]
```

\--- /task \---