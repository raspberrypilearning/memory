## Več stopenj

Zaenkrat si mora igralec zapomniti zaporedje petih barv. Izboljšaj svojo igro, tako da dodaš točke in dodaj kode, da bo igralec, ko dobi dovolj točk, prešel na naslednjo stopnjo, na kateri si bo moral zapomniti daljše zaporedje.

\--- task \--- Ustvari novo spremenljivko z imenom `točke`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

Glede na točke `score`{:class="block3variables"}, se bo igra odločila, kako dolgo bo zaporedje. Začni s številom točk (in dolžino zaporedja) `3`.

\--- task \--- Na začetek bloka `ko kliknemo na zastavico`v figuri tvojega lika {:class="block3events"} dodaj kodo, ki nastavi `točke`{:class="block3variables"} na `3`. \--- /task \---

Namesto tega, da vedno ustvariš zaporedje petih barv, boš sedaj uporabil-a `točke`{:class="block3variables"} za določitev dolžine zaporedja.

\--- task \--- V figuri spremeni zanko `ponovi`{:class="block3control"} (ki ustvarja barvno zaporedje), da se ponovi `točke-`{:class="block3variables"}krat:

![figura](images/ballerina.png)

```blocks3
ponovi (točke :: Spremenljivka) krat
konec
```

\--- /task \---

\--- task \--- Če igralec pravilno ponovi zaporedje, dodaj `1` k `točkam`{:class="block3variables"}, kar podaljša dolžino naslednjega zaporedja. Kodi lika dodaj naslednji blok na **tisto mesto, kjer že veš, da je zaporedje pravilno**:

![figura](images/ballerina.png)

```blocks3
spremeni [točke v] za (1)
```

\--- hints \--- \--- hint \--- Da je zaporedje pravilno, veš tedaj, ko igra `objavi`{:class="block3events"} sporočilo 'zmaga'. \--- /hint \--- \--- /hints \---

\--- /task \---

Na koncu dodaj okoli kode, ki ustvarja zaporedje še zanko `ponavljaj`{:class="block3control"}, da bo za vsako naslednjo stopnjo ustvarjeno novo barvno zaporedje. Tvoja koda lika bi lahko bila videti takole:

![balerina](images/ballerina.png)

```blocks3
ko kliknemo na zastavico
nastavi [točke v] na (3)
ponavljaj
    izbriši (vse v) v [zaporedje v]
    ponovi (točke) krat
        dodaj (naključno število med (1) in (4)) k [zaporedje v]
        zamenjaj videz na (element (dolžina [zaporedje v]) v [zaporedje v]
        počakaj (1) sekund
    konec
    počakaj dokler ni < (dolžina [zaporedje v]) = (0)>
    objavi (zmaga v) in čakaj
    spremeni [točke v] za (1)
konec
```

\--- /task \---

\--- task \--- Prijatelji naj igro preizkusijo. Ne pozabi skriti seznama `zaporedje`{:class="block3variables"}, preden jo začenjo igrati! \--- /task \---