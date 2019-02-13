## Nivele multiple

Până în prezent, jucătorul trebuie doar să-și amintească o secvență de cinci culori. Îmbunătățiți-vă jocul prin adăugarea unui scor și adăugând un cod, astfel încât, în timp ce jucătorul să înscrie puncte, jocul trece la nivelul următor și secvența de culori pe care trebuie să o memoreze devine mai lungă.

\--- task \--- Creați o nouă variabilă numită `scor`{: class = "block3variables"}.

[[[generic-scratch3-add-variable]]] \--- / sarcina \---

Bazat pe `scor`{: class = „block3variables“}, jocul va decide cu privire la lungimea secvenței de culori. Începeți cu un scor (și o lungime de secvență) de `3`.

\--- task \--- Adăugați un bloc la începutul caracterului dvs. `atunci când ați făcut clic pe codul`{: class = "block3events"} pentru a seta `scor`{: class = "block3variables"} la `3`. \--- /task \---

În loc să creați întotdeauna o secvență de cinci culori, doriți acum `scor`{: class = "block3variables"} pentru a determina lungimea secvenței.

\--- task \--- Modificați bucla (pentru crearea secvenței de culoare) a caracterelor `repeat`{: class = "block3control"} pentru a repeta `scoruri`{: class = "block3variables"} ori:

![personaj](images/ballerina.png)

```blocks3
repetare (scor :: variabile)
sfârșit
```

\--- /task \---

\--- task \--- Dacă jucătorul repetă secvența corectă, ar trebui să adăugați `1` la `scor`{: class = "block3variables"}, și astfel crește lungimea secvenței următoare. Adăugați următorul bloc la codul caracterului **în punctul în care știți că secvența este corectă**:

![personaj](images/ballerina.png)

```blocks3
schimba [scorul v] de către (1)
```

\--- sugestii \--- \--- indiciu \--- Știți că secvența este corectă în momentul în care jocul `transmite`{: class = "block3events"} mesajul "victorie". \--- / indiciu \--- \--- / sugestii \---

\--- /task \---

\--- task \--- În cele din urmă, adăugați o buclă `pentru totdeauna`{: class = "block3control"} în jurul codului care generează secvența, astfel încât jocul să creeze o nouă secvență de culoare pentru fiecare nivel. Acesta este modul în care ar putea arăta codul personajului dvs.

![balerină](images/ballerina.png)

```blocks3
când flag apasat
set [scor v] până la [3]
pentru totdeauna
    șterge (toate v) din [secvență v]
    repeat (scor)
        add (alege aleator (1) la (4)) la [secvență v]
        costum comutator la (elementul (lungimea secvenței v)) a secvenței v
        așteptați 1 secunde
    sfârșitul
    așteptați până la < (lungimea secvenței v) = [0]>
    difuzați (câștigați v) și așteptați
    schimbați [ scor v] de (1)
sfarsit
```

\--- /task \---

\--- task \--- Obțineți-vă prietenii să vă testeze jocul. Nu uitați să ascundeți lista de `secvență`{: class = "block3variables"} înainte de ao reda! \--- / sarcina \---