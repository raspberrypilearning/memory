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
repeat (score :: variables)
end
```

\--- /task \---

\--- task \--- Če igralec pravilno ponovi zaporedje, dodaj `1` k `točkam`{:class="block3variables"}, kar podaljša dolžino naslednjega zaporedja. Add the following block to the character's code **at the point you know the sequence is correct**:

![figura](images/ballerina.png)

```blocks3
spremeni [točke v] za (1)
```

\--- hints \--- \--- hint \--- Da je zaporedje pravilno, veš tedaj, ko igra `objavi`{:class="block3events"} sporočilo 'zmaga'. \--- /hint \--- \--- /hints \---

\--- /task \---

Na koncu dodaj okoli kode, ki ustvarja zaporedje še zanko `ponavljaj`{:class="block3control"}, da bo za vsako naslednjo stopnjo ustvarjeno novo barvno zaporedje. Tvoja koda lika bi lahko bila videti takole:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
set [score v] to [3]
forever
    delete (all v) of [sequence v]
    repeat (score)
        add (pick random (1) to (4)) to [sequence v]
        switch costume to (item (length of [sequence v]) of [sequence v]
        wait (1) seconds
    end
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
    change [score v] by (1)
end
```

\--- /task \---

\--- task \--- Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it! \--- /task \---