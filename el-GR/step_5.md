## Πολλαπλά επίπεδα

Μέχρι στιγμής, ο παίκτης πρέπει μόνο να θυμάται μια σειρά πέντε χρωμάτων. Βελτιώστε το παιχνίδι προσθέτοντας ένα σκορ και προσθέτοντας τον κωδικό έτσι ώστε, καθώς ο παίκτης βαθμολογεί τα σημεία, το παιχνίδι μετακινείται στο επόμενο επίπεδο και η ακολουθία χρωμάτων που θυμάται γίνεται μεγαλύτερη.

\--- task \--- Δημιουργήστε μια νέα μεταβλητή που ονομάζεται `score`{: class = "block3variables"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

Με βάση την `όρος`{: class = «block3variables»}, το παιχνίδι θα αποφασίσει σχετικά με το μήκος της αλληλουχίας χρώματος. Ξεκινήστε με μια βαθμολογία (και ένα μήκος ακολουθίας) `3`.

\--- task \--- Προσθέστε ένα μπλοκ στην αρχή του χαρακτήρος σας `όταν πατήσατε σημαία`code: "block3events"} για να ορίσετε το `σκορ`{: class = "block3variables"} στο `3`. \--- / task \---

Αντί να δημιουργείτε πάντα μια ακολουθία πέντε χρωμάτων, θέλετε τώρα το `σκορ`{: class = "block3variables"} για να καθορίσετε το μήκος της ακολουθίας.

\--- καθήκον \--- Μεταβολή ο χαρακτήρας του `επανάληψης`{: class = "block3control"} βρόγχου (για τη δημιουργία της ακολουθίας χρώμα) να επαναλάβει `βαθμολογία`{: class = "block3variables"} φορές:

![ξωτικό](images/ballerina.png)

```blocks3
επανάληψη (βαθμολογία :: μεταβλητές)
τέλος
```

\--- / task \---

\--- task \--- Εάν ο παίκτης επαναλάβει τη σωστή ακολουθία, θα πρέπει να προσθέσετε `1` έως `βαθμολογία`{: class = "block3variables"}, αυξάνοντας έτσι το μήκος της επόμενης ακολουθίας. Προσθέστε το ακόλουθο μπλοκ στον κωδικό **του χαρακτήρα στο σημείο που γνωρίζετε ότι η ακολουθία είναι σωστή**:

![ξωτικό](images/ballerina.png)

```blocks3
αλλαγή [βαθμολογία v] από (1)
```

\--- Συμβουλές \--- \--- υπαινιγμός \--- Γνωρίζετε ότι η ακολουθία είναι σωστή στο σημείο όταν το παιχνίδι `μεταδίδει το`{: class = "block3events"} το μήνυμα "win". \--- / υπαινιγμός \--- \--- / υπαινιγμοί \---

\--- / task \---

\--- καθήκον \--- Τέλος, προσθέστε ένα `για πάντα`{: class = «block3control»} θηλιά γύρω από το κώδικα που παράγει την ακολουθία, έτσι ώστε το παιχνίδι δημιουργεί μια νέα ακολουθία χρώμα για κάθε επίπεδο. Αυτός είναι ο τρόπος εμφάνισης του κώδικα του χαρακτήρα σας:

![μπαλλαρίνα](images/ballerina.png)

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

\--- / task \---

\--- task \--- Πάρτε τους φίλους σας για να δοκιμάσετε το παιχνίδι σας. Θυμηθείτε να αποκρύψετε τη λίστα `σειράς`{: class = "block3variables"} πριν την αναπαράγουν! \--- / task \---