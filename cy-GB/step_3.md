## Ychwanegu sain

\--- task \---

Profa dy brosiect. Wyt ti'n sylwi weithiau fod yr un rhif yn cael ei ddewis ddwywaith (neu fwy) ar ôl ei gilydd, sy’n gwneud y dilyniant yn anoddach i gofio?

\--- /task \---

Wyt ti’n gallu gwneud sŵn drwm i chwarae bob tro mae’n cymeriad yn newid gwisg? Beth am sain drwm gwahanol ar gyfer pob lliw?

\--- task \---

Ychwanega estyniad Sain i dy brosiect fel dy fod yn gallu defnyddio bloc `chwarae drwm`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

Mae'r côd sy'n chwarae'r drwm yn debyg **iawn** i'r côd sy'n newid gwisg y cymeriad.

\--- hints \--- \--- hint \--- Mae dim ond angen i ti ychwanegu dau floc: bloc `chwarae drwm am (0.25) beats`{:class="block3sound"} a bloc `eitem dilyniant (hyd y dilyniant)`{:class="block3variables"}. \--- /hint \--- \--- hint \---

Dyma'r blociau côd rwyt ti eu hangen:

![ballerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \--- Dyma sut ddylai dy gôd gorffenedig edrych:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
    play drum (item (length of [sequence v]) of [sequence v]) for (0.25) beats
    switch costume to (item (length of [sequence v]) of [sequence v])
    wait (1) seconds
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---