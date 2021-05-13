## একটি রঙের ক্রম তৈরি করুন

প্রথমে এমন একটি character তৈরি করুন যা রঙের যেকোনো ক্রম প্রদর্শন করতে পারে।.

\--- task \---

একটি নতুন Scratch প্রকল্প খুলুন।.

**Online:** একটি নতুন online Scratch প্রকল্প খুলুন [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Offline:** offline editor এ একটি নতুন প্রকল্প খুলুন।.

আপনার যদি Scratch offline editor ডাউনলোড এবং ইনস্টল করতে হয় তবে আপনি এটি [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"} এ খুঁজে পেতে পারেন।.

\--- /task \---

\--- task \---

একটি character sprite এবং একটি backdrop চয়ন করুন। আপনি ballerina ব্যবহার করতে পারেন, তবে আপনার character টি কোনও ব্যক্তি হতে হবে না, তাদের কেবল বিভিন্ন রং প্রদর্শন করতে সক্ষম হওয়া প্রয়োজন।.

![screenshot](images/colour-sprite.png)

\--- /task \---

+ প্রতিটি রঙকে উপস্থাপন করতে আপনার গেমটির আলাদা নম্বর ব্যবহার করা উচিত:
    
    + 1 = লাল
    + 2 = নীল
    + 3 = সবুজ
    + 4 = হলুদ

\--- task \---

আপনার চরিত্রটিকে চারটি costume দিন যার বিভিন্ন বর্ণ রয়েছে, উপরে বর্ণিত চারটি বর্ণের একটির জন্য একটি costume। আপনার রঙিন costume উপরের তালিকার মতো একই ক্রমে রয়েছে তা নিশ্চিত করুন।.

![screenshot](images/colour-costume.png)

\--- /task \---

আপনি যদি চান তবে আপনি ** color a shape ** দিয়ে costume র অংশগুলিকে আলাদা রঙ দিয়ে পূরণ করতে পারেন.

![color-a-shape](images/color-a-shape.png)

এরপরে, আপনাকে মনে রাখতে হবে এমন যেকোনো রঙের ক্রম সংরক্ষণ করার জন্য একটি তালিকা যুক্ত করার বেপারে।.

\--- task \---

একটা তালিকা তৈরী করুন যার নাম `sequence`{:class="block3variables"}. কেবলমাত্র character sprite এই তালিকাটি দেখতে পারবে, সুতরাং আপনি এইটা **For this sprite only ** নির্বাচন করতে পারবেন তালিকা তৈরির সময়.

[[[generic-scratch3-make-list]]]

\--- /task \---

তালিকাগুলি ব্যবহারের জন্য এখন প্রচুর নতুন কোড ব্লক দেখতে পাবেন। স্টেজের উপরের বাম-কোণে খালি তালিকাটি দৃশ্যমান হওয়া উচিত।.

![screenshot](images/colour-list-blocks-annotated.png)

প্রতিটি রঙের একটি আলাদা নম্বর থাকে, তাই আপনি যেকোনো নম্বর দিয়ে রং ঠিক করতে পারবেন এবং তালিকায় যুক্ত করতে পারবেন.

\--- task \---

যেকোনো সংখ্যা চয়ন করতে এবং অনুক্রমের সাথে যুক্ত করতে এই কোড character sprite এ যুক্ত করুন `sequence ` {: class = "block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
add (pick random (1) to (4)) to [sequence v]
```

\--- /task \---

\--- task \---

আপনার কোড পরীক্ষা করুন। এটি পরীক্ষা করুন, প্রতিবার আপনি পতাকাটিতে ক্লিক করলে 1 থেকে 4 এর মধ্যে যেকোনো একটি সংখ্যা তালিকায় যুক্ত হয় কিনা।.

\--- /task \---

\--- task \---

আপনি একবারে যেকোনো পাঁচটি সংখ্যা তৈরি করে আপনার প্রোগ্রামে কোড যুক্ত করতে পারেন?

\--- hints \---

\--- hint \---

Add a `delete all of sequence`{:class="block3variables"} to first delete all the items on the list, and then add a `repeat`{:class="block3control"} block that adds five random numbers to the list.

\--- /hint \---

\--- hint \---

আপনার কোড দেখতে এমন হওয়া উচিত:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

প্রতিবার তালিকায় কোনও সংখ্যা যুক্ত হওয়ার সাথে সাথে character টির costume পরিবর্তন করা উচিত যাতে costume রঙ সংখ্যার সাথে মেলে।. এই কোড অবিলম্বে নীচে আপনার ব্লকে রাখুন যেখানে যেকোনো সংখ্যা যুক্ত করা হয় ` sequence ` {: class = "block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
switch costume to (item (length of [sequence v]) of [sequence v])
wait (1) seconds
```

\--- /task \---