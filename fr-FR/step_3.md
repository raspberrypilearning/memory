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

\--- hints \--- \--- hint \--- Il suffit d'ajouter deux blocs : un bloc ` jouer de la batterie pendant (0.25) battements `{:class="block3sound"} et un ` élément (longueur de la séquence) de la séquence ` . \--- /hint \--- \--- hint \---

Voici les blocs dont tu auras besoin :

![ballerina](images/ballerina.png)

```blocks3
jouer de la batterie (\(1\) caisse claire v) pour (0.25) battements

(élément (longueur de [séquence v) de [séquence v])
```

\--- /hint \---

\--- hint \--- Voici à quoi devrait ressembler ton code fini :

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
    play drum (item (length of [sequence v]) of [sequence v]) for (0.25) beats
    switch costume to (item (length of [sequence v]) of [sequence v])
    wait (1) seconds
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---