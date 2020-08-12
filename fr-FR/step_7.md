## Défi : Améliore ton jeu

### Faire plus de blocs

Vois-tu un autre code qui est le même pour les quatre boutons ?

```blocks3
when I receive [rouge v]
if <(item (1 v) of [séquence v])=[1]> then
	play drum (\(1\) Snare Drum v) for (0.25) beats
	delete (1 v) of [séquence v]
else
	perdu :: custom
end

when I receive [bleu v]
if <(item (1 v) of [séquence v])=[1]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [séquence v]
else
	perdu :: custom
end
```

Peux-tu créer un autre bloc personnalisé que tous les boutons peuvent utiliser ?

### Un autre costume

Peux-tu voir que ton jeu commence avec ton personnage montrant une des quatre couleurs, et que le personnage affiche toujours la dernière couleur dans la séquence pendant que le joueur répète la séquence de couleur ?

Peux-tu ajouter un autre costume blanc à ton personnage, et ajoute du code pour que le personnage affiche ce costume au début du jeu et pendant que le joueur répète la séquence ?

![capture d'écran](images/colour-white.png)

### Niveau de difficulté

Peux-tu permettre à ton joueur de choisir entre jouer au jeu en mode « facile » (en utilisant uniquement les couleurs rouge et bleu) et « mode normal » (qui utilise les quatre couleurs) ?

Si tu veux, tu peux même ajouter un mode « difficile » qui utilise un cinquième tambour !