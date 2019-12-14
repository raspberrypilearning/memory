## Ustvari barvno zaporedje

Najprej ustvari lik, ki zna prikazati naključno zaporedje barv na zaslonu.

\--- task \--- Odprite nov Scratch projekt.

**S povezavo:** ustvari nov spletni Scratch projekt na [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Brez povezave:** ustvari nov projekt v namiznem Scratch urejevalniku.

Če želiš prenesti in namestiti Namizni Scratch, ga lahko najdeš na [rpf.io/scratchoff](https://rpf.io/scratchoff){: target = "_ blank"}.

\--- /task \---

\--- task \--- Izberi figuro lika in ozadje. Lahko uporabiš balerino, vendar ni nujno, da je tvoj lik sploh oseba, vse kar je pomembno je to, da zna prikazati različne barve.

![posnetek zaslona](images/colour-sprite.png) \--- /task \---

+ Tvoja igra bi morala uporabljati različne številke za prikaz barv:
    
    + 1 = rdeča
    + 2 = modra
    + 3 = zelena
    + 4 = rumena

\--- task \--- Svojemu liku ustvari štiri videze različnih barv - po en videz za vsako od štirih barv, ki so prikazane zgoraj. Bodi pozoren, da bodo videzi v enakem zaporedju, kot na zgornjem seznamu barv.

![posnetek zaslona](images/colour-costume.png) \--- /task \---

Če želiš, lahko uporabiš orodje **pobarvaj lik**, da zapolniš posamezne dele videza z drugačno barvo.

![barva-a-oblika](images/color-a-shape.png)

Nato ustvari seznam, v katerega se bo shranilo naključno zaporedje barv, ki si jih mora igralec zapomniti.

\--- task \--- Ustvari seznam imenovan`zaporedje`{:class="block3variables"}. Ta seznam potrebuje le figura lika, zato lahko izbereš **Samo za to figuro**, ko ustvarjaš seznam.

[[[generic-scratch3-make-list]]]

\--- /task \---

Zdaj bi moral videti številne nove bloke kode, za rabo s seznami. Prazen seznam bi moral biti viden v zgornjem levem kotu odra.

![posnetek zaslona](images/colour-list-blocks-annotated.png)

Vsaka barva ima drugačno številko, zato lahko izbereš naključno barvo s pomočjo naključno izbrane številke, ki jo dodaš seznamu.

\--- task \--- Figuri lika dodaj to kodo, da izbere naključno številko in jo doda v `zaporedje`{:class="block3variables"}:

![balerina](images/ballerina.png)

```blocks3
ko kliknemo na zastavico
dodaj (naključno število med (1) in (4)) k [zaporedje]
```

\--- /task \---

\--- task \--- Preizkusi svojo kodo. Preveri ali je ob vsakem kliku na zastavico na seznam dodana števlka med 1 in 4. \--- /task \---

\--- task \--- Ali lahko svojemu programu dodaš kodo, ki bo ustvarila pet naključnih števil naenkrat?

\--- hints \--- \--- hint \--- Dodaj `izbriši vse v zaporedju`{:class="block3variables"}, da najprej izbrišeš vse predmete v seznamu in nato dodaj blok `ponovi`{:class="block3control"}, ki doda pet naključnih števil v szenam. \--- /hint \--- \--- hint \---

Tvoja koda mora izgledati tako:

![balerina](images/ballerina.png)

```blocks3
ko kliknemo na zastavico
izbriši (vse v) v [zaporedje v]
ponovi (5) krat
  dodaj (naključno število med (1) in (4)) k [zaporedje v]
konec
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Vsakič, ko je število dodano k seznamu, naj lik zamenja svoj videz, tako da barva videza ustreza številki. Dodaj te bloke v svojo kodo, takoj pod delom, kjer se naključno število doda k `zaporedju`{:class="block3variables"}:

![balerina](images/ballerina.png)

```blocks3
zamenjaj videz na (element(dolžina [zaporedje v]) v [zaporedje v])
počakaj (1) sekund
```

\--- /task \---