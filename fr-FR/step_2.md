## Crée une séquence de couleurs

Premièrement, crée un personnage qui puisse afficher des séquences de couleurs aléatoires.

—- task —- Ouvre un nouveau projet scratch.

**En ligne**: ouvre un nouveau projet scratch à [rpf.io/scratch-new](https://rpf.io/scratchon).

**Hors-ligne**: ouvre Un nouveau projet dans l’éditeur hors-ligne.

Si tu as besoin de télécharger et d’installer l’éditeur Scratch hors-ligne, tu peux le trouver ici : [rpf.io/scratchoff](https://rpf.io/scratchoff).

\--- /task \---

\--- task \--- Choisis un personnage (lutin) et un arrière-plan. Tu peux utiliser la ballerine, mais ton lutin ne dois pas forcément être une personne, il doit seulement être capable de montrer différentes couleurs.

![screenshot](images/colour-sprite.png) \--- /task \---

+ Ton jeu doit utiliser différents nombres afin de représenter chaque couleur :
    
    + 1 = rouge
    + 2 = bleu
    + 3 = vert
    + 4 = jaune

—- task —- Donne à ton personnage quatre costumes, chacun ayant une couleur différente, une par costume pour chacune des couleurs ci-dessus. Assure-toi que les costumes colorés sont dans le même ordre que ci-dessus.

![screenshot](images/colour-costume.png) \--- /task \---

Si tu le souhaites, tu peux utiliser l’outil de ** coloriage de forme **Pour remplir les parties du costume avec une couleur différente.

![color-a-shape](images/color-a-shape.png)

Ensuite, ajoute une liste pour stocker la séquence aléatoire de couleurs que le joueur doit mémoriser.

\--- task \--- Premièrement, ajoute une nouvelle liste appelée `Séquence `{: class = "block3variables"}. Seul le lutin doit avoir besoin de voir cette liste, donc tu peux sélectionner **Pour ce lutin seulement** quand tu crées la liste.

[[[generic-scratch3-make-list]]]

\--- /task \---

You should now see lots of new code blocks for using lists. The empty list should be visible in the top left-hand corner of the Stage.

![screenshot](images/colour-list-blocks-annotated.png)

Each colour has a different number, so you can choose a random colour by randomly choosing a number and adding it to the list.

\--- task \--- Add this code to the character sprite to choose a random number and add it to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
add (pick random (1) to (4)) to [sequence v]
```

\--- /task \---

\--- task \--- Test your code. Check that, each time you click the flag, a random number between 1 and 4 gets added to the list. \--- /task \---

\--- task \--- Can you add code to your program to generate five random numbers at once?

\--- hints \--- \--- hint \--- Add a `delete all of sequence`{:class="block3variables"} to first delete all the items on the list, and then add a `repeat`{:class="block3control"} block that adds five random numbers to the list. \--- /hint \--- \--- hint \---

This is what your code should look like:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Each time a number gets added to the list, the character should change its costume so the costume's colour matches the number. Put these blocks into your code immediately below where a random number is added to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
switch costume to (item (length of [sequence v]) of [sequence v])
wait (1) seconds
```

\--- /task \---