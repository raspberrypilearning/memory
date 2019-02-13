## Cel mai mare scor

Acum salva scorul mare pentru a putea juca impotriva prietenilor tai.

\--- task \--- Adăugați la proiect două variabile noi denumite `scor mare`{: class = "block3variables"} și `nume`{: class = "block3variables"}. \--- / sarcina \---

Când jocul se termină deoarece jucătorul primește secvența greșită, jocul ar trebui să verifice dacă scorul este mai mare decât scorul curent ridicat. Dacă este, jocul ar trebui să salveze scorul ca scorul mare și să stocheze și numele jucătorului.

\--- task \--- Adăugați codul pentru personajul dvs. sprite pentru a stoca `scor mare`{: class = "block3variables"}. De asemenea, cereți numele jucătorului și păstrați-l în variabila `nume`{: class = "block3variables"}.

[[[generic-scratch3-high-score]]]

\--- sugestii \--- \--- sugestie \--- Codul dvs. nou trebuie să urmeze acest model:

După `joc peste`{: class = "block3looks"} Mesaj `Dacă`{: class = "block3control"} cele `scor`{: class = "block3variables"} este `mai mare de`{: class = "block3operators "} `scor`{: class =" block3variables "} `Set`{: class =" block3variables "} a `mare scor`{: class =" block3variables "} la `scor`{: class =" block3variables "} `Ask`{: class =" block3sensing "} pentru numele jucătorului `Set`{: class =" block3variables "} `nume`{: class =" block3variables "} la `răspuns`{: class = "block3sensing") \--- / indiciu \--- \--- indiciu \---

Aveți nevoie de următoarele blocuri:

![balerină](images/ballerina.png)

```blocks3
dacă < > apoi
final

(scor)

(scor)

[] > []

răspuns

(scor mare)

întrebați [Care este numele tau?] și așteptați

set de [scor v de mare] la [] 

set [ numele v] la [] 
```

\--- / hint \--- \--- sugestie \--- Iată cum codul dvs. pentru atunci când butonul roșu este apăsat ar trebui să arate:

![balerină](images/ballerina.png)

```blocks3
atunci când primesc [v red]
dacă <(punctul (1 v) din [secvență v]) =[1]> , apoi
    tambur de redare (element (1 v) din [secvență v]) pentru (0,25) bate
    șterge (1 v) de la [secventa v]
altceva
    spune [Joc peste!] pentru (1) secunde
    daca < (scor :: variabile) > (scor mare) > apoi
        set [scor mare v] )
        cereți [Scor mare! Care este numele dvs.?] Și așteptați
        setați [nume v] la (răspuns)
    capăt
    oprire [toate v]

```

\--- / indiciu \--- \--- / sugestii \--- \--- / sarcina \---

Trebuie să adăugați acest nou cod la caracterul sprite și pentru celelalte trei culori.

Puteți vedea că codul "Joc peste" pentru fiecare dintre cele patru culori este exact același?

![balerină](images/ballerina.png)

```blocks3
spun [Joc de peste!] pentru (1) secunde
dacă < (scor :: variabile) > (scor mare) > , apoi
    set [scor v mare] la (scor :: variabile)
    cere [scor mare! Care este numele dvs.?] Și așteptați
    setați [nume v] la (răspuns)
capăt
oprire [toate v]
```

Dacă trebuie să schimbați oricare dintre codurile "Joc peste", de exemplu pentru a adăuga un sunet sau pentru a modifica mesajul "Joc peste", trebuie să îl modificați de patru ori. Asta e enervant și pierde mult timp.

În schimb, puteți să vă definiți propriul bloc de cod și să îl utilizați oriunde în proiect.

\--- task \--- Faceți clic pe `blocurile mele`{: class = "block3myblocks"}, apoi pe **Faceți un bloc**. Apelați acest nou bloc `Joc peste`{: class = "block3myblocks"}.

\--- /task \---

\--- sarcina \--- Adăugați codul din blocul `{`} = {block3control}} conectat la `roșu`{: class = "block3events"} difuzat la jocul `peste`{: class = "block3myblocks"} bloc, astfel încât să pară următoarele:

![balerină](images/ballerina.png)

```blocks3
defini Joc de peste
spun [Joc de peste!] pentru (1) secunde
în cazul în care < (scor :: variabile) > (scor ridicat) > apoi
    set [mare scor v] pentru a (scor :: variabile)
    cere [scor ridicat ! Care este numele dvs.?] Și așteptați
    setați [nume v] la (răspuns)
capăt
oprire [toate v]
```

\--- /task \---

\--- task \--- Acum eliminati codul care se afla in blocul `else`{: class = "block3control"} conectat la emisiunea `rosie`{: class = "block3events"} si adaugati in jocul ``{: class = "block3myblocks"}} în loc de bloc:

![balerină](images/ballerina.png)

```blocks3
atunci când primesc [v red]
dacă <(punctul (1 v) din [secvență v]) =[1]> , apoi
    tambur joc (\ (1 \) Snare Drum v) pentru (0,25) bate
    șterge (1 v) din [secventa v]
altfel
    Joc peste :: personalizat
sfarsit
```

\--- /task \---

\--- task \--- Testați-vă noul bloc jucând jocul și făcând clic pe butonul roșu într-un punct greșit din secvența de culoare. \--- / sarcina \---

Noul dvs. `Joc de peste`{: class = „block3myblocks“} bloc este un **funcție**, un pic script pe care le puteți utiliza oriunde doriți în codul dvs. adăugând `Joc de peste`{: class = „block3myblocks“} bloc în.

\--- sarcina \--- înlocui , de asemenea codul din `altceva`{: class = „block3control“} bloc conectat la `emisiunile`{: class = „block3events“} pentru celelalte culori cu noul `Joc de peste`{: class = "block3myblocks"} bloc. Iată ce ar trebui să arate codul pentru mesajul `albastru`{: class = "block3events"}

![balerină](images/ballerina.png)

```blocks3
atunci când primesc [v blue]
dacă <(punctul (1 v) din [secvență v]) =[1]> , apoi
    tambur joc (\ (2 \) Bass Drum v) pentru (0,25) bate
    șterge (1 v) din [secventa v]
altfel
    Joc peste :: personalizat
sfarsit
```

\--- /task \---

\--- task \--- Acum adăugați un sunet care se joacă când este apăsat un buton greșit. Trebuie doar să adăugați acest cod o singură dată în blocul `joc peste`{block = block3myblocks}} pe care l-ați făcut și nu patru ori separat!

![balerină](images/ballerina.png)

```blocks3
defini Joc de peste
de pornire a sunetului [Cough1 v]
spun [Joc de peste!] pentru (1) secunde
în cazul în care < (scor :: variabile) > (scor ridicat) > , apoi
    sunet redare (trumpet1 v)
    set [scor mare v] la (scor)
    cere [Scor mare! Care este numele dvs.?] Și așteptați
    setați [nume v] la (răspuns)
capăt
oprire [toate v]
```

\--- /task \---