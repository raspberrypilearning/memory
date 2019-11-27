## ශබ්ද එක් කිරීම

\--- task \---

ඔබේ ව්‍යාපෘතිය කිහිප වතාවක් පරීක්ෂා(test) කරන්න. සමහර විට එකම(same) අංකය(number එක) පේළියක(row) දෙවරක් (හෝ ඊට වැඩි) වාර ගනනක් තෝරාගෙන බව ඔබට පෙනෙනු ඇති අතර එමඟින් අනුක්‍රමය(sequence එක) කටපාඩම්(memorise) කිරීම අපහසු වේ.

\--- /task \---

sprite චරිතය ඇඳුම(costume එක) වෙනස් කරන සෑම අවස්ථාවකම, ඔබට ඩ්‍රම් ශබ්ද වාදනය කළ හැකිද? එක් එක් වර්ණය සඳහා වෙනස් ඩ්‍රම් ශබ්දයක් වැයේ නම් කෙතරම් අගනේද?

\--- task \---

ඔබේ ව්‍යාපෘතියට(project එකට) සංගීත(music) දිගුව(extension) එක් කරන්න, එවිට ඔබට `බෙර වාදනය(play drum)`{:class="block3extensions"} කට්ටිය(block එක) භාවිතා කළ හැකියි.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

බෙර වාදනය කරන කේතය(code එක) චරිතයේ(character එකේ) ඇඳුම(costume එක) වෙනස් කරන කේතයට(code එකට) **ඉතා(very)** සමානය.

\--- hints \--- \--- hint \--- ඔබට එකතු කළ යුත්තේ කට්ටි(blocks) දෙකක් පමණි: `(0.25) සඳහා බෙර වාදනය(play drum for 0.25)`{:class="block3sound"} කට්ටිය සහ ` අයිතම(item) [අනුක්‍රමයේ දිග(length of sequence)] අනුක්‍රමය(sequence)`{:class="block3variables"} කට්ටිය. \--- /hint \--- \--- hint \---

ඔබට අවශ්‍ය කට්ටි(blocks) මෙහි දැක්වේ:

![මුද්‍රා නාට්‍ය ශිල්පිනිය(ballerina)](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \--- ඔබේ නිමි(finished) කේතය(code එක) මෙහි දැක්වෙන ආකාරයේ එකක් වියයුතුයි:

![මුද්‍රා නාට්‍ය ශිල්පිනිය(ballerina)](images/ballerina.png)

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

\--- /hint \---

\--- /task \---