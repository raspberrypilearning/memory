## Ychwanegu sain

--- task ---

Profa dy brosiect. Wyt ti'n sylwi weithiau fod yr un rhif yn cael ei ddewis ddwywaith (neu fwy) ar ôl ei gilydd, sy’n gwneud y dilyniant yn anoddach i gofio?

--- /task ---

Wyt ti’n gallu gwneud sŵn drwm i chwarae bob tro mae’n cymeriad yn newid gwisg? Beth am sain drwm gwahanol ar gyfer pob lliw?

--- task ---

Ychwanega estyniad Sain i dy brosiect fel dy fod yn gallu defnyddio bloc `chwarae drwm`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

Mae'r côd sy'n chwarae'r drwm yn debyg **iawn** i'r côd sy'n newid gwisg y cymeriad.

--- hints ---
 --- hint --- Mae dim ond angen i ti ychwanegu dau floc: bloc `chwarae drwm am (0.25) beats`{:class="block3sound"} a bloc `eitem dilyniant (hyd y dilyniant)`{:class="block3variables"}.
--- /hint ---
 --- hint ---

Dyma'r blociau côd rwyt ti eu hangen:

![ballerina](images/ballerina.png)

```blocks3
chwarae drwm ((1) Snare Drum v) am (0.25) curiad

(eitem (hyd [dilyniant v]) o [dilyniant v])
```

--- /hint ---

--- hint --- Dyma sut ddylai dy gôd gorffenedig edrych:

![ballerina](images/ballerina.png)

```blocks3
pan fo'r flag werdd yn cael ei glicio
dileu (all v) o [dilyniant v]
ailadrodd (5) 
  ychwanegu (dewis ar hap (1) i (4)) i [dilyniant v]
  chwarae drwm (eitem (hyd [dilyniant v]) o [dilyniant v]) am (0.25) curiad
  newid gwisg i (eitem (hyd [dilyniant v]) o [dilyniant v])
  aros (1) eiliad
end
```

--- /hint ---

--- /hints ---

--- /task ---