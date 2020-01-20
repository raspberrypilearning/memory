## Ajouter du son

\--- task \---

Teste ton projet plusieurs fois. As-tu remarqué que des fois, le même nombre est choisi deux fois (ou plus) dans la suite, ce qui rend la séquence plus difficile à mémoriser ?

\--- /task \---

Peux-tu mettre un son de batterie à chaque fois que le personnage change de costume ? Et que dis-tu d'un son de batterie différent pour chaque couleur ?

\--- task \---

Ajoute l'extension Musique à ton projet de sorte à pouvoir utiliser le bloc ` jouer de la batterie `{:class="block3extensions"} .

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

Le code qui joue de la batterieest ** très ** similaire au code qui change le costume du personnage.

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /hint \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
jouer de la batterie (\(1\) caisse claire v) pour (0.25) battements

(élément (longueur de [séquence v) de [séquence v])
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

```blocks3
quand le drapeau est cliqué
supprimer (toutes les valeurs) de [séquence v]
répéter (5) fois
    ajouter (nombre aléatoire entre (1) et (4)) à la [séquence v]
    jouer de la batterie (élément (longueur de la [séquence v]) de la  [séquence v]) pour (0.25) battements
    changer le costume à (élément (longueur de la [éequence v]) de la [séquence v])
    attendre (1) secondes
fin
```

\--- /hint \---

\--- /hints \---

\--- /task \---