## একটি রঙ ক্রম তৈরি করুন

প্রথম অক্ষরের একটি র্যান্ডম ক্রম প্রদর্শন করতে পারেন যে একটি অক্ষর তৈরি করুন।

\--- task \---

Open a new Scratch project.

**Online**: open a new online Scratch project at [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Offline**: open a new project in the offline editor.

If you need to download and install the Scratch offline editor, you can find it at [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}.

\--- /task \---

\--- task \---

Choose a character sprite and a backdrop. You could use the ballerina, but your character doesn't have to be a person, they only need to be able to show different colours.

![screenshot](images/colour-sprite.png)

\--- /task \---

+ আপনার খেলা প্রতিটি রং প্রতিনিধিত্ব করতে একটি ভিন্ন সংখ্যা ব্যবহার করা উচিত:
    
    + 1 = লাল
    + 2 = নীল
    + 3 = সবুজ
    + 4 = হলুদ

\--- task \---

Give your character four costumes that have different colours, one costumes for each of the four colours shown above. Make sure that your coloured costumes are in the same order as the list above.

![screenshot](images/colour-costume.png)

\--- /task \---

If you want, you can use the **color a shape** tool to fill parts of the costume with a different colour.

![color-a-shape](images/color-a-shape.png)

Next, add a list for storing the random sequence of colours that the player has to remember.

\--- task \---

Create a list called `sequence`{:class="block3variables"}. Only the character sprite needs to see this list, so you can select **For this sprite only** when you create the list.

[[[generic-scratch3-make-list]]]

\--- /কাজ \---

You should now see lots of new code blocks for using lists. The empty list should be visible in the top left-hand corner of the Stage.

![screenshot](images/colour-list-blocks-annotated.png)

Each colour has a different number, so you can choose a random colour by randomly choosing a number and adding it to the list.

\--- task \---

Add this code to the character sprite to choose a random number and add it to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
যখন পতাকা ক্লিক
যোগ (র্যান্ডম (1) থেকে (4)) [sequence v] বাছাই করুন
```

\--- /task \---

\--- task \---

Test your code. Check that, each time you click the flag, a random number between 1 and 4 gets added to the list.

\--- /task \---

\--- task \---

Can you add code to your program to generate five random numbers at once?

\--- hints \---

\--- hint \---

Add a `delete all of sequence`{:class="block3variables"} to first delete all the items on the list, and then add a `repeat`{:class="block3control"} block that adds five random numbers to the list.

\--- /hint \---

\--- hint \---

This is what your code should look like:

![ballerina](images/ballerina.png)

```blocks3
যখন পতাকাটি
ক্রমিক (সমস্ত বনাম) [ক্রম বনাম]
পুনরাবৃত্তি (5)
    যোগ ক্লিক করুন (র্যান্ডম (1) থেকে (4)) [ক্রমানুসারে]
প্রান্তে ক্লিক করুন
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Each time a number gets added to the list, the character should change its costume so the costume's colour matches the number. Put these blocks into your code immediately below where a random number is added to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
পরিচয়ে স্যুইচ করুন (আইটেম ([ক্রমানুসারে v] এর দৈর্ঘ্য] [ক্রম বনাম])
অপেক্ষা করুন (1) সেকেন্ড
```

\--- /task \---