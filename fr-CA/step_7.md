## Défi : Améliore ton jeu

### Faire plus de blocs

Voyez-vous un autre code identique pour les quatre boutons?

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game Over :: custom
end

when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beat
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

Pouvez-vous créer un autre bloc personnalisé que tous les boutons peuvent utiliser?

### Un autre costume

Pouvez-vous voir que votre jeu commence avec votre personnage montrant l'une des quatre couleurs et que le personnage affiche toujours la dernière couleur de la séquence pendant que le joueur répète la séquence de couleurs?

Pouvez-vous ajouter un autre costume blanc uni à votre personnage et ajouter du code pour que le personnage affiche ce costume au début du jeu et pendant que le joueur répète la séquence?

![capture d'écran](images/colour-white.png)

### Niveau de difficulté

Pouvez-vous permettre à votre joueur de choisir entre jouer au jeu en «mode facile» (en utilisant uniquement les couleurs rouge et bleu) et en «mode normal» (qui utilise les quatre couleurs)?

Si vous voulez, vous pouvez même ajouter un mode "dur" qui utilise un cinquième tambour !