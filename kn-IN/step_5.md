## ಬಹು ಮಟ್ಟಗಳು

ಇಲ್ಲಿಯವರೆಗೆ, ಆಟಗಾರನು ಐದು ಬಣ್ಣಗಳ ಅನುಕ್ರಮವನ್ನು ಮಾತ್ರ ನೆನಪಿಟ್ಟು ಕೊಂಡಿದ್ದಾರೆ. ಸ್ಕೋರ್ ಸೇರಿಸುವ ಮೂಲಕ ಮತ್ತು ಕೋಡ್ ಸೇರಿಸುವ ಮೂಲಕ ನಿಮ್ಮ ಆಟವನ್ನು ಸುಧಾರಿಸಿ ಇದರಿಂದ ಆಟಗಾರನು ಅಂಕಗಳನ್ನು ಗಳಿಸಿದಂತೆ, ಆಟವು ಮುಂದಿನ ಹಂತಕ್ಕೆ ಚಲಿಸುತ್ತದೆ ಮತ್ತು ನೆನಪಿಡುವ ಬಣ್ಣ ಅನುಕ್ರಮವು ಉದ್ದವಾಗುತ್ತದೆ.

\--- task \---

ಹೊಸ ವೇರಿಯೇಬಲ್ ಅನ್ನು ರಚಿಸಿ `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

ಆಧರಿಸಿ `score`{:class="block3variables"}, ಬಣ್ಣ ಅನುಕ್ರಮದ ಉದ್ದವನ್ನು ಆಟವು ನಿರ್ಧರಿಸುತ್ತದೆ.ಸ್ಕೋರ್‌ನೊಂದಿಗೆ ಪ್ರಾರಂಭಿಸಿ (ಮತ್ತು ಅನುಕ್ರಮ ಉದ್ದ) `3`.

\--- task \---

ಸೇರಿಸಿ block ನಿಮ್ಮ ಪಾತ್ರದ ಪ್ರಾರಂಭದಲ್ಲಿ `when flag clicked`{:class="block3events"} ಕೋಡ್ ಹೊಂದಿಸಲು `score`{:class="block3variables"} ಗೆ `3`.

\--- /task \---

ಯಾವಾಗಲೂ ಐದು ಬಣ್ಣಗಳ ಅನುಕ್ರಮವನ್ನು ರಚಿಸುವ ಬದಲು, ನೀವು ಈಗ ಬಯಸುತ್ತೀರಿ `score`{:class="block3variables"} ಅನುಕ್ರಮ ಉದ್ದವನ್ನು ನಿರ್ಧರಿಸಲು.

\--- task \---

ಕ್ಯಾರೆಕ್ಟರ್ ವನ್ನು ಬದಲಾಯಿಸಿ `repeat`{:class="block3control"} ಲೂಪ್ (ಬಣ್ಣ ಅನುಕ್ರಮವನ್ನು ರಚಿಸಲು) ಗೆ ಪುನರಾವರ್ತಿಸಿ `score`{:class="block3variables"}ಬಾರಿ:

![sprite](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

\--- /task \---

\--- task \---

ಆಟಗಾರನು ಸರಿಯಾದ ಅನುಕ್ರಮವನ್ನು ಪುನರಾವರ್ತಿಸಿದರೆ, ನೀವು `1` ಅನ್ನು ಸೇರಿಸಬೇಕು `score`{:class="block3variables"}ಗೆ, ಮತ್ತು ಹಾಗೆ ಮಾಡುವುದರಿಂದ ಮುಂದಿನ ಅನುಕ್ರಮದ ಉದ್ದ ಹೆಚ್ಚಾಗುತ್ತದೆ. ಈ ಕೆಳಗಿನ ಬ್ಲಾಕ್ ಅನ್ನು ಕ್ಯಾರೆಕ್ಟರ್ ಗಳ ಕೋಡ್‌ಗೆ ಸೇರಿಸಿ **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
change [score v] by (1)
```

\--- hints \---

\--- hint \---

ಆಟದ ಸಮಯದಲ್ಲಿ ಅನುಕ್ರಮವು ಸರಿಯಾಗಿದೆ ಎಂದು ನಿಮಗೆ ತಿಳಿದಿದೆ `broadcasts`{:class="block3events"} 'ಗೆಲುವು' ಸಂದೇಶವನ್ನು ಪ್ರಸಾರಮಾಡಿದ್ದಾಗ.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

ಅಂತಿಮವಾಗಿ, ಒಂದು ಸೇರಿಸಿ `forever`{:class="block3control"} ಅನುಕ್ರಮವನ್ನು ಉತ್ಪಾದಿಸುವ ಕೋಡ್‌ನ ಸುತ್ತಲೂ ಲೂಪ್ ಮಾಡಿ, ಇದರಿಂದಾಗಿ ಆಟವು ಪ್ರತಿ ಹಂತಕ್ಕೂ ಹೊಸ ಬಣ್ಣ ಅನುಕ್ರಮವನ್ನು ರಚಿಸುತ್ತದೆ. ನಿಮ್ಮ ಕ್ಯಾರೆಕ್ಟರ್'ಸ್ ಕೋಡ್ ಹೀಗಿರಬಹುದು:

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

\--- task \---

ನಿಮ್ಮ ಆಟವನ್ನು ಪರೀಕ್ಷಿಸಲು ನಿಮ್ಮ ಸ್ನೇಹಿತರನ್ನು ಪಡೆಯಿರಿ. ಮರೆಮಾಡಲು ಮರೆಯದಿರಿ `sequence`{:class="block3variables"} ಪಟ್ಟಿ ಅವರು ಅದನ್ನು ಆಡುವ ಮೊದಲು!

\--- /task \---