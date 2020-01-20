## Record

Ora salva il punteggio più alto in modo da poter sfidare i tuoi amici.

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
se < > allora
end

(punteggio)

(punteggio)

[ ] > [ ]

(risposta)

(record)

chiedi [What's your name?] e attendi

porta [record v] a [ ]

porta [nome v] a [ ] 
```

\--- /hint \---

\--- hint \---

Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

```blocks3
quando ricevo [rosso v]
se <(elemento (1 v) di [sequenza v]) = [1]> allora 
  suona il tamburo (elemento (1 v) di [sequenza v]) per (0.25) battute
  cancella (1 v) da [sequenza v]
altrimenti 
  dire [Hai perso!] per (1) secondi
  se <(punteggio :: variables) > (punteggio record) > allora 
    porta [record v] a (punteggio :: variables)  chiedi [Nuovo record! Come ti chiami?] e attendi
    porta [nome v] a (risposta)
  end
  ferma [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks3
dire [Hai perso!] per (1) secondi
se <(punteggio :: variables) > (punteggio record)> allora 
  porta [record v] a (punteggio :: variables) chiedi [Nuovo record! Come ti chiami?] e attendi
  porta [nome v] a (risposta)
end
ferma [all v]
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
definisci Game over
say [Hai perso!] per (1) secondi
se <(punteggio :: variables) > (Punteggio record) > then
porta [record v] a (punteggio) chiedi [Nuovo record! Come ti chiami?] e attendi
porta [nome v] a (risposta)
end
ferma [all v]
```

\--- /task \---

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks3
quando ricevo [rosso v]
se <(elemento (1 v) di [sequenza v]) = [1]> allora 
  suona il tamburo ((1) Snare Drum v) per (0.25) battute
  cancella (1 v) da [sequenza v]
altrimenti 
  Game over :: custom
end
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
quando ricevo [blu v]
se <(elemento (1 v) di [sequenza v]) = [1]> allora 
  suona il tamburo ((2) Bass Drum v) per (0.25) battute
  cancella (1 v) da [sequenza v]
altrimenti 
  Game over :: custom
end
```

\--- /task \---

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks3
definisci Game over
avvia riproduzione suono [Cough1 v]
dì [Hai perso!] per (1) secondi
se <(punteggio :: variables) > (Punteggio record) > poi
suono play (trumpet1 v)
porta [Punteggio record v] a (punteggio) chiedi [Nuovo record! Come ti chiami?] e attendi
porta [nome v] a (risposta)
end
ferma [all v]
```

\--- /task \---