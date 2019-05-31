## Creu dilyniant o liwiau

Yn gyntaf, fe wnawn ni greu cymeriad sydd yn gallu newid ei gwisg yn ôl dilyniant o liwiau ar hap.

\--- task \--- Agor prosiect Scratch newydd.

**Arlein:** agora brosiect Scratch newydd yma [rpf.io/scratch-new](https://rpf.io/scratchon)l.

**All-lein** agora brosiect newydd yn y golygydd all-lein.

Os oes angen i ti lawrlwytho a gosod golygydd Scratch all-lein, mae modd dod o hyd iddo yma [rpf.io/scratchoff](https://rpf.io/scratchoff).

\--- /task \---

\--- task \--- Dewisa gymeriad a chefndir. Does dim rhaid i dy gymeriad fod yn berson, ond mae’n rhaid iddo allu dangos lliwiau gwahanol.

![sgrinlun](images/colour-sprite.png) \--- /task \---

+ Dylai dy gêm ddefnyddio rhif gwahanol i gynrychioli pob lliw:
    
    + 1 = coch
    + 2 = glas
    + 3 = gwyrdd
    + 4 = melyn

\--- task \---Rho 4 wisg lliw gwahanol i dy gymeriad, un ar gyfer y 4 lliw uchod. Gwna’n siwr bod dy wisgoedd yn y drefn gywir, fel y rhestr uchod.

![sgrinlun](images/colour-costume.png) \--- /task \---

Os hoffet ti, alli di ddefnydio'r teclyn **lliwio siâp** i lenwi darnau o'r wisg mewn lliw gwahanol.

![lliw-a-siâp](images/color-a-shape.png)

Nesaf, ychwanega restr ar gyfer storio dilyniant ar hap o liwiau mae'n rhaid i'r chwareuwr eu cofio.

\--- task \--- Creu rhestr o'r enw `dilyniant`{:class="block3variables"}. Gan mai dim ond dy gymeriad sydd angen gweld y rhestr, fe alli di ddewis **Ar gyfer y ciplun yma yn unig’**.

[[[generic-scratch3-make-list]]]

\--- /task \---

Fe ddyle ti nawr weld dy restr gwag ar ochr top-chwith y llwyfan, yn ogystal â llawer o flociau newydd ar gyfer defnyddio’r rhestr.

![sgrinlun](images/colour-list-blocks-annotated.png)

Mae gan bob lliw rif gwahanol, fel dy fod yn gallu dewis lliw ar hap gan ddewis rhif a'i ychwanegu i'r rhestr.

\--- task \--- Ychwanega’r côd yma i dy gymeriad i ddewis ac ychwanegu rhif ar hap i'r `dilyniant`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
pan fo'r flag werdd yn cael ei glicio
ychwanegu (dewis ar hap (1) i (4)) i [dilyniant v]
```

\--- /task \---

\--- task \--- Profa dy gôd. Gwna'n siwr, bob tro rwyt ti'n clicio'r faner, fod rhif ar hap rhwng 1 a 4 yn cael ei ychwanegu i'r rhestr. \--- /task \---

\--- task \--- Alli di ychwanegu côd i dy raglen i greu pump o rifau ar hap ar unwaith?

\--- hints \--- \--- hint \--- Ychwanega `dileu pob dilyniant`{:class="block3variables"} i ddileu pob eitem ar y rhestr, yna ychwanegu bloc `ail-adrodd`{:class="block3control"} sy'n ychwanegu pump rhif ar hap i dy restr. \--- /hint \--- \--- hint \---

Dyma sut dylai dy gôd edrych:

![ballerina](images/ballerina.png)

```blocks3
pan fo'r flag werdd yn cael ei glicio
dileu (all v) o [dilyniant v]
ailadrodd (5) 
  ychwanegu (dewis ar hap (1) i (4)) i [dilyniant v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Bob tro mae rhif yn cael ei ychwanegu i'r rhestr, fe ddylai'r cymeriad newid ei wisg fel bod lliw y wisg yn cyfateb i'r rhif. Rho'r blociau yma i'r côd yn syth o dan lle mae'r rhif ar hap yn cael ei ychwanegu i'r `dilyniant`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
newid gwisg i (eitem (hyd [dilyniant v]) o [dilyniant v])
aros (1) eiliad
```

\--- /task \---