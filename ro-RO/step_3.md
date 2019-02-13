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

\--- sugestii \--- \--- indiciu \--- Doar trebuie sa adaugati doua blocuri: un tambur de `jucari pentru (0.25) batai`{: class = "block3sound"} bloc si un element `(lungimea secvență) din blocul secvenței`{: class = "block3variables"}. \--- / indiciu \--- \--- indiciu \---

Iată blocurile de care aveți nevoie:

![balerină](images/ballerina.png)

```blocks3
juca tambur (\ (1 \) Snare Drum v) pentru (0.25) bate

(element (lungime de secventa v)) [secventa v]
```

\--- / indiciu \---

\--- hint \--- Aici este modul în care ar trebui să arate codul dvs. finit:

![balerină](images/ballerina.png)

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

\--- / indiciu \---

\--- / sugestii \---

\--- /task \---