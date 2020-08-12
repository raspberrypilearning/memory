## Ajouter du son

--- task ---

Teste ton projet plusieurs fois. As-tu remarqué que des fois, le même nombre est choisi deux fois (ou plus) à la suite, ce qui rend la séquence plus difficile à mémoriser ?

--- /task ---

Peux-tu mettre un son de batterie à chaque fois que le sprite personnage change de costume ? Et que dirais-tu d'un son de batterie différent pour chaque couleur ?

--- task ---

Ajoute l'extension Musique à ton projet de sorte à pouvoir utiliser le bloc `jouer du tambour`{:class="block3extensions"} .

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

Le code qui joue de la batterie est **très** similaire au code qui change le costume du personnage.

--- hints ---


--- hint ---

Tu dois seulement ajouter deux blocs : un bloc `jouer le tambour pour (0.25) temps`{:class="block3sound"} et un bloc `élément (longueur de la séquence)`{:class="block3variables"}.

--- /hint ---

--- hint ---

Voici les blocs dont tu auras besoin :

![ballerine](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [séquence v]) of [séquence v])
```

--- /hint ---

--- hint ---

Voici à quoi devrait ressembler ton code fini :

![ballerine](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [séquence v]
repeat (5)
	add (pick random (1) to (4)) to [séquence v]
    play drum (item (length of [séquence v]) of [séquence v]) for (0.25) beats
    switch costume to (item (length of [séquence v]) of [séquence v])
    wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---