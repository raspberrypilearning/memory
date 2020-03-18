## Défi : Améliore ton jeu

### Faire plus de blocs

Vois-tu un autre code qui est le même pour les quatre boutons ?

```blocks3
quand je reçois [rouge v]
si <(élément (1 v) de [séquence v]) = [1]> alors 
  jouer du tambour ((1) Caisse claire v) pendant (0.25) temps
  supprimer l'élément (1 v) de [séquence v]
sinon 
  perdu :: custom
fin

quand je reçois [bleu v]
si <(élément (1 v) de [séquence v]) = [1]> alors 
  jouer du tambour ((2) Grosse caisse v) pendant (0.25) temps
  supprimer l'élément (1 v) de [séquence v]
sinon 
  perdu :: custom
fin
```

Peux-tu créer un autre bloc personnalisé que tous les boutons peuvent utiliser ?

### Un autre costume

Peux-tu voir que ton jeu commence avec ton personnage montrant une des quatre couleurs, et que le personnage affiche toujours la dernière couleur dans la séquence pendant que le joueur répète la séquence de couleur ?

Peux-tu ajouter un autre costume blanc à ton personnage, et ajoute du code pour que le personnage affiche ce costume au début du jeu et pendant que le joueur répète la séquence ?

![capture d'écran](images/colour-white.png)

### Niveau de difficulté

Peux-tu permettre à ton joueur de choisir entre jouer au jeu en mode « facile » (en utilisant uniquement les couleurs rouge et bleu) et « mode normal » (qui utilise les quatre couleurs) ?

Si tu veux, tu peux même ajouter un mode « difficile » qui utilise un cinquième tambour !