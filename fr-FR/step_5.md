## Multiples niveaux

Jusqu'à présent, le joueur n'a qu'à se souvenir d'une séquence de cinq couleurs. Améliore ton jeu en ajoutant un score, et du code pour que le joueur marque des points. Le jeu passe au niveau suivant et la séquence de couleurs à retenir devient plus longue.

--- task ---

Crée une nouvelle variable appelée `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

--- /task ---

Basé sur le `score`{:class="block3variables"}, le jeu décidera de la longueur de la séquence de couleurs. Commence par un score (et une longueur de séquence) de `3`.

--- task ---

Ajoute un bloc au début du code de ton personnage `quand le drapeau est cliqué`{:class="block3events"} pour définir le `score`{:class="block3variables"} à `3`.

--- /task ---

Au lieu de toujours créer une séquence de cinq couleurs, tu veux maintenant que le `score`{:class="block3variables"} détermine la longueur de la séquence.

--- task ---

Change la boucle `répéter (5) fois`{:class="block3control"} du personnage (pour créer la séquence de couleur) pour répéter `score`{:class="block3variables"} fois :

![sprites](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

--- /task ---

--- task ---

Si le joueur répète la séquence correcte, tu devras ajouter `1` à `score`{:class="block3variables"}, ce qui augmente la longueur de la séquence suivante. Ajoute le bloc suivant au code du personnage **au moment où tu sais que la séquence est correcte**:

![sprites](images/ballerina.png)

```blocks3
change [score v] by (1)
```

--- hints ---


--- hint ---

Tu sais que la séquence est correcte au moment où le jeu `envoie`{:class="block3events"} le message « gagné ».

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

Enfin, ajoute une boucle `répéter indéfiniment`{:class="block3control"} autour du code qui génère la séquence, de sorte que le jeu crée une nouvelle séquence de couleurs pour chaque niveau. Voici à quoi le code de ton personnage pourrait ressembler :

![ballerine](images/ballerina.png)

```blocks3
when flag clicked
set [score v] to [3]
forever
	delete (all v) of [séquence v]
	repeat (score)
		add (pick random (1) to (4)) to [séquence v]
		switch costume to (item (length of [séquence v]) of [séquence v]
		wait (1) seconds
	end
	wait until < (length of [séquence v]) = [0]>
	broadcast (gagné v) and wait
	change [score v] by (1)
end
```

--- /task ---

--- task ---

Amène tes amis à tester ton jeu. N'oublie pas de cacher la liste `séquence`{:class="block3variables"} avant de jouer !

--- /task ---