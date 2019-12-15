## Izziv: izboljšaj igro

### Ustvari več blokov

Vidiš še kakšen drug del kode, ki je enak za vse štiri gumbe?

```blocks3
ko prejmem [rdeča v]
če <(element (1 v) v [zaporedje v])=(1)> potem
  zaigraj na boben (\(1\) Mali boben v) za (0.25) utripov
  zbriši (1 v) v [zaporedje v]
sicer
   Konec igre :: custom
konec

ko prejmem [modra v]
če <(element (1 v) v [zaporedje v])=(2)> potem
  zaigraj na boben (\(2\) Mali boben v) za (0.25) utripov
  zbriši (1 v) v [zaporedje v]
sicer
   Konec igre :: custom
konec
```

Ali lahko ustvariš še en lastni blok, ki ga lahko uporabijo vsi gumbi?

### Drug videz

Si opazil, da se tvoja igra začne tako, da figura prikazuje eno od štirih barv in da lik vedno prikazuje zadnjo barvo v zaporedju, medtem ko igralec ponavlja barvno zaporedje?

Ali lahko dodaš svojemu liku še en bel videz in dodaš kodo, ki ta videz prikaže na začetku igre in medtem ko igralec ponavlja zaporedje?

![posnetek zaslona](images/colour-white.png)

### Težavnostna stopnja

Ali lahko omogočiš igralcu izbiro med 'enostavnim načinom' (v katerem se uporabljata le rdeče in modra barva) in 'navadnim načinom' (ki uporablja vse štiri barve)?

Če želiš, lahko dodaš tudi 'težak' način, ki doda še peti boben!