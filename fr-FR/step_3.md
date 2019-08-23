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

The code that plays the drum is **very** similar to the code that changes the character's costume.

\--- hints \--- \--- hint \--- You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block. \--- /hint \--- \--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \--- Here is how your finished code should look:

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