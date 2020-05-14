## Προσθήκη ήχου

--- task ---

Δοκιμάστε το έργο σας μερικές φορές. Παρατηρείτε ότι μερικές φορές ο ίδιος αριθμός επιλέγεται δύο φορές (ή περισσότερες) στη σειρά, γεγονός που καθιστά την αλληλουχία πιο δύσκολη στην απομνημόνευση;

--- /task ---

Μπορείτε να κάνετε έναν ήχο τυμπανισμού κάθε φορά που αλλάζει το κοστούμι του sprite χαρακτήρα και έναν διαφορετικό ήχο τυμπάνου για κάθε χρώμα;

--- task ---

Προσθέστε την επέκταση μουσικής στο έργο σας, ώστε να μπορείτε να χρησιμοποιήσετε το μπλοκ `παίξε τύμπανο`{:class="block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

Ο κώδικας που παίζει το τύμπανο είναι **πολύ** παρόμοιος με τον κώδικα που αλλάζει το κοστούμι του χαρακτήρα.

--- hints ---

--- hint ---

Το μόνο που χρειάζεται είναι να προσθέσετε δύο μπλοκ: α `παίξε τύμπανο για (0.25) κτύπους`{:class="block3sound"} μπλοκ και ένα `στοιχείο (μήκος λίστας) της [λίστας]`{:class="block3variables"}.

--- /hint ---

--- hint ---

Εδώ είναι τα μπλοκ που χρειάζεστε:

![μπαλλαρίνα](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

--- /hint ---

--- hint ---

O τρόπος με τον οποίο πρεπει να μοίαζει ο τελικό σας κώδικας:

![μπαλλαρίνα](images/ballerina.png)

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