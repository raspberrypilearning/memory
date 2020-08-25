## ক্রম বা sequence এর পুনরাবৃত্তি

এখন আপনি চারটি বোতাম যুক্ত করুন যাতে প্লেয়ারটি বোতাম টিপে রঙের ক্রম পুনরাবৃত্তি করতে পারে.

\--- task \---

চারটি বোতামের প্রতিনিধিত্ব করতে আপনার প্রকল্পে চারটি নতুন sprites যুক্ত করুন।.

+ নতুন sprite এর costume গুলি edit করুন যাতে চারটি বর্ণের প্রতিটিটিতে একটি করে sprite থাকে
+ Costume এর হিসাবে sprite গুলি একই ক্রমে রাখুন: লাল, নীল, সবুজ, হলুদ

![screenshot](images/colour-drums.png)

\--- /task \---

\--- task \---

'লাল' sprite এ কিছু কোড যুক্ত করুন যাতে এই sprite টি যখন ক্লিক করা হয়, তখন এটি ` broadcast ` ।: class= "block3events"} বার্তাটি "লাল" করে দেবে:

![red-drum](images/red_drum.png)

```blocks3
    when this sprite clicked
    broadcast (red v)
```

\--- /task \---

`broadcast`{:class="block3events"} একটি লাউড স্পিকারের মাধ্যমে ঘোষণা করা বার্তার মতো যা উদাহরণস্বরূপ বলা যায় যেগুলি স্কুল বা সুপারমার্কেটে শুনতে পাওয়া যায়।. Sprite রা সকলেই `broadcast`{:class="block3evnts"},শুনতে পারে, তবে কেবলমাত্র সেই sprites যার কাজ প্রতিক্রিয়া দেওয়া সেই শুধু প্রতিক্রিয়া দেবে.

\--- task \---

নীল, সবুজ এবং হলুদ sprite এ একই কোড যুক্ত করুন `broadcast`{:class="block3events"} যাতে তারা নিজস্ব রঙ সম্পর্কে বার্তা দেয়।.

\--- /task \---

আপনার কি মনে আছে যে `broadcast`{:class="block3events"} লাউডস্পিকারের বার্তার মতো? আপনি `broadcast`{:class="block3events"} বার্তাগুলির জবাব দেওয়ার জন্য ও character sprite কাজ করার জন্য code যুক্ত করবেন।.

\--- task \---

যখন আপনার character sprite `red`{:class="block3events"}বার্তাটি পেয়েছে, কোডটি `sequence`{:class="block3variables"} তালিকার শুরুতে `1` নম্বর কিনা তা যাচাই করা উচিত (which means that `red`{:class="block3events"} is the next colour in the sequence).

যদি `1` তালিকার শুরুতে থাকে তবে কোডটির তালিকা থেকে নম্বর সরিয়ে নেওয়া উচিত, কারণ প্লেয়ারটি সঠিক রঙটি মনে রেখেছিল।. তা না হলে খেলা শেষ এবং কোড টিকে `stop all`{:class="block3control"} করে খেলা শেষ করতে হবে।.

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /task \---

\--- task \---

আপনি যে কোডটি লিখেছেন সেটিতে যুক্ত করুন যাতে character sprite `broadcast`{:class="block3events"} প্রাপ্ত হলে ড্রাম বিট বাজায়.

\--- hints \---

\--- hint \---

সঠিক ড্রাম বিট দিতে আপনি কি প্রতিটি রঙের সাথে মেলে এমন নম্বর ব্যবহার করতে পারেন?

+ 1 = লাল
+ 2 = নীল
+ 3 = সবুজ
+ 4 = হলুদ

\--- /hint \---

\--- hint \---

উপরে `delete 1 of sequence`{:class="block3variables"} ব্লক আছে, `play drum`{:class="block3sound"} ব্লক যোগ করুন যাতে প্রথম শব্দটি চলে `sequence`{:class="block3variables"} লিস্টে.

\--- /hint \---

\--- hint \---

আপনার যে কোডটি যুক্ত করতে হবে:

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then

+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

আপনি নিজের character sprite `red`{:class="block3events"} বার্তাটিতে সাড়া দেওয়ার জন্য যে কোডটি ব্যবহার করেছেন সেটিকে নকল করুন. নকল কোডটি পরিবর্তন করুন যাতে এটি বার্তা পাঠাতে পারে `blue`{:class="block3events"}.

\--- /task \---

Sprite যখন বার্তাটি সাড়া দেয় `blue`{:class="block3events"}, তখন কোন bit কোড একই থাকা উচিত এবং কোন bit পরিবর্তন হওয়া উচিত? মনে রাখবেন যে প্রতিটি রঙের একটি অনুরূপ নম্বর রয়েছে।.

\--- task \---

Character sprite কোডটি পরিবর্তন করুন যাতে অক্ষরটি বার্তায় `blue`{:class="block3events"}সঠিকভাবে প্রতিক্রিয়া জানায়।.

\--- hints \---

\--- hint \---

এই ব্লক রাখুন, তবে আপনাকে এইগুলিতে কিছু উপায়ে পরিবর্তন করতে হবে:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

\--- /hint \---

\--- hint \---

আপনার কোডটি সম্প্রচারে এইরকম দেখতে হবে `blue`{:class="block3events"}.

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[2]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

কোডটি আবার দুবার নকল করুন (সবুজ এবং হলুদ বোতামগুলির জন্য) এবং প্রয়োজনীয় অংশগুলি পরিবর্তন করুন যাতে নতুন character সঠিকভাবে প্রতিক্রিয়া জানায় `broadcasts`{:class="block3events"}.

\--- /task \---

কোড পরীক্ষা করতে মনে রাখবেন! আপনি কি পাঁচটি রঙের একটি ক্রম মুখস্থ করতে পারবেন? ক্রমটি কি প্রতিবার আলাদা হয়?

যখন প্লেয়ার পুরো রঙের ক্রমটি সঠিকভাবে পুনরাবৃত্তি করে, `sequence`{:class="block3variables"} তালিকা খালি এবং প্লেয়ার জয়লাভ করে।. আপনি যদি চান, আপনি একবার পুরষ্কার হিসাবে কিছু ঝলকানি আলোও প্রদর্শন করতে পারেন `sequence`{:class="block3variables"} তালিকাটি খালি থাকলে.

\--- task \---

আপনার character টির শেষে এই কোডটি যুক্ত করুন `when flag clicked`{:class="block3events"}:

![ballerina](images/ballerina.png)

```blocks3
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
```

\--- /task \---

\--- task \---

Stage স্যুইচ করুন এবং `drum machine` শব্দ বা আপনার পছন্দ মতো অন্য শব্দ আমদানি করুন।.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \---

একটি শব্দ বাজানোর জন্য এই কোডটি যুক্ত করুন এবং প্লেয়ার জিতলে পটভূমির রং পরিবর্তন করুন।.

![ballerina](images/stage.png)

```blocks3
    when I receive [won v]
    start sound (drum machine v)
    repeat (50)
        change [color v] effect by (25)
        wait (0.1) seconds
    end
    clear graphic effects
```

\--- /task \---