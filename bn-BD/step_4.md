## ক্রম পুনরাবৃত্তি করুন

এখন আপনি চারটি বোতাম যোগ করতে যাচ্ছেন, প্লেয়ারকে রঙের ক্রম পুনরাবৃত্তি করতে চাপতে হবে।

\--- task \---

Add four new sprites to your project to represent the four buttons.

+ নতুন sprites 'পরিচ্ছদ সম্পাদনা করুন যাতে চার রং প্রতিটি এক sprite আছে
+ ভাস্কর্য হিসাবে লাল রঙের, নীল, সবুজ, হলুদ হিসাবে একই পর্যায়ে sprites রাখুন

![screenshot](images/colour-drums.png)

\--- /task \---

\--- task \---

Add code to the red sprite so that, when the sprite is clicked, it `broadcasts`{:class="block3events"} a 'red' message to the character sprite:

![red-drum](images/red_drum.png)

```blocks3
    যখন এই sprite
    সম্প্রচার ক্লিক করুন (লাল v)
```

\--- /task \---

A `broadcast`{:class="block3events"} is like a message announced over a loudspeaker, which you can for example hear in schools or supermarkets. All of the sprites can hear the `broadcast`{:class="block3events"}, but only the sprite whose job it is to respond will do something.

\--- task \---

Add similar code to the blue, green, and yellow sprites to make them `broadcast`{:class="block3events"} messages about their own colour.

\--- /task \---

Do you remember that the `broadcast`{:class="block3events"} is like a loudspeaker message? You will add code to make it the character sprite's job to respond to the `broadcast`{:class="block3events"} messages.

\--- task \---

When your character sprite receives the message `red`{:class="block3events"}, the code should check whether the number `1` is at the start of the `sequence`{:class="block3variables"} list (which means that `red`{:class="block3events"} is the next colour in the sequence).

If `1` is at the start of the list, the code should remove the number from the list, because the player remembered the correct colour. Otherwise it's game over, and the code needs to `stop all`{:class="block3control"} to end the game.

![ballerina](images/ballerina.png)

```blocks3
যখন আমি [লাল v]
পাই তখন যদি <(আইটেমটি 1 বনাম) [ক্রম বনাম] =[1]> তারপর
[মুছে ফেলা v] এর 
 মুছে ফেলা (1 বনাম)

বলুন [খেলা শেষ!] (1) সেকেন্ড
স্টপ [সব ভী]
শেষ
```

\--- /task \---

\--- task \---

Add to the code you just wrote so that a drum beat also plays when the character sprite receives the correct `broadcast`{:class="block3events"}.

\--- hints \---

\--- hint \---

Can you use the numbers that correspond to each colour to play the correct drum beat?

+ 1 = লাল
+ 2 = নীল
+ 3 = সবুজ
+ 4 = yellow

\--- /hint \---

\--- hint \---

Above the `delete 1 of sequence`{:class="block3variables"} block, add the `play drum`{:class="block3sound"} block to play the first sound in the `sequence`{:class="block3variables"} list.

\--- /hint \---

\--- hint \---

Here is the code you will need to add:

```blocks3
যখন আমি [লাল v]
পাই তাহলে [ <] (ক্রম বনাম] এর < (আইটেম (1 ভি)) =[1]> তারপর

+ ড্রাম ড্রাম (\ (1 \) স্ন্যার ড্রাম v) (0.25)
মুছে ফেলবে (1 v ) [ক্রম বনাম]
অন্য
বলুন [খেলা শেষ!] (1) সেকেন্ড
স্টপ [সব ভী]
শেষ
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code you used to make your character sprite respond to the message `red`{:class="block3events"}. Change the duplicated code so that it sends the message `blue`{:class="block3events"}.

\--- /task \---

When the sprite responds to the message `blue`{:class="block3events"}, which bit of code should stay the same, and which bit should change? Remember that each colour has a corresponding number.

\--- task \---

Change the character sprite's code so that the character responds correctly to the `blue`{:class="block3events"} message.

\--- hints \---

\--- hint \---

Keep these blocks, but you need to change them in some way:

![ballerina](images/ballerina.png)

```blocks3
<([ধারা বনাম] এর আইটেম (1 বনাম) = [1]>

যখন আমি [লাল v]

play drum (\ (1 \) স্ন্যারে ড্রাম v) (0.25) বিট
```

\--- /hint \---

\--- hint \---

Here is how your code should look for the `blue`{:class="block3events"} broadcast.

![ballerina](images/ballerina.png)

```blocks3
যখন আমি [নীল v]
পাই তখন [sequence v] এর <(item (1 v)) =[2]> তারপর
    ড্রাম (\ (2 \) বাস ড্রাম v) (0.25)
    মুছে ফেলবে (1 v) [অনুক্রম ভী]
অন্য
    বলুন [খেলা শেষ!] (1) সেকেন্ড
    স্টপ [সব ভী]
শেষ
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code again twice (for the green and yellow buttons), and change the necessary parts so that the character responds correctly to the new `broadcasts`{:class="block3events"}.

\--- /task \---

Remember to test the code! Can you memorise a sequence of five colours? Is the sequence different each time?

When the player repeats the whole colour sequence correctly, the `sequence`{:class="block3variables"} list emtpy and the player wins. If you want, you can also display some flashing lights as a reward once the `sequence`{:class="block3variables"} list is empty.

\--- task \---

Add this code to the end of your character's `when flag clicked`{:class="block3events"} script:

![ballerina](images/ballerina.png)

```blocks3
    < পর্যন্ত অপেক্ষা করুন [ক্রমানুসারে v]) = [0]>
    সম্প্রচার (জিতেছে v) এবং অপেক্ষা করুন
```

\--- /task \---

\--- task \---

Switch to the Stage, and import the `drum machine` sound or another sound you like.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \---

Add this code to play a sound and make the backdrop change colour when the player wins.

![ballerina](images/stage.png)

```blocks3
    যখন আমি পাই [জিতে v]
    শুরুর শব্দ (ড্রাম মেশিন v)
    পুনরাবৃত্তি (50)
        পরিবর্তন [রঙ v] প্রভাব (25)
        অপেক্ষা (0.1) সেকেন্ড
    শেষ
    স্পষ্ট গ্রাফিক প্রভাব
```

\--- /task \---