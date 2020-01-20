## Πολλαπλά επίπεδα

Μέχρι στιγμής, ο παίκτης πρέπει μόνο να θυμάται μια σειρά πέντε χρωμάτων. Βελτιώστε το παιχνίδι προσθέτοντας ένα σκορ και προσθέτοντας τον κωδικό έτσι ώστε, καθώς ο παίκτης βαθμολογεί τα σημεία, το παιχνίδι μετακινείται στο επόμενο επίπεδο και η ακολουθία χρωμάτων που θυμάται γίνεται μεγαλύτερη.

\--- task \---

Create a new variable called `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \---

Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`.

\--- / task \---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \---

Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
επανάληψη (βαθμολογία :: μεταβλητές)
τέλος
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
αλλαγή [βαθμολογία v] από (1)
```

\--- hints \---

\--- hint \---

You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks3
Όταν στην πράσινη σημαία γίνει κλικ
όρισε [βαθμολογία v] σε [3]
για πάντα 
  διάγραψε (all v) από λίστα [sequence v]
  επανάλαβε (score) 
    πρόσθεσε (επίλεξε τυχαίο (1) εώς (4)) στη λίστα [sequence v]
    άλλαξε ενδυμασία σε (στοιχείο (μήκος λίστας [sequence v]) λίστας [sequence v])
    περίμενε (1) δευτερόλεπτα
  end
  περίμενε ώσπου <(μήκος λίστας [sequence v]) = [0]>
  μετάδωσε (νίκη v) και περίμενε
  άλλαξε [βαθμολογία v] κατά (1)
end
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---