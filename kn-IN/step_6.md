## ಹೆಚ್ಚಿನ ಅಂಕ

ಈಗ ಹೆಚ್ಚಿನ ಸ್ಕೋರ್ ಅನ್ನು ಉಳಿಸಿ ಇದರಿಂದ ನಿಮ್ಮ ಸ್ನೇಹಿತರ ವಿರುದ್ಧ ಆಡಬಹುದು.

--- task ---

ಎರಡು ಹೊಸ ವೇರಿಯೇಬಲ್ ಸೇರಿಸಿ `high score`{:class="block3variables"} ಮತ್ತು`name`{:class="block3variables"} ನಿಮ್ಮ ಯೋಜನೆಗೆ.

--- /task ---

ಆಟಗಾರನು ಅನುಕ್ರಮವನ್ನು ತಪ್ಪಾಗಿ ಪಡೆದ ಕಾರಣ ಆಟವು ಕೊನೆಗೊಂಡಾಗ, ಪ್ರಸ್ತುತ ಹೆಚ್ಚಿನ ಸ್ಕೋರ್‌ಗಿಂತ ಅಥವಾ ಈಗ ಪಡೆದ ಸ್ಕೋರ್ ಹೆಚ್ಚಿದೆಯೇ ಎಂದು ಆಟವು ಪರಿಶೀಲಿಸಬೇಕು. ಅದು ಇದ್ದರೆ, ಆಟವು ಸ್ಕೋರ್ ಅನ್ನು ಹೆಚ್ಚಿನ ಸ್ಕೋರ್ ಆಗಿ ಉಳಿಸಬೇಕು, ಮತ್ತು ಆಟಗಾರನ ಹೆಸರನ್ನು ಸಹ ಸಂಗ್ರಹಿಸಬೇಕು.

--- task ---

ನಿಮ್ಮ ಕ್ಯಾರೆಕ್ಟರ್ sprite ಇಗೆ `high score`{:class="block3variables"} ಉಳಿಸಲು ಕೋಡ್ ಸೇರಿಸಬೇಕು. ಆಟಗಾರನ ಹೆಸರನ್ನು ಸಹ ಕೇಳಿ, ಮತ್ತು ಅದನ್ನು ಸಂಗ್ರಹಿಸಿ `name`{:class="block3variables"} variable ನಲ್ಲಿ.

[[[generic-scratch3-high-score]]]

--- hints ---


--- hint ---

ನಿಮ್ಮ ಹೊಸ ಕೋಡ್ ಈ ಮಾದರಿಯನ್ನು ಅನುಸರಿಸಬೇಕು:

ನಂತರ `Game over`{:class="block3looks"} ಸಂದೇಶ `If`{:class="block3control"}`score`{:class="block3variables"}`greater than`{:class="block3operators"}`high score`{:class="block3variables"} `set`{:class="block3variables"}`high score`{: class="block3variables"}`score`{:class="block3variables"} `Ask`{:class="block3sensing} ಆಟಗಾರನ ಹೆಸರಿಗಾಗಿ `Set`{:class="block3variables"}`name`{:class="block3variables"}`answer`{:class="block3sensing"}.

--- /hint ---

--- hint ---

ನಿಮಗೆ ಈ ಕೆಳಗಿನ ಬ್ಲಾಕ್ಗಳು ಬೇಕಾಗುತ್ತವೆ:

![ballerina](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```

--- /hint ---

--- hint ---

Red ಬಟನ್ ಒತ್ತಿದಾಗ ನಿಮ್ಮ ಕೋಡ್ ಹೇಗೆ ಕಾಣುತ್ತದೆ ಎಂಬುದು ಇಲ್ಲಿದೆ:

![ನರ್ತಕಿಯಾಗಿ](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (ಹೆಚ್ಚಿನ ಸ್ಕೋರ್) > then
        set [ಹೆಚ್ಚಿನ ಸ್ಕೋರ್ v] to (score :: variables)
        ask [High score! What is your name?] and wait
        set [name v] to (answer)
    end
    stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

ಇತರ ಮೂರು ಬಣ್ಣಗಳಿಗೆ ನೀವು ಈ ಹೊಸ ಕೋಡ್ ಅನ್ನು ಕ್ಯಾರೆಕ್ಟರ್ sprite‌ಗೆ ಸೇರಿಸುವ ಅಗತ್ಯವಿದೆ!

ನಾಲ್ಕು ಬಣ್ಣಗಳಲ್ಲಿ ಪ್ರತಿಯೊಂದಕ್ಕೂ 'Game over' ಕೋಡ್ ಒಂದೇ ಆಗಿರುವುದನ್ನು ನೀವು ನೋಡಬಹುದೇ?

![ನರ್ತಕಿಯಾಗಿ](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
	set [high score v] to (score :: variables)
	ask [High score! What is your name?] and wait
	set [name v] to (answer)
end
stop [all v]
```

ನೀವು ಯಾವುದೇ 'Game over' code ಅನ್ನು ಬದಲಾಯಿಸಬೇಕಾದರೆ, ಉದಾಹರಣೆಗೆ ಧ್ವನಿಯನ್ನು ಸೇರಿಸಲು ಅಥವಾ 'Game over' ಸಂದೇಶವನ್ನು ಬದಲಾಯಿಸಲು, ನೀವು ಅದನ್ನು ನಾಲ್ಕು ಬಾರಿ ಬದಲಾಯಿಸಬೇಕು. ಅದು ಕಿರಿಕಿರಿ ಮತ್ತು ಸಾಕಷ್ಟು ಸಮಯವನ್ನು ವ್ಯರ್ಥ ಮಾಡುತ್ತದೆ.

ಬದಲಾಗಿ, ನಿಮ್ಮ ಸ್ವಂತ ಕೋಡ್ ಬ್ಲಾಕ್ ಅನ್ನು ನೀವು ವ್ಯಾಖ್ಯಾನಿಸಬಹುದು ಮತ್ತು ಅದನ್ನು ನಿಮ್ಮ ಯೋಜನೆಲಿ ಎಲ್ಲಿಯಾದರೂ ಬಳಸಬಹುದು.

--- task ---

ಇದನ್ನು ಒತ್ತಿ `My blocks`{:class="block3myblocks"}, ತದನಂತರ **Make a Block** ಒತ್ತಿ. ಹೊಸ ಬ್ಲಾಕ್ ಕಾರಿಯೆರೆ `Game over`{:class="block3myblocks"}.

--- /task ---

--- task ---

ಕೋಡ್ಅನ್ನು`else`{:class="block3control"} ಬ್ಲಾಕ್ ನಿಂದ ಸೇರಿಸಿ ಅದು ಸಂಪರ್ಕಗೊಂಡಿದೆ `red`{:class="block3events"} ಪ್ರಸಾರ ಗೆ `Game over`{:class="block3myblocks"} ಬ್ಲಾಕ್ ಆದ್ದರಿಂದ ಇದು ಈ ರೀತಿ ಕಾಣುತ್ತದೆ:

![ನರ್ತಕಿಯಾಗಿ](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

--- /task ---

--- task ---

ಈಗ ಕೋಡ್ ಅನ್ನು ತೆಗೆದುಹಾಕಿ ಅದು `else`{:class="block3control"} ಬ್ಲಾಕ್ ಅನ್ನು `red`{:class="block3events"}ಪ್ರಸಾರ ಗೆ ಸಂಪರ್ಕಿಸಲಾಗಿದೆ, ಮತ್ತು ಸೇರಿಸಿ `Game over`{:class="block3myblocks"} ಬ್ಲಾಕ್ಬದಲಾಗಿ:

![ನರ್ತಕಿಯಾಗಿ](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

--- /task ---

--- task ---

ಆಟವನ್ನು ಆಡುವ ಮೂಲಕ ನಿಮ್ಮ ಹೊಸ ಬ್ಲಾಕ್ ಅನ್ನು ಪರೀಕ್ಷಿಸಿ ಮತ್ತು red ಬಟನ್ ಬಣ್ಣದ ಅನುಕ್ರಮ ತಪ್ಪು ಹಂತದಲ್ಲಿ ಕ್ಲಿಕ್ ಮಾಡಿ.

--- /task ---

ನಿಮ್ಮ ಹೊಸ `Game over`{:class="block3myblocks"} ಬ್ಲಾಕ್ ಒಂದು **function**, ಸ್ವಲ್ಪ ಸ್ಕ್ರಿಪ್ಟ್ ಅದು ನಿಮಗೆ ಇಷ್ಟವಾದ ಕೋಡ್ ನಲ್ಲಿ ನೀವು ಎಲ್ಲಿ ಬೇಕಾದರೂ ಬಳಸಬಹುದಾದ `Game over`{:class="block3myblocks"} ಬ್ಲಾಕ್ ಒಳಗೆ ಸೇರಿಸಿ.

--- task ---

ಕೋಡ್ ಅನ್ನು ಸಹ ಬದಲಾಯಿಸಿ `else`{:class="block3control"} ಬ್ಲಾಕ್ `broadcasts`{:class="block3events"} ಗೆ ಸಂಪರ್ಕಿಸಲಾಗಿದೆ, ನಿಮ್ಮ ಹೊಸ ಬಣ್ಣಗಳೊಂದಿಗೆ ಇತರ ಬಣ್ಣಗಳಿಗಾಗಿ `Game over`{:class="block3myblocks"} ಬ್ಲಾಕ್. ಇಲ್ಲಿ ಕೋಡ್ ಏನು ಬೆಕೀರೋಧು `blue`{:class="block3events"} ಸಂದೇಶವು ಹೇಗಿರಬೇಕು

![ನರ್ತಕಿಯಾಗಿ](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

--- /task ---

--- task ---

ಈಗ ತಪ್ಪುಬಟನ್ ಒತ್ತಿದಾಗ ಪ್ಲೇ ಆಗುವ ಧ್ವನಿಯನ್ನು ಸೇರಿಸಿ. ನೀವು ಈ ಕೋಡ್ ಅನ್ನು ಒಮ್ಮೆ ಮಾತ್ರ ಸೇರಿಸಬೇಕಾಗಿದೆ `Game over`{:class="block3myblocks"}ಬ್ಲಾಕ್ ನೀವು ಮಾಡಿದ, ಮತ್ತು ನಾಲ್ಕು ಪ್ರತ್ಯೇಕ ಸಮಯಗಳಲ್ಲ!

![ನರ್ತಕಿಯಾಗಿ](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

--- /task ---