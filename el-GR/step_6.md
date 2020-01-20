## Υψηλή βαθμολογία

Τώρα σώστε το υψηλό σκορ ώστε να μπορείτε να παίξετε εναντίον των φίλων σας.

\--- task \---

Add two new variables called `high score`{:class="block3variables"} and `name`{:class="block3variables"} to your project.

\--- /task \---

When the game ends because the player gets the sequence wrong, the game should check whether the score is higher than the current high score. If it is, the game should save the score as the high score, and also store the name of the player.

\--- task \---

Add code to your character sprite to store the `high score`{:class="block3variables"}. Also ask for the player's name, and store it in the `name`{:class="block3variables"} variable.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Your new code needs to follow this pattern:

After the `Game over`{:class="block3looks"} message `If`{:class="block3control"} the `score`{:class="block3variables"} is `greater than`{:class="block3operators"} the `high score`{:class="block3variables"} `Set`{:class="block3variables"} the `high score`{:class="block3variables"} to the `score`{:class="block3variables"} `Ask`{:class="block3sensing"} for the player's name `Set`{:class="block3variables"} the `name`{:class="block3variables"} to the `answer`{:class="block3sensing"}

\--- /hint \---

\--- hint \---

You need the following blocks:

![ballerina](images/ballerina.png)

```blocks3
αν < > στη συνέχεια
άκρο

(βαθμολογία)

(βαθμολογία)

[] > []

απάντηση

(υψηλή βαθμολογία)

ζητήσει [Πώς σε λένε;] και περιμένετε

σύνολο [υψηλή βαθμολογία v] στη θέση [] 

σύνολο [ όνομα v] έως [] 
```

\--- /hint \---

\--- hint \---

Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

```blocks3
όταν λάβω [κόκκινο v]
αν <(στοιχείο (1 v) του [αλληλουχίας v]) =[1]> , στη συνέχεια,
    τύμπανο ενέργεια (στοιχείο (1 v) του [αλληλουχίας v]) για το (0,25) κτυπά
    διαγραφή (1 v) της [ακολουθίας v]
άλλο
    λένε [Game over!] για (1) δευτερόλεπτα
    εάν < (βαθμολογία :: μεταβλητές) > (υψηλή βαθμολογία) > τότε
        σύνολο [υψηλή βαθμολογία v] με (βαθμολογία :: μεταβλητές )
        ρωτήστε [Υψηλή βαθμολογία! Ποιο είναι το όνομά σας;] και περιμένετε
        ορίσετε [όνομα v] σε (απάντηση)
    τέλος
    τελεία [όλα]
τέλος
```

\--- /hint \---

\--- /hints \---

\--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks3
πες [Τέλος παιχνιδιού!]  για (1) δευτερόλεπτα
εάν < (βαθμολογία :: μεταβλητές) > (υψηλή βαθμολογία) > τότε
    όρισε [υψηλή βαθμολογία v] σε (βαθμολογία :: μεταβλητές)
    ρώτησε [Υψηλή βαθμολογία! Πώς σε λένε;] και περίμενε
όρισε [όνομα v] σε (απάντηση)
end
σταμάτησε [all v]
```

If you need to change any of the 'Game over' code, for example to add a sound or change the 'Game over' message, you have to change it four times. That's annoying and wastes a lot of time.

Instead, you can define your own code block, and use it anywhere in your project.

\--- task \---

Click on `My blocks`{:class="block3myblocks"}, and then on **Make a Block**. Call this new block `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Add the code from the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast to the `Game over`{:class="block3myblocks"} block so that it looks like this:

![ballerina](images/ballerina.png)

```blocks3
ορισμός Game over
πες [Τέλος παιχνιδιού!] για (1) δευτερόλεπτα
εάν <(βαθμολογία :: variables) > (Υψηλή βαθμολογία)> τότε 
  όρισε [Υψηλή βαθμολογία v] σε (βαθμολογία :: variables)
  ρώτησε [Υψηλή βαθμολογία!]
end Πώς σε λένε;] και περίμενε
όρισε [όνομα v] σε (απάντηση)
end
σταμάτησε [all v]
```

\--- /task \---

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks3
όταν λάβω [κόκκινο v]
εάν <(στοιχείο (1 v) λίστας [sequence v]) = [1]> τότε 
  παίξε τύμπανο ((1) Snare Drum v) για (0.25) χτύπους
  διάγραψε (1 v) από λίστα [sequence v]
αλλιώς 
  Game over :: custom
end
```

\--- /task \---

\--- task \---

Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence.

\--- /task \---

Your new `Game over`{:class="block3myblocks"} block is a **function**, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="block3myblocks"} block in.

\--- task \---

Also replace the code in the `else`{:class="block3control"} block connected to the `broadcasts`{:class="block3events"} for the other colours with your new `Game over`{:class="block3myblocks"} block. Here is what the code for the `blue`{:class="block3events"} message should look like

![ballerina](images/ballerina.png)

```blocks3
όταν λάβω [μπλε v]
εάν <(στοιχείο (1 v) λίστας [sequence v]) = [1]> τότε 
  παίξε τύμπανο ((2) Bass Drum v) για (0.25) χτύπους
  διάγραψε (1 v) από λίστα [sequence v]
αλλιώς 
  Game over :: custom
end
```

\--- /task \---

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks3
ορισμός Game over
παίξε τον ήχο [Cough1 v]
πες [Τέλος παιχνιδικού!] για (1) δευτερόλεπτα
εάν <(βαθμολογία :: variables)  > (Υψηλή βαθμολογία) > τότε 
  παίξε τον ήχο (trumpet1 v)
  όρισε [υψηλή βαθμολογία v] σε (score)
  ask [Υψηλή βαθμολογία!]
end Πώς σε λένε] και περίμενε
όρισε [όνομα v] σε (απάντηση)
end
σταμάτησε [all v]
```

\--- /task \---