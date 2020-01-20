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

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /hint \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
chwarae drwm ((1) Snare Drum v) am (0.25) curiad

(eitem (hyd [dilyniant v]) o [dilyniant v])
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

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

\--- /hint \---

\--- /hints \---

\--- /task \---