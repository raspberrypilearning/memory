## ಸವಾಲು: ನಿಮ್ಮ ಆಟವನ್ನು ಸುಧಾರಿಸಿ

### ಹೆಚ್ಚಿನ ಬ್ಲಾಕ್ಗಳು ಮಾಡಿ

ಎಲ್ಲಾ ನಾಲ್ಕು ಬಟನ್ ಒಂದೇ ರೀತಿಯ ಬೇರೆ ಯಾವುದೇ ಕೋಡ್ ಅನ್ನು ನೀವು ನೋಡುತ್ತೀರಾ?

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game Over :: custom
end

when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

ಎಲ್ಲಾ ಗುಂಡಿಗಳು ಬಳಸಬಹುದಾದ ಮತ್ತೊಂದು ಕಸ್ಟಮ್ ಬ್ಲಾಕ್ ಅನ್ನು ನೀವು ಮಾಡಬಹುದೇ?

### ಮತ್ತೊಂದು ವೇಷಭೂಷಣ

ನಿಮ್ಮ ಆಟವು ನಾಲ್ಕು ಬಣ್ಣಗಳಲ್ಲಿ ಒಂದನ್ನು ತೋರಿಸುವುದರೊಂದಿಗೆ ನಿಮ್ಮ ಆಟವು ಪ್ರಾರಂಭವಾಗುತ್ತದೆ ಮತ್ತು ಆಟಗಾರನು ಬಣ್ಣ ಅನುಕ್ರಮವನ್ನು ಪುನರಾವರ್ತಿಸುವಾಗ ಕ್ಯಾರೆಕ್ಟರ್ ಯಾವಾಗಲೂ ಅನುಕ್ರಮದಲ್ಲಿ ಕೊನೆಯ ಬಣ್ಣವನ್ನು ತೋರಿಸುತ್ತದೆ ಎಂದು ನೀವು ನೋಡಬಹುದೇ?

ನೀವು ಇನ್ನೊಂದು ಸರಳ ಬಿಳಿ ವೇಷಭೂಷಣ ಸೇರಿಸಬಹುದ ನಿಮ್ಮ ಕ್ಯಾರೆಕ್ಟರ್ ಇಗೆ, ಮತ್ತು ಕೋಡ್ ಅನ್ನು ಸೇರಿಸಿ ಇದರಿಂದ ನಿಮ್ಮ ಕ್ಯಾರೆಕ್ಟರ್ ಇ ವೇಷಭೂಷಣ ವನ್ನು ಆಟದ ಪ್ರಾರಂಭದಲ್ಲಿ ಮತ್ತು ಆಟಗಾರನು ಅನುಕ್ರಮವನ್ನು ಪುನರಾವರ್ತಿಸುತ್ತಿರುವಾಗ ತೋರಿಸುತ್ತದೆ?

![screenshot](images/colour-white.png)

### ಕಷ್ಟದ್ದ ಮಟ್ಟ

ನಿಮ್ಮ ಆಟಗಾರನು ಆಟವನ್ನು ಆಡುವ ನಡುವೆ ಆಯ್ಕೆ ಮಾಡಲು ನೀವು ಅನುಮತಿಸಬಹುದೇ 'easy mode' (ಕೇವಲ ಬಳಸಿ red ಮತ್ತು blue ಬಣ್ಣಗಳು) ಮತ್ತು 'normal mode' (ಇದು ಎಲ್ಲಾ ನಾಲ್ಕು ಬಣ್ಣಗಳನ್ನು ಬಳಸುತ್ತದೆ)?

ನೀವು ಬಯಸಿದರೆ, ನೀವು ಸಹ ಸೇರಿಸಬಹುದು 'hard' mode, ಇದು ಐದನೇ ಡ್ರಮ್ ಅನ್ನು ಬಳಸುತ್ತದೆ!