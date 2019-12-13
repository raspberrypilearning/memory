## Dodaj zvok

\--- task \---

Nekajkrat preizkusi svoj projekt. Ali opaziš, da je včasih enaka številka izbrana dvakrat (ali večkrat) zaporedoma, kar povzroči, da si je zaporedje težje zapomniti?

\--- /task \---

Ali lahko narediš, da bo zvok bobna zaigral vsakič, ko bo lik zamenjal svoj videz? Kako pa je z drugačnim zvokom bobna za vsako barvo?

\--- task \---

Projektu dodaj razširitev Glasba, da boš lahko uporabil blok `zaigraj na boben`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

Koda, ki igra na boben, je **zelo** podobna kodi, ki spreminja videz lika.

\--- hints \--- \--- hint \--- Dodati moraš le dva bloka: blok `zaigraj na boben za (0.25) udarcev`{:class="block3sound"} in blok `element (dolžina zaporedja) v zaporedju`{:class="block3variables"}. \--- /hint \--- \--- hint \---

To so potrebni bloki:

![balerina](images/ballerina.png)

```blocks3
zaigraj na boben (\1(1\) Mali boben v) za (0.25) udarcev

(element (dolžina [zaporedje v]) v [zaporedje v])
```

\--- /hint \---

\--- hint \--- Tako bi morala izgledati tvoja dokončana koda:

![balerina](images/ballerina.png)

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