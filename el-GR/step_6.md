## Υψηλή βαθμολογία

Τώρα σώστε το υψηλό σκορ ώστε να μπορείτε να παίξετε εναντίον των φίλων σας.

--- task ---

Προσθέστε δύο νέες μεταβλητές που ονομάζονται `υψηλό σκορ`{:class="block3variables"} και `όνομα`{:class="block3variables"} στο έργο σας.

--- /task ---

Όταν το παιχνίδι τελειώσει επειδή ο παίκτης παίρνει λάθος την ακολουθία, το παιχνίδι πρέπει να ελέγξει αν το σκορ είναι υψηλότερο από το τρέχον υψηλό σκορ. Αν είναι, το παιχνίδι πρέπει να σώσει το σκορ ως το υψηλό σκορ και επίσης να αποθηκεύσει το όνομα του παίκτη.

--- task ---

Προσθέστε τον κώδικα στον χαρακτήρα σας για να αποθηκεύσετε το `υψηλό σκορ`{:class="block3variables"}. Ζητήστε επίσης το όνομα του παίκτη και αποθηκεύστε το στη μεταβλητή `όνομα`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

--- hints ---

--- hint ---

Ο νέος σας κώδικας πρέπει να ακολουθήσει αυτό το μοτίβο:

Μετά τις `Τέλος Παιχνιδιού`{:class="block3looks"} μήνυμα `Αν`{:class="block3control"} οι `βαθμολογία`{:class="block3variables"} είναι `μεγαλύτερη από`{:class="block3operators "} η `υψηλή βαθμολογία`{:class="block3variables"} `Set`{:class="block3variables"} οι `υψηλή βαθμολογία`{:class="block3variables"} στο `στείλει`{:class="block3variables"} `Ζητήστε από`{:class="block3sensing"} για το όνομα του παίκτη `Σετ`{:class="block3variables"} το `όνομα`{:class="block3variables"} στο `απάντηση`{:class="block3sensing")

--- /hint ---

--- hint ---

Χρειάζεστε τα παρακάτω μπλοκ:

![μπαλλαρίνα](images/ballerina.png)

```blocks3
if < > then
end

(βαθμολογία)

(βαθμολογία)

[ ] > [ ]

answer

(υψηλή βαθμολογία)

ask [Πώς σε λένε;] and wait

set [υψηλή βαθμολογία v] to [ ] 

set [όνομα v] to [ ] 
```

--- /hint ---

--- hint ---

Ακολουθεί ο τρόπος με τον οποίο θα πρέπει να εμφανίζεται ο κωδικός σας για το πάτημα του κόκκινου κουμπιού:

![μπαλλαρίνα](images/ballerina.png)

```blocks3
when I receive [κόκκινο v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (item (1 v) of [sequence v]) for (0.25) beats
	delete (1 v) of [sequence v]
else
	say [Τέλος Παιχνιδιού!] for (1) seconds
	if < (βαθμολογία :: variables) > (υψηλή βαθμολογία) > then
		set [υψηλή βαθμολογία v] to (βαθμολογία :: variables)
		ask [υψηλή βαθμολογία! Ποιο είναι το όνομά σας;] and wait
		set [όνομα v] to (answer)
	end
	stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

Πρέπει να προσθέσετε αυτόν τον νέο κώδικα στο χαρακτήρα sprite και για τα άλλα τρία χρώματα!

Μπορείτε να δείτε ότι ο κωδικός 'Παιχνίδι πάνω' για κάθε ένα από τα τέσσερα χρώματα είναι ακριβώς ο ίδιος;

![μπαλλαρίνα](images/ballerina.png)

```blocks3
say [Τέλος Παιχνιδιού!] for (1) seconds
if < (βαθμολογία :: variables) > (υψηλή βαθμολογία) > then
	set [υψηλή βαθμολογία v] to (βαθμολογία :: variables)
	ask [υψηλή βαθμολογία! Ποιο είναι το όνομά σας;] and wait
	set [όνομα v] to (answer)
end
stop [all v]
```

Εάν πρέπει να αλλάξετε οποιονδήποτε από τους κωδικούς 'Παιχνίδι πάνω', για παράδειγμα για να προσθέσετε ήχο ή να αλλάξετε το μήνυμα 'Παιχνίδι πάνω', πρέπει να το αλλάξετε τέσσερις φορές. Αυτό είναι ενοχλητικό και σπαταλά πολύ χρόνο.

Αντ 'αυτού, μπορείτε να ορίσετε το δικό σας μπλοκ κώδικα και να το χρησιμοποιήσετε οπουδήποτε στο έργο σας.

--- task ---

Κάντε κλικ στο `Τα μπλοκ μου`{:class="block3myblocks"}, και έπειτα στο **Κάντε ένα μπλοκ**. Καλέστε αυτό το νέο μπλοκ `Παιχνίδι πάνω από`{:class="block3myblocks"}.

--- /task ---

--- task ---

Προσθέστε τον κώδικα από το `άλλο`{:class="block3control"} μπλοκ συνδέονται με τα `κόκκινα`{:class="block3events"} εκπέμπονται προς το `Τέλος Παιχνιδιού`{:class="block3myblocks"} μπλοκάρει έτσι ώστε να μοιάζει με αυτό:

![μπαλλαρίνα](images/ballerina.png)

```blocks3
define Τέλος Παιχνιδιού
say [Τέλος Παιχνιδιού!] for (1) seconds
if < (βαθμολογία :: variables) > (υψηλή βαθμολογία) > then
	set [υψηλή βαθμολογία v] to (βαθμολογία :: variables)
	ask [υψηλή βαθμολογία! Ποιο είναι το όνομά σας;] and wait
	set [όνομα v] to (answer)
end
stop [all v]
```

--- /task ---

--- task ---

Τώρα αφαιρέστε τον κώδικα που είναι στο `άλλο`{:class="block3control"} μπλοκ συνδέονται με τα `κόκκινα`{:class="block3events"} εκπομπή, και προσθέστε στο `Τέλος Παιχνιδιού`{:class="block3myblocks"}} αντί για:

![μπαλλαρίνα](images/ballerina.png)

```blocks3
when I receive [κόκκινο v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(1\) Snare Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Τέλος Παιχνιδιού :: custom
end
```

--- /task ---

--- task ---

Δοκιμάστε το νέο μπλοκ παίζοντας το παιχνίδι και κάνοντας κλικ στο κόκκινο κουμπί σε λάθος σημείο της ακολουθίας χρωμάτων.

--- /task ---

Το νέο σας `Τέλος Παιχνιδιού`{:class="block3myblocks"} μπλοκ είναι ένα **λειτουργία**, ένα μικρό script που μπορείτε να χρησιμοποιήσετε οπουδήποτε θέλετε στον κώδικά σας με την προσθήκη του `Τέλος Παιχνιδιού`{:class="block3myblocks"} μπλοκ σε.

--- task ---

Αντικαταστήστε επίσης τον κωδικό στο `άλλο`{:class="block3control"} μπλοκ που συνδέονται με τις `εκπομπές`{:class="block3events"} για τα άλλα χρώματα με το νέο σας `Τέλος Παιχνιδιού`{:class="block3myblocks"} μπλοκ. Εδώ θα πρέπει να μοιάσει ο κώδικας για το μήνυμα `μπλε`{:class="block3events"}

![μπαλλαρίνα](images/ballerina.png)

```blocks3
when I receive [μπλε v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	Τέλος Παιχνιδιού :: custom
end
```

--- /task ---

--- task ---

Προσθέστε τώρα έναν ήχο που παίζει όταν πιέσετε το λάθος κουμπί. Χρειάζεται μόνο να προσθέσετε αυτόν τον κωδικό μία φορά στο μπλοκ `Παιχνιδιού πάνω από`{:class="block3myblocks"} που κάνατε και όχι τέσσερις ξεχωριστές φορές!

![μπαλλαρίνα](images/ballerina.png)

```blocks3
define Τέλος Παιχνιδιού
start sound [Cough1 v]
say [Τέλος Παιχνιδιού!] for (1) seconds
if < (βαθμολογία :: variables) > (υψηλή βαθμολογία) > then
	play sound (trumpet1 v)
	set [υψηλή βαθμολογία v] to (βαθμολογία)
	ask [υψηλή βαθμολογία! Ποιο είναι το όνομά σας;] and wait
	set [όνομα v] to (answer)
end
stop [all v]
```

--- /task ---