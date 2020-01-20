## একাধিক মাত্রা

এ পর্যন্ত, প্লেয়ার শুধুমাত্র পাঁচ রং একটি ক্রম মনে আছে। স্কোর যুক্ত করে এবং কোড যোগ করে আপনার গেমটি উন্নত করুন যাতে প্লেয়ার স্কোর পয়েন্ট হিসাবে, খেলাটি পরবর্তী স্তরের দিকে যায় এবং মনে রাখতে রঙ ক্রমটি আরও বেশি হয়ে যায়।

\--- task \---

Create a new variable called `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \---

Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`.

\--- /কাজ \---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \---

Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
পুনরাবৃত্তি (স্কোর :: ভেরিয়েবল)
শেষ
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
পরিবর্তন [স্কোর v] দ্বারা (1)
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
যখন পতাকাটি
সেট [স্কোর ভ] থেকে [3]টিতে ক্লিক করে
চিরদিনের জন্য
    মুছে ফেলুন (সর্বাধিক v) [ক্রমবর্ধমান v]
    পুনরাবৃত্তি (স্কোর)
        যোগ করুন (র্যান্ডম (1) থেকে (4)) [ক্রম অনুসারে]
        সুইচ পরিচ্ছদ আইটেমে ((এর [ক্রম বনাম]) এর [ক্রম V] দৈর্ঘ্য
        অপেক্ষার (1) সেকেন্ড
    শেষ
    পর্যন্ত অপেক্ষা < ([ক্রম V]) = দৈর্ঘ্য [0]>
    ব্রডকাস্ট (জয়ী v) ও অপেক্ষা করুন
    পরিবর্তন করুন [ স্কোর V] দ্বারা (1)
শেষ
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---