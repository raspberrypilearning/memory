## Dodaj zvok

\--- task \---

Nekajkrat preizkusi svoj projekt. Ali opaziš, da je včasih enaka številka izbrana dvakrat (ali večkrat) zaporedoma, kar povzroči, da si je zaporedje težje zapomniti?

\--- /task \---

Ali lahko narediš, da bo zvok bobna zaigral vsakič, ko bo lik zamenjal svoj videz? Kaj pa da ima boben različen zvok za vsako barvo?

\--- task \---

Projektu dodaj razširitev Glasba, da boš lahko uporabil blok `zaigraj na boben`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

Koda, ki igra na boben, je **zelo** podobna kodi, ki spreminja videz lika.

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /hint \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
zaigraj na boben (\1(1\) Mali boben v) za (0.25) udarcev

(element (dolžina [zaporedje v]) v [zaporedje v])
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

```blocks3
ko kliknemo na zastavico
izbriši vse v [zaporedje]
ponovi (5) krat
  dodaj (naključno število med (1) in (4)) k [seznam v]
  zaigraj na boben (element (dolžina [zaporedje v]) v [zaporedje v]) za (0.25) udarcev
  zamenjaj videz na (element (dolžina [zaporedje v] v [sekvenca v])
  počakaj (1) sekund
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---