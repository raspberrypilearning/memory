## Adăugați un sunet

\--- task \---

Testați-vă proiectul de câteva ori. Observi că uneori același număr este ales de două ori (sau mai mult) într-un rând, ceea ce face ca secvența să fie mai greu de memorat?

\--- /task \---

Poți să faci o piesă de sunet cu tambur de fiecare dată când personajul sprite schimbă costumul? Și ce zici de un sunet diferit pentru fiecare culoare?

\--- proba\---

Adăugați extensia Muzică în proiectul dvs. pentru a putea utiliza blocul `jocul tambur`{: class = "block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- proba\---

Codul care joacă tamburul este **foarte** similar cu codul care schimbă costumul personajului.

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- / indiciu \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
juca tambur (\ (1 \) Snare Drum v) pentru (0.25) bate

(element (lungime de secventa v)) [secventa v]
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

```blocks3
când pavilion apasat
șterge (toate v) [secvență v]
repeat (5)
    add (alege aleator (1) la (4)) la [secvența v]
    tambur de redare (element (lungimea [secvență v]) din [secvență v]) pentru (0.25) bate
    costum comutator la (element (lungimea [secvență v]) din [secvență v])
    wait (1) secunde
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---