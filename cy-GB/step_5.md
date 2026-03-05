## Lefelau gwahanol

Hyd yn hyn, mae’r chwareuwr ond wedi gorfod cofio 5 lliw. Beth am wella’r gêm trwy ychwanegu sgôr, ac ychwanegu côd fel bod y chwareuwr yn ennill pwyntiau, y gêm yn symud i'r lefel nesaf a'r dilyniant lliwiau i'w gofio yn cynyddu.

--- task --- Creu newidyn newydd o'r enw `sgôr`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]] --- /task ---

Yn seiliedig ar y `sgôr`{:class="block3variables"}, bydd y gêm yn penderfynu ar hyd y dilyniant lliw. Cychwyna gyda sgôr (a hyd dilyniant) o `3`.

--- task --- Ychwanega floc ar ddechrau côd dy gymeriad `pan fo'r faner wedi ei chlicio`{:class="block3events"} i osod y `sgôr`{:class="block3variables"} i `3`. --- /task ---

Yn hytrach na chreu dilyniant o bum lliw bob amser, rwyt ti eisiau i'r `sgôr`{:class="block3variables"} i benderfynu hyd y dilyniant.

--- task --- Newida dolen y cymeriad `ail-adrodd`{:class="block3control"} (i greu y dilyniant lliw) i ail-adrodd y `sgôr`{:class="block3variables"}:

<p><img src="images/ballerina.png" alt="corlun" /></p>

```blocks3
repeat (sgôr)
end
```

--- /task ---

--- task --- Os yw'r chwaraewr yn ailadrodd y dilyniant cywir, fe ddylai ychwanegu `1` i'r `sgôr`{:class="block3variables"}, ac mae gwneud hynny yn cynyddu hyd y dilyniant nesaf. Ychwanega'r bloc canlynol i gôd y cymeriad **ar y rhan rwyt ti'n gwybod bod y dilyniant yn gywir**:

![corlun](images/ballerina.png)

```blocks3
change [sgôr v] by (1)
```

--- hints ---
 --- hint --- Ti'n gwybod bod y dilynant yn gywir ar y pwynt mae'r gêm yn `darlledu`{:class="block3events"} y neges 'ennill.
--- /hint ---
--- /hints ---

--- /task ---

--- task --- Yn olaf, ychwanega dolen `am byth`{:class="block3control"} o amgylch y côd sydd yn creu'r dilyniant, fel fod y gêm yn creu lliw newydd ar gyfer pob lefel. Dyma sut y gallai côd y cymeriad edrych:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
set [sgôr v] to [3]
forever 
  delete (all v) of [dilyniant v]
  repeat (sgôr) 
    add (pick random (1) to (4)) to [dilyniant v]
    switch costume to (item (length of [dilyniant v]) of [dilyniant v])
    wait (1) seconds
  end
  wait until <(length of [dilyniant v]) = [0]>
  broadcast (won v) and wait
  change [sgôr v] by (1)
end
```

--- /task ---

--- task --- Gofyn i dy ffrindiau brofi dy gêm. Cofia guddio rhestr `dilyniant`{:class="block3variables"} cyn iddynt ei chwarae! --- /task ---