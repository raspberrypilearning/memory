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

\--- task \--- Donne à ton personnage quatre costumes, chacun ayant une couleur différente, une par costume pour chacune des couleurs ci-dessus. Assure-toi que les costumes colorés sont dans le même ordre que ci-dessus.

![screenshot](images/colour-costume.png) \--- /task \---

Si tu le souhaites, tu peux utiliser l’outil de ** coloriage de forme **Pour remplir les parties du costume avec une couleur différente.

![color-a-shape](images/color-a-shape.png)

Ensuite, ajoute une liste pour stocker la séquence aléatoire de couleurs que le joueur doit mémoriser.

\--- task \--- Premièrement, ajoute une nouvelle liste appelée `Séquence `{: class = "block3variables"}. Seul le lutin doit avoir besoin de voir cette liste, donc tu peux sélectionner **Pour ce lutin seulement** quand tu crées la liste.

[[[generic-scratch3-make-list]]]

\--- /task \---

Tu devrais maintenant voir beaucoup de nouveaux blocs de code pour utiliser les listes. La liste vide doit être visible dans le coin supérieur gauche de la scène.

![screenshot](images/colour-list-blocks-annotated.png)

Chaque couleur a un numéro différent, tu peux donc choisir une couleur aléatoire en choisissant un nombre au hasard et en l'ajoutant à la liste.

\--- task \--- Ajoute ce code au lutin pour choisir un nombre aléatoire et l'ajouter à la `séquence` {:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
quand le drapeau est cliqué
ajouter (prendre un nombre aléatoire entre (1) et (4)) à [séquence v]
```

\--- /task \---

\--- task \--- Teste ton code. Vérifie que, chaque fois que tu cliques sur le drapeau, un chiffre aléatoire entre 1 et 4 est ajouté à la liste. \--- /task \---

\--- task \--- Peux-tu ajouter du code à ton programme qui génère cinq chiffres aléatoires en même temps ?

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