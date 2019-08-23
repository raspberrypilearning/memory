## Crée une séquence de couleurs

Premièrement, crée un personnage qui puisse afficher des séquences de couleurs aléatoires.

—- task —- Ouvre un nouveau projet scratch.

**En ligne**: ouvre un nouveau projet scratch à [rpf.io/scratch-new](https://rpf.io/scratchon).

**Hors-ligne**: ouvre Un nouveau projet dans l’éditeur hors-ligne.

Si tu as besoin de télécharger et d’installer l’éditeur Scratch hors-ligne, tu peux le trouver ici : [rpf.io/scratchoff](https://rpf.io/scratchoff).

\--- /task \---

\--- task \--- Choisis un personnage (lutin) et un arrière-plan. Tu peux utiliser la ballerine, mais ton lutin ne dois pas forcément être une personne, il doit seulement être capable de montrer différentes couleurs.

![capture d'écran](images/colour-sprite.png) \--- /task \---

+ Ton jeu doit utiliser différents nombres afin de représenter chaque couleur :
    
    + 1 = rouge
    + 2 = bleu
    + 3 = vert
    + 4 = jaune

\--- task \--- Donne à ton personnage quatre costumes, chacun ayant une couleur différente, une par costume pour chacune des couleurs ci-dessus. Assure-toi que les costumes colorés sont dans le même ordre que ci-dessus.

![capture d'écran](images/colour-costume.png) \--- /task \---

Si tu le souhaites, tu peux utiliser l’outil de ** coloriage de forme **Pour remplir les parties du costume avec une couleur différente.

![colorer une forme](images/color-a-shape.png)

Ensuite, ajoute une liste pour stocker la séquence aléatoire de couleurs que le joueur doit mémoriser.

\--- task \--- Premièrement, ajoute une nouvelle liste appelée `Séquence `{: class = "block3variables"}. Seul le lutin doit avoir besoin de voir cette liste, donc tu peux sélectionner **Pour ce lutin seulement** quand tu crées la liste.

[[[generic-scratch3-make-list]]]

\--- /task \---

Tu devrais maintenant voir beaucoup de nouveaux blocs de code pour utiliser les listes. La liste vide doit être visible dans le coin supérieur gauche de la scène.

![capture d'écran](images/colour-list-blocks-annotated.png)

Chaque couleur a un numéro différent, tu peux donc choisir une couleur aléatoire en choisissant un nombre au hasard et en l'ajoutant à la liste.

\--- task \--- Ajoute ce code au lutin pour choisir un nombre aléatoire et l'ajouter à la `séquence` {:class="block3variables"}:

![ballerine](images/ballerina.png)

```blocks3
quand le drapeau est cliqué
ajouter (prendre un nombre aléatoire entre (1) et (4)) à [séquence v]
```

\--- /task \---

\--- task \--- Teste ton code. Vérifie que, chaque fois que tu cliques sur le drapeau, un chiffre aléatoire entre 1 et 4 est ajouté à la liste. \--- /task \---

\--- task \--- Peux-tu ajouter du code à ton programme qui génère cinq chiffres aléatoires en même temps ?

\--- hints \--- \--- hint \--- Ajoute `supprimer tout de la séquence`{:class="block3variables"} pour supprimer premièrement tous les éléments de la liste, puis ajoute un bloc ` répéter `{:class="block3control"} qui va ajouter 5 nombres aléatoires à la liste. \--- /hint \--- \--- hint \---

Voici à quoi ton code devrait ressembler :

![ballerine](images/ballerina.png)

```blocks3
quand le drapeau est cliqué
supprimer tous les éléments de la liste [v]
---répéter 5 fois :
| ajouter (nombre aléatoire entre (1) et (4)) à [séquence v]
---
stop tout
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Chaque fois qu'un nombre est ajouté à la liste, le personnage doit changer son costume de sorte à ce que la couleur du costume corresponde au nombre. Ajoute ce code au lutin pour choisir un nombre aléatoire et l'ajouter à la `séquence` {:class="block3variables"}:

![ballerine](images/ballerina.png)

```blocks3
basculer vers le costume (élément (longueur de la séquence [v] de séquence [v])
```

\--- /task \---