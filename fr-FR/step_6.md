## Meilleur score

Maintenant sauvegarde le meilleur score pour pouvoir jouer contre tes amis.

--- task ---

Ajoute deux nouvelles variables appelées `meilleur score`{:class="block3variables"} et `nom`{:class="block3variables"} à ton projet.

--- /task ---

Lorsque le jeu se termine parce que le joueur donne une mauvaise séquence, le jeu doit vérifier si le score est supérieur au meilleur score actuel. Si c'est le cas, le jeu devrait enregistrer le score comme le meilleur score, et aussi stocker le nom du joueur.

--- task ---

Ajoute du code à ton sprite personnage pour stocker le `meilleur score`{:class="block3variables"}. Demande également le nom du joueur, et stocke-le dans la variable `nom`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

--- hints ---

--- hint ---

Ton nouveau code doit suivre ce modèle :

Après le message `perdu`{:class="block3looks"} `Si`{:class="block3control"} le `score`{:class="block3variables"} est `supérieur à`{:class="block3operators"} le `meilleur score`{:class="block3variables"} `Définir`{:class="block3variables"} le `meilleur score`{:class="block3variables"} au `score`{:class="block3variables"} `Demander`{:class="block3sensing"} le nom du joueur `mettre`{:class="block3variables"} `la réponse`{:class="block3sensing"} dans le `nom`{:class="block3variables"}

--- /hint ---

--- hint ---

Tu as besoin des blocs suivants :

![ballerine](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(meilleur score)

ask [Quel est ton nom ?] and wait

set [meilleur score v] to [ ] 

set [nom v] to [ ] 
```

--- /hint ---

--- hint ---

Voici à quoi devrait ressembler ton code lorsque le bouton rouge est pressé :

![ballerine](images/ballerina.png)

```blocks3
when I receive [rouge v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	say [Perdu!] for (1) seconds
	if < (score :: variables) > (meilleur score) > then
		set [meilleur score v] to (score :: variables)
		ask [Meilleur score! Quel est ton nom ?] and wait
		set [nom v] to (answer)
	end
	stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

Tu dois ajouter ce nouveau code au sprite personnage pour les trois autres couleurs aussi !

Peux-tu voir que le code « Perdu » pour chacune des quatre couleurs est exactement le même ?

![ballerine](images/ballerina.png)

```blocks3
say [Perdu!] for (1) seconds
if < (score :: variables) > (meilleur score) > then
	set [meilleur score v] to (score :: variables)
	ask [Meilleur score! Quel est ton nom ?] and wait
	set [nom v] to (answer)
end
stop [all v]
```

Si tu as besoin de changer l'un des codes « Perdu », par exemple pour ajouter un son ou changer le message « Perdu », tu dois le modifier quatre fois. C'est ennuyeux et on perd beaucoup de temps.

Au lieu de cela, tu peux définir ton propre bloc de code et l'utiliser n'importe où dans ton projet.

--- task ---

Clique sur `Mes blocs`{:class="block3myblocks"}, puis sur **Créer un bloc**. Appelle ce nouveau bloc `perdu`{:class="block3myblocks"}.

--- /task ---

--- task ---

Ajoute le code du bloc `sinon`{:class="block3control"} connecté au bloc `rouge`{:class="block3events"} envoyer à tous au bloc `perdu`{:class="block3myblocks"} pour qu'il ressemble à ceci :

![ballerine](images/ballerina.png)

```blocks3
define perdu
say [Perdu!] for (1) seconds
if < (score :: variables) > (meilleur score) > then
	set [meilleur score v] to (score :: variables)
	ask [Meilleur score! Quel est ton nom ?] and wait
	set [nom v] to (answer)
end
stop [all v]
```

--- /task ---

--- task ---

Maintenant, supprime le code qui se trouve dans le bloc `sinon`{:class="block3control"} connecté au programme `rouge`{:class="block3events"} et ajoute le bloc `perdu`{:class="block3myblocks"} à la place :

![ballerine](images/ballerina.png)

```blocks3
when I receive [rouge v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(1\) Snare Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	perdu :: custom
end
```

--- /task ---

--- task ---

Teste ton nouveau bloc en jouant au jeu et en cliquant sur le bouton rouge au mauvais point de la séquence de couleurs.

--- /task ---

Ton nouveau bloc `perdu`{:class="block3myblocks"} est une **fonction**, un petit script que tu peux utiliser où tu veux dans ton code en ajoutant le bloc `perdu`{:class="block3myblocks"}.

--- task ---

Remplace également le code dans le bloc `sinon`{:class="block3control"} connecté au bloc `message`{:class="block3events"} pour les autres couleurs avec ton nouveau bloc `perdu`{:class="block3myblocks"}. Voici à quoi devrait ressembler le code pour le message `bleu`{:class="block3events"}

![ballerine](images/ballerina.png)

```blocks3
when I receive [bleu v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	perdu :: custom
end
```

--- /task ---

--- task ---

Maintenant, ajoute un son qui joue lorsque le mauvais bouton est enfoncé. Tu n'as besoin d'ajouter ce code qu'une seule fois dans le bloc `perdu`{:class="block3myblocks"} que tu as fait, et non pas quatre fois séparés !

![ballerine](images/ballerina.png)

```blocks3
define perdu
start sound [Cough1 v]
say [Perdu!] for (1) seconds
if < (score :: variables) > (meilleur score) > then
	play sound (trumpet1 v)
	set [meilleur score v] to (score)
	ask [Meilleur score! Quel est ton nom ?] and wait
	set [nom v] to (answer)
end
stop [all v]
```

--- /task ---