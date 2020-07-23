## आवाज जोडा

\--- task \---

आपल्या प्रकल्पची काही वेळा चाचणी घ्या. आपणास असे लक्षात आले आहे की कधीकधी समान संख्या सलग दोनदा (किंवा अधिक) निवडली जाते ज्यामुळे अनुक्रम लक्षात ठेवणे कठीण होते?

\--- /task \---

प्रत्येक वेळी पात्र spriteच्या पोशाखात आपण ड्रम आवाज वाजवू शकता? आणि प्रत्येक रंगासाठी वेगळ्या ड्रम ध्वनीबद्दल काय?

\--- task \---

आपल्या प्रकल्पमध्ये संगीत विस्तार जोडा जेणेकरुन आपण `play drum`{:class="block3extensions"} ब्लॉक वापरू शकता.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

ड्रम वाजविणारा कोड ** very**आहे आणि कोडची समानता जी वर्णांची पोशाख बदलते.

\--- hints \---

\--- hint \---

आपल्याला फक्त दोन ब्लॉक्स जोडण्याची आवश्यकता आहे: एक `play drum for (0.25) beats`{:class="block3sound"} साठी ब्लॉक आणि `item (length of sequence) of sequence`{:class="block3variables"} ब्लॉक.

\--- /hint \---

\--- hint \---

आपल्याला आवश्यक असलेले ब्लॉक येथे आहेत:

![ballerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \---

तुमचा कोड कसा दिसला पाहिजे हे येथे आहे:

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