## ಧ್ವನಿಯನ್ನು ಸೇರಿಸಿ

--- task ---

ನಿಮ್ಮ ಯೋಜನೆಯನ್ನು ಕೆಲವು ಬಾರಿ ಪರೀಕ್ಷಿಸಿ. ಕೆಲವೊಮ್ಮೆ ಒಂದೇ ಸಂಖ್ಯೆಯನ್ನು ಸತತವಾಗಿ ಎರಡು ಬಾರಿ (ಅಥವಾ ಹೆಚ್ಚಿನದನ್ನು) ಆಯ್ಕೆಮಾಡುವುದನ್ನು ನೀವು ಗಮನಿಸುತ್ತೀರಾ, ಇದು ಅನುಕ್ರಮವನ್ನು ನೆನಪಿಟ್ಟುಕೊಳ್ಳಲು ಕಷ್ಟವಾಗಿಸುತ್ತದೆ?

--- /task ---

ಪ್ರತಿ ಬಾರಿ ಕ್ಯಾರೆಕ್ಟರ್ sprite ವೇಷಭೂಷಣ ಬದಲಾಯಿಸಿದಾಗ ನೀವು ಡ್ರಮ್ ಸೌಂಡ್ ಪ್ಲೇ ಮಾಡಬಹುದೇ? ಮತ್ತು ಪ್ರತಿ ಬಣ್ಣಕ್ಕೂ ವಿಭಿನ್ನ ಡ್ರಮ್ ಧ್ವನಿ ಹೇಗೆ?

--- task ---

ನಿಮ್ಮ ಯೋಜನೆಗೆ ಸಂಗೀತ ವಿಸ್ತರಣೆಯನ್ನು ಸೇರಿಸಿ ಇದರಿಂದ ನೀವು `play drum`{:class="block3extensions"} ಬ್ಲಾಕ್ ಅನ್ನು ಬಳಸಬಹುದು.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

ಡ್ರಮ್ ನುಡಿಸುವ ಕೋಡ್ **very** ಕ್ಯಾರೆಕ್ಟರ್ ಇನ ವೇಷಭೂಷಣ ಬದಲಾಯಿಸುವ ಕೋಡ್‌ಗೆ ಹೋಲುತ್ತದೆ.

--- hints ---


--- hint ---

ನೀವು ಎರಡು ಬ್ಲಾಕ್‌ಗಳನ್ನು ಸೇರಿಸಬೇಕು ಅದು: `play drum for (0.25) beats`{:class="block3sound"}ಬ್ಲಾಕ್‌ ಮತ್ತು `item (length of sequence) of sequence`{:class="block3variables"} ಬ್ಲಾಕ್‌.

--- /hint ---

--- hint ---

ನಿಮಗೆ ಅಗತ್ಯವಿರುವ ಬ್ಲಾಕ್ ಗಳು ಇಲ್ಲಿವೆ:

![ನರ್ತಕಿಯಾಗಿ](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

--- /hint ---

--- hint ---

ನಿಮ್ಮ ಸಿದ್ಧಪಡಿಸಿದ ಕೋಡ್ ಹೇಗೆ ಇರಬೇಕು ಎಂಬುದು ಇಲ್ಲಿದೆ:

![ನರ್ತಕಿಯಾಗಿ](images/ballerina.png)

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

--- /hint ---

--- /hints ---

--- /task ---