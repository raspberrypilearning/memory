## Meilleur score

Maintenant sauvegarde le meilleur score pour pouvoir jouer contre tes amis.

\--- task \---

Ajoute deux nouvelles variables appelées `meilleur score`{:class="block3variables"} et `nom`{:class="block3variables"} à ton projet.

\--- /task \---

Lorsque le jeu se termine parce que le joueur donne une mauvaise séquence, le jeu doit vérifier si le score est supérieur au meilleur score actuel. Si c'est le cas, le jeu devrait enregistrer le score comme le meilleur score, et aussi stocker le nom du joueur.

\--- task \---

Ajoute du code à ton sprite personnage pour stocker le `meilleur score`{:class="block3variables"}. Demande également le nom du joueur, et stocke-le dans la variable `nom`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Ton nouveau code doit suivre ce modèle :

Après le message ` perdu` {: class = "block3looks"} ` Si ` {:class="block3control"} le ` score ` {:class="block3variables"} est ` supérieur à ` {:class="block3operators"} le ` meilleur score ` {:class="block3variables"} ` Définir ` {:class="block3variables"} le ` meilleur score ` {:class="block3variables"} au ` score` {:class="block3variables"} ` Demander ` {:class="block3sensing"} le nom du joueur ` mettre ` {:class="block3variables"}` la réponse` {:class="block3sensing"} dans le ` nom ` {:class="block3variables"}

\--- /hint \---

\--- hint \---

Tu as besoin des blocs suivants :

![ballerine](images/ballerina.png)

```blocks3
si <> alors
fin

(score)

(score)

[ ] > [ ]

(réponse)

(meilleur score)

demander [Quel est ton nom?] et attendre

mettre [meilleur score v] à [ ]

mettre [nom v] à [ ] 
```

\--- /hint \---

\--- hint \---

Voici à quoi devrait ressembler ton code lorsque le bouton rouge est pressé :

![ballerine](images/ballerina.png)

```blocks3
quand je reçois [rouge v]
si <(élément (1 v) de [séquence v]) = [1]> alors 
  jouer du tambour (élément (1 v) de [séquence v]) pendant (0.25) temps
  supprimer l'élément (1 v) de [séquence v]
sinon 
  dire [Perdu!] pendant (1) secondes
  si <(score :: variables) > (meilleur score)> alors 
    mettre [meilleur score v] à (score :: variables)
    Demander [Meilleur score!
 Quel est ton nom?\] et attendre
mettre [nom v] à (réponse)
fin
stop [tout v]

fin
```

\--- /hint \---

\--- /hints \---

\--- /task \---

Tu dois ajouter ce nouveau code au sprite personnage pour les trois autres couleurs aussi !

Peux-tu voir que le code « Perdu » pour chacune des quatre couleurs est exactement le même ?

![ballerine](images/ballerina.png)

```blocks3
dire [Perdu!] pendant (1) secondes
si <(score :: variables) > (meilleur score)> alors 
  mettre [meilleur score v] à (score :: variables)
  Demander [Meilleur score! Quel est ton nom?\] et attendre
mettre [nom v] à (réponse)
fin
stop [tout v]
```

Si tu as besoin de changer l'un des codes « Perdu », par exemple pour ajouter un son ou changer le message « Perdu », tu dois le modifier quatre fois. C'est ennuyeux et on perd beaucoup de temps.

Au lieu de cela, tu peux définir ton propre bloc de code et l'utiliser n'importe où dans ton projet.

\--- task \---

Clique sur `Mes blocs`{:class="block3myblocks"}, puis sur **Créer un bloc**. Appelle ce nouveau bloc `perdu`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Ajoute le code du bloc `sinon`{:class="block3control"} connecté au bloc `rouge`{:class="block3events"} envoyer à tous au bloc `perdu`{:class="block3myblocks"} pour qu'il ressemble à ceci :

![ballerine](images/ballerina.png)

```blocks3
définir perdu
dire [Perdu!] pendant (1) secondes
si <(score :: variables) > (meilleur score)> alors 
  mettre [meilleur score v] à (score :: variables)
  demander [meilleur score! Qeul est ton nom?\] et attendre
mettre [nom v] à (réponse)
fin
stop [tout v]
```

\--- /task \---

\--- task \---

Maintenant, supprime le code qui se trouve dans le bloc ` sinon ` {: class = "block3control"} connecté au programme ` rouge ` {:class="block3events"} et ajoute le bloc ` perdu ` {:class="block3myblocks"} à la place :

![ballerine](images/ballerina.png)

```blocks3
quand je reçois [rouge v]
si <(élément (1 v) de [séquence v]) = [1]> alors 
  jouer du tambour ((1) Caisse claire v) pendant (0.25) temps
  supprimer l'élément (1 v) de [séquence v]
sinon 
  perdu :: custom
fin
```

\--- /task \---

\--- task \---

Teste ton nouveau bloc en jouant au jeu et en cliquant sur le bouton rouge au mauvais point de la séquence de couleurs.

\--- /task \---

Ton nouveau bloc `perdu`{:class="block3myblocks"} est une **fonction**, un petit script que tu peux utiliser où tu veux dans ton code en ajoutant le bloc `perdu`{:class="block3myblocks"}.

\--- task \---

Remplace également le code dans le bloc `sinon`{:class="block3control"} connecté au bloc `message`{:class="block3events"} pour les autres couleurs avec ton nouveau bloc `perdu`{:class="block3myblocks"}. Voici à quoi devrait ressembler le code pour le message `bleu`{:class="block3events"}

![ballerine](images/ballerina.png)

```blocks3
quand je reçois [bleu v]
si <(élément (1 v) de [séquence v]) = [1]> alors 
  jouer du tambour ((2) Grosse caisse v) pendant (0.25) temps
  supprimer l'élément (1 v) de [séquence v]
sinon 
  perdu :: custom
fin
```

\--- /task \---

\--- task \---

Maintenant, ajoute un son qui joue lorsque le mauvais bouton est enfoncé. Tu n'as besoin d'ajouter ce code qu'une seule fois dans le bloc `perdu`{:class="block3myblocks"} que tu as fait, et non pas quatre fois séparés !

![ballerine](images/ballerina.png)

```blocks3
définir perdu
jouer le son [Cough1 v]
dire [Perdu!] pendant (1) secondes
si <(score :: variables) > (meilleur score)> alors 
  jouer le son (trombone v)
  mettre [meilleur score v] à (score)
  demander [Meilleur score! Quel est ton nom?\] et attendre
mettre [nom v] à (réponse)
fin
stop [tout v]
```

\--- /task \---