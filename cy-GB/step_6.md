## Sgôr Uchel

Nawr fe alli di arbed y sgôr uchel, fel dy fod di’n gallu chwarae yn erbyn dy ffrindiau.

--- task ---Ychwanega 2 newidyn newydd i dy brosiect, o’r enw `sgôr uchel`{:class="block3variables"} ac `enw`{:class="block3variables"}. --- /task ---

Pan fo'r gêm yn gorffen (trwy wasgu’r botwm anghywir), fe ddylai'r gêm wirio os yw sgôr y chwareuwr yn uwch na’r sgôr uchel presennol. Os yw e, bydd angen i ti arbed y sôr fel y sgôr uchel, a’i storio dan enw’r chwareuwr.

--- task --- Ychwanega gôd i dy gymeriad i gadw `sgôr uchel`{:class="block3variables"}. Gofyna enw'r chwareuwr, a'i arbed yn y newidyn `enw`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

--- hints ---
 --- hint --- Fe ddylai dy gôd newydd ddilyn y patrwm canlynol:

Ar ôl y neges `Gêm drosodd`{:class="block3looks"} `Os`{:class="block3control"} yw'r `sgôr`{:class="block3variables"} yn `uwch na`{:class="block3operators"} y `sgôr uchel`{:class="block3variables"} `Gosod`{:class="block3variables"} y `sgôr uchel`{:class="block3variables"} i `sgôr`{:class="block3variables"} `Gofyn`{:class="block3sensing"} am enw'r chwareuwr`Gosod`{:class="block3variables"} yr `enw`{:class="block3variables"} i'r `ateb`{:class="block3sensing"}
--- /hint ---
 --- hint ---

Mae angen y blociau canlynol:

![ballerina](images/ballerina.png)

```blocks3
if <> then
end

(sgôr)

(sgôr)

<[ ] > [ ]>

(answer)

(sgôr uchel)

ask [Beth yw dy enw?] and wait

set [sgôr uchel v] to [ ]

set [enw v] to [ ]
```

--- /hint --- --- hint --- Dyma sut y dylai'r côd edrych ar gyfer pan mae'r botwm coch wedi ei wasgu:

![ballerina](images/ballerina.png)

```blocks3
when I receive [coch v]
if <(item (1 v) of [dilyniant v]) = [1]> then 
  play drum (item (1 v) of [dilyniant v]) for (0.25) beats
  delete (1 v) of [dilyniant v]
else 
  say [Gêm drosodd!] for (1) seconds
  if <(sgôr :: variables) > (sgôr uchel)> then 
    set [sgôr uchel v] to (sgôr :: variables)
    ask [Sgôr uchel! Beth yw dy enw?] and wait
    set [enw v] to (answer)
  end
  stop [y cyfan v]
end
```

--- /hint ------ /hints --- --- /task ---

Mae angen ychwanegu'r côd newydd yma i'r cymeriad ar gyfer y tri lliw arall hefyd!

Alli di weld fod y côd ar gyfer 'Gêm drosodd' ar gyfer y pedwar lliw yn union yr un peth?

![ballerina](images/ballerina.png)

```blocks3
say [Gêm drosodd!] for (1) seconds
if <(sgôr :: variables) > (sgôr uchel)> then 
  set [sgôr uchel v] to (sgôr :: variables)
  ask [Sgôr uchel! Beth yw dy enw?] and wait
  set [enw v] to (answer)
end
stop [y cyfan v]
```

Os wyt ti byth eisiau newid rhan o’r côd yma, fel ychwanegu sain neu newid y neges ‘Gêm drosodd!’, bydd angen i ti ei newid 4 gwaith! Gall hwnna fod yn boen, ac yn wastraff amser.

Yn hytrach, mae modd i ti ddiffinio dy flociau dy hunan, a’u ail-defnyddio ar gyfer dy brosiect.

--- task --- Clicia `Mwy o flociau`{:class="block3myblocks"}, yna **Creu bloc**. Galwa'r bloc yma yn `Gêm drosodd`{:class="block3myblocks"}.

--- /task ---

--- task --- Ychwanegu'r côd o'r bloc `fel arall`{:class="block3control"} sydd wedi ei gysylltu â'r darllediad `coch`{:class="block3events"} i'r bloc `Gêm drosodd`{:class="block3myblocks"} fel ei fod yn edrych fel hyn:

![ballerina](images/ballerina.png)

```blocks3
define Gêm drosodd
say [Gêm drosodd!] for (1) seconds
if <(sgôr :: variables) > (sgôr uchel)> then 
  set [sgôr uchel v] to (sgôr :: variables)
  ask [Sgôr uchel! Beth yw dy enw?] and wait
  set [enw v] to (answer)
end
stop [y cyfan v]
```

--- /task ---

--- task --- Nawr tynna'r côd sydd yn y bloc `fel arall`{:class="block3control"} sydd wedi ei gysylltu â'r darllediad `coch`{:class="block3events"} a'i ychwanegu i'r bloc `Gêm drosodd`{:class="block3myblocks"} yn lle:

![ballerina](images/ballerina.png)

```blocks3
when I receive [coch v]
if <(item (1 v) of [dilyniant v]) = [1]> then 
  play drum (\(1\) Snare Drum v) for (0.25) beats
  delete (1 v) of [dilyniant v]
else 
  Gêm drosodd :: custom
end
```

--- /task ---

--- task --- Profa dy floc newydd trwy ei chwarae a chlicio'r botwm coch ar y pwynt anghywir yn y dilyniant. --- /task ---

Mae dy floc `Gêm drosodd`{:class="block3myblocks"} yn **weithred**, sgript y mae modd ei ddefnyddio unrhywle yn dy gôd trwy ychwanegu bloc `Gêm drosodd`{:class="block3myblocks"}.

--- task --- Hefyd bydd angen i ti ailosod y bloc `fel arall`{:class="block3control"} sydd wedi ei gysylltu â'r `darllediad`{:class="block3events"} ar gyfer y lliwiau eraill yn dy floc `Gêm drosodd`{:class="block3myblocks"}. Dyma sut ddylai'r côd ar gyfer y neges `glas`{:class="block3events"} edrych fel

![ballerina](images/ballerina.png)

```blocks3
when I receive [glas v]
if <(item (1 v) of [dilyniant v]) = [1]> then 
  play drum (\(2\) Bass Drum v) for (0.25) beats
  delete (1 v) of [dilyniant v]
else 
  Gêm drosodd :: custom
end
```

--- /task ---

--- task --- Nawr ychwanega sain sy'n chwarae pan fydd y botwm anghywir yn cael ei wasgu. Ti dim ond angen ychwanegu'r côd yma unwaith yn y bloc `Gêm drosodd`{:class="block3myblocks"} rwyt ti wedi ei greu, dim pedwar gwaith!

![ballerina](images/ballerina.png)

```blocks3
define Gêm drosodd
start sound [Cough1 v]
say [Gêm drosodd!] for (1) seconds
if <(sgôr :: variables) > (sgôr uchel)> then 
  start sound (trumpet1 v)
  set [sgôr uchel v] to (sgôr)
  ask [Sgôr uchel! Beth yw dy enw?] and wait
  set [enw v] to (answer)
end
stop [y cyfan v]
```

--- /task ---