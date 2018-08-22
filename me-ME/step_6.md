## Više nivoa

Do sada, igrač treba da zapamti samo niz od pet boja. Poboljšajmo igru tako što ćemo dodati rezultat, a zatim dodati kôd da se, sa povećanjem igračevog rezultata, povećava dužina niza koji treba da zapamti.

+ Kreiraj novu promjenljivu (variable) i nazovi je `rezultat`{:class="blockdata"}.

[[[generic-scratch-add-variable]]]

`Rezultat`{:class="blockdata"} će se koristiti za određivanje dužine niza koji igrač treba da zapamti. Počnimo sa rezultatom (i dužinom niza) od `3`.

+ Na početku kôda svog karaktera `when flag clicked`{:class="blockevents"} (kada je kliknuto na zastavicu) dodaj blok da postaviš `rezultat`{:class="blockdata"} na `3`.

Umjesto da se uvijek kreira niz od pet boja, sada želiš da `rezultat`{:class="blockdata"} određuje dužinu niza.

+ Promijeni petlju karaktera `repeat`{:class="blockcontrol"} (ponavljaj) koja kreira niz, tako da ponavlja `rezultat`{:class="blockdata"}:

```blocks
    repeat (rezultat)
    end
```

+ Ako je niz ispravno pogođen, rezultatu treba da dodaš `1`, kako bi se dužina sljedećeg niza povećala. Dodaj ovaj blok kôdu karaktera **kada saznaš da je niz ispravno pogođen**.

```blocks
    change [rezultat v] by (1)
```

--- hints --- --- hint --- Znaš da je niz ispravno pogođen kada pošalješ poruku `pobjeda`. --- /hint --- --- /hints ---

+ Na kraju, treba da dodaš petlju `forever`{:class="blockcontrol"} (ponavljaj) oko kôda koji stvara niz, kako bi se za svaki nivo kreirao novi niz. Ovako bi trebalo da izgleda kôd tvog karaktera:
    
    ```blocks
        when flag clicked
        set [rezultat v] to [3]
        forever
            delete (all v) of [niz v]
            repeat (rezultat)
                add (pick random (1) to (4)) to [niz v]
                switch costume to (item (last v) of [niz v]
                wait (1) secs
            end
            wait until < (length of [niz v]) = [0]>
            broadcast [pobjeda v] and wait
            change [rezultat v] by (1)
        end
    ```

+ Zamoli prijatelje da isprobaju tvoju igru. Ne zaboravi da sakriješ listu `niz`{:class="blockdata"} prije nego što započnu igru!