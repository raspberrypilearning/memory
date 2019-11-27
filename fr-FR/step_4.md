## Répéter la séquence

Maintenant, tu vas ajouter quatre boutons sur lesquels le joueur doit appuyer pour répéter la séquence de couleurs.

\--- task \--- Ajoute quatre nouveaux lutins à ton projet pour représenter les quatre boutons.

+ Modifie les costumes des nouveaux lutins de manière à ce qu'il y ait un lutin dans chacune des quatre couleurs
+ Place les lutins dans le même ordre sur la scène que les costumes : rouge, bleu, vert et jaune

![capture d'écran](images/colour-drums.png) \--- /task \---

\--- task \--- Ajoute du code au lutin rouge pour que, lorsqu'il est cliqué, il `envoie à tous`{:class="block3events"} le message 'rouge' :

![tambour rouge](images/red_drum.png)

```blocks3
    quand ce lutin est cliqué
    envoyer à tous (rouge)
```

\--- /task \---

Un `envoyer à tous`{:class="block3events"} est comme une annonce par haut-parleur : elle doit être entendue par tous les lutins. Tous les lutins peuvent entendre le ` envoyer à tous `{:class="block3events"}, mais seulement le lutin dont le travail consiste à répondre fera quelque chose.

\--- task \---

Ajoute un code similaire aux lutins bleu, vert et jaune pour les faire faire ` envoyer à tous `{:class="block3events"} un message à propos de leur propre couleur.

\--- /task \---

Te souviens-tu que le ` Envoyer à tous `{:class="block3events"} est comme un message de haut-parleur ? Tu ajouteras un code pour faire en sorte que le lutin principal réponde à la diffusion du message `Envoyer à tous`{:class="block3events"} .

\--- task \---

Quand ton sprite reçoit le message `rouge`{:class="block3events"}, le code doit vérifier si le nombre ` 1 ` est au début de la ` séquence `{:class="block3variables"} (ce qui signifie que ` rouge `{:class="block3events"} est la prochaine couleur de la séquence).

If `1` is at the start of the list, the code should remove the number from the list, because the player remembered the correct colour. Otherwise it's game over, and the code needs to `stop all`{:class="block3control"} to end the game.

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /task \---

\--- task \--- Add to the code you just wrote so that a drum beat also plays when the character sprite receives the correct `broadcast`{:class="block3events"}.

\--- hints \--- \--- hint \--- Can you use the numbers that correspond to each colour to play the correct drum beat?

+ 1 = red
+ 2 = blue
+ 3 = green
+ 4 = yellow \--- /hint \--- \--- hint \--- Above the `delete 1 of sequence`{:class="block3variables"} block, add the `play drum`{:class="block3sound"} block to play the first sound in the `sequence`{:class="block3variables"} list.

\--- /hint \--- \--- hint \--- Here is the code you will need to add:

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then

+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end

```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Duplicate the code you used to make your character sprite respond to the message `red`{:class="block3events"}. Change the duplicated code so that it sends the message `blue`{:class="block3events"}. \--- /task \---

When the sprite responds to the message `blue`{:class="block3events"}, which bit of code should stay the same, and which bit should change? Remember that each colour has a corresponding number.

\--- task \--- Change the character sprite's code so that the character responds correctly to the `blue`{:class="block3events"} message.

\--- hints \--- \--- hint \---

Keep these blocks, but you need to change them in some way:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

\--- /hint \--- \--- hint \--- Here is how your code should look for the `blue`{:class="block3events"} broadcast.

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[2]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    stop [all v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Duplicate the code again twice (for the green and yellow buttons), and change the necessary parts so that the character responds correctly to the new `broadcasts`{:class="block3events"} . \--- /task \---

Remember to test the code! Can you memorise a sequence of five colours? Is the sequence different each time?

When the player repeats the whole colour sequence correctly, the `sequence`{:class="block3variables"} list emtpy and the player wins. If you want, you can also display some flashing lights as a reward once the `sequence`{:class="block3variables"} list is empty.

\--- task \--- Add this code to the end of your character's `when flag clicked`{:class="block3events"} script:

![ballerina](images/ballerina.png)

```blocks3
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
```

\--- /task \---

\--- task \--- Switch to the Stage, and import the `drum machine` sound or another sound you like.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \--- Add this code to play a sound and make the backdrop change colour when the player wins.

![ballerina](images/stage.png)

```blocks3
    when I receive [won v]
    start sound (drum machine v)
    repeat (50)
        change [color v] effect by (25)
        wait (0.1) seconds
    end
    clear graphic effects
```

\--- /task \---