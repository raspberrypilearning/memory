## Creează o secvenţă de culori

Mai întâi creați un caracter care poate afișa o secvență aleatoare de culori.

\--- task \--- Deschide un nou proiect Scratch.

**Online**: open a new online Scratch project at [rpf.io/scratch-new](https://rpf.io/scratchon).

**Offline**: deschideți un nou proiect în editorul offline.

Dacă trebuie să descărcați și să instalați editorul Scratch offline, îl puteți găsi la [rpf.io/scratchoff](https://rpf.io/scratchoff).

\--- /task \---

\--- task \--- Alege un sprite de caractere și un fundal. Ai putea folosi balerina, dar personajul tău nu trebuie să fie o persoană, trebuie doar să poată arăta culori diferite.

![captură de ecran](images/colour-sprite.png) \--- /task \---

+ Jocul dvs. ar trebui să utilizeze un număr diferit pentru a reprezenta fiecare culoare:
    
    + 1 = roșu
    + 2 = albastru
    + 3 = verde
    + 4 = galben

\--- task \--- Dă personajul tău patru costume care au culori diferite, câte un costum pentru fiecare dintre cele patru culori prezentate mai sus. Asigurați-vă că costumele dvs. colorate sunt în aceeași ordine ca și lista de mai sus.

![captură de ecran](images/colour-costume.png) \--- /task \---

Dacă doriți, puteți utiliza instrumentul de culoare **forma** pentru a umple părțile costumului cu o altă culoare.

![culoare-o formă](images/color-a-shape.png)

Apoi, adăugați o listă pentru stocarea secvenței aleatoare a culorilor pe care playerul trebuie să o rețină.

\--- task \--- Creați o listă numită `secvență`{: class = "block3variables"}. Numai caracterul sprite trebuie să vadă această listă, astfel încât să puteți selecta **Pentru această sprite numai** când creați lista.

[[[generic-scratch3-make-list]]]

\--- /task \---

Ar trebui să vedeți acum o mulțime de blocuri de cod noi pentru utilizarea listelor. Lista golităii ar trebui să fie vizibilă în colțul din stânga sus al scenei.

![captură de ecran](images/colour-list-blocks-annotated.png)

Fiecare culoare are un număr diferit, astfel încât să puteți alege o culoare aleatoră prin alegerea aleatorie a unui număr și adăugarea acestuia în listă.

\--- task \--- Adăugați acest cod la caracterul sprite pentru a alege un număr aleator și a adăuga la `secvență`{: class = "block3variables"}:

![balerină](images/ballerina.png)

```blocks3
atunci când faceți clic pe pavilion
adăugați (alegeți aleatoriu (1) la (4)) la [secvența v]
```

\--- /task \---

\--- task \--- Testați-vă codul. Verificați că, de fiecare dată când faceți clic pe pavilion, un număr aleator între 1 și 4 se adaugă la listă. \--- / sarcina \---

\--- task \--- Puteți adăuga codul programului dvs. pentru a genera cinci numere aleatorii dintr-o dată?

\--- indicii \--- \--- indiciu \--- Adăugați o `șterge toate secvenței`{: class = „block3variables“} pentru a șterge mai întâi toate elementele de pe listă, și apoi se adaugă o `repetare`{block: block3control}} care adaugă cinci numere aleatorii în listă. \--- / indiciu \--- \--- indiciu \---

Acesta ar trebui să arate codul dvs.:

![balerină](images/ballerina.png)

```blocks3
când pavilion apasat
șterge (toate v) [secvență v]
repeat (5)
    add (alege aleator (1) la (4)) la [secvență v]
capăt
```

\--- / indiciu \--- \--- / sugestii \--- \--- / sarcina \---

\--- task \--- De fiecare dată când un număr se adaugă la listă, personajul trebuie să-și schimbe costumul, astfel încât culoarea costumului să se potrivească cu numărul. Pune aceste blocuri în codul imediat mai jos în cazul în care se adaugă un număr aleatoriu la `secvență de`{: class = „block3variables“}:

![balerină](images/ballerina.png)

```blocks3
comutați costumul la (elementul (lungimea secvenței v) a secvenței v)
așteptați (1) secunde
```

\--- /task \---