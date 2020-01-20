## উচ্চ স্কোর

এখন উচ্চ স্কোর সংরক্ষণ করুন যাতে আপনি আপনার বন্ধুদের বিরুদ্ধে খেলতে পারেন।

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
যদি < > তারপর
শেষ

(স্কোর)

(স্কোর)

[] > []

উত্তর

(উচ্চ স্কোর)

জিজ্ঞাসা করুন [আপনার নাম কি?] এবং

সেট [উচ্চ স্কোর v] থেকে [ 

] সেট করুন [ নাম ভি] থেকে [] 
```

\--- /hint \---

\--- hint \---

Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

```blocks3
যখন আমি [লাল v]
পাই তাহলে [ <] (ক্রম বনাম] এর < (আইটেম (1 ভি)) =[1]> তারপর
    ড্রাম (আইটেম (1 ক্রম) এর ড্রাম (আইটেমটি 1 ভি)) (0.25)
    মুছে ফেলবে (1 v) [ক্রমিক v]
আর
    বলুন [খেলা শেষ!] (1) সেকেন্ডের জন্য
    যদি < (স্কোর :: ভেরিয়েবল) > (উচ্চ স্কোর) > তারপর
        সেট [উচ্চ স্কোর v] থেকে (স্কোর :: ভেরিয়েবল )
        জিজ্ঞাসা [উচ্চ স্কোর! আপনার নাম কি?] এবং
        সেট [নাম ভি] থেকে অপেক্ষা করুন (উত্তর)
    শেষ
    স্টপ [সব ভী]
শেষ
```

\--- /hint \---

\--- /hints \---

\--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks3
বলুন [খেলা শেষ!] জন্য (1) সেকেন্ড
যদি < (স্কোর :: ভেরিয়েবল) > (উচ্চ স্কোর) > তারপর
    সেট [উচ্চ স্কোর v] থেকে (স্কোর :: ভেরিয়েবল)
    জিজ্ঞাসা করুন [উচ্চ স্কোর! আপনার নাম কি?] এবং
    সেট [নাম ভি] থেকে অপেক্ষা করুন (উত্তর)
শেষ
স্টপ [সব ভী]
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
খেলা
বলুন [খেলা শেষ!] জন্য (1) সেকেন্ড
যদি < (স্কোর :: ভেরিয়েবল) > (উচ্চ স্কোর) > তারপর
    সেট [উচ্চ স্কোর v] থেকে (স্কোর :: ভেরিয়েবল)
    জিজ্ঞাসা করুন [উচ্চ স্কোর ! আপনার নাম কি?] এবং
    সেট [নাম ভি] থেকে অপেক্ষা করুন (উত্তর)
শেষ
স্টপ [সব ভী]
```

\--- /task \---

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks3
যখন আমি [লাল v]
পাই তখন যদি <(আইটেমটি 1 বনাম) [ক্রম বনাম] =[1]> তারপর
    ড্রাম (\ (1 \) স্ন্যারে ড্রাম v) (0.25)
    মুছে ফেলবে (1 ভি) এর [ক্রম বনাম]
আর
    গেমস :: কাস্টম
এন্ড
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
যখন আমি [নীল v]
পাই তখন [sequence v] এর <(item (1 v)) =[1]> তারপর
    ড্রাম (\ (2 \) বাস ড্রাম v) (0.25)
    মুছে ফেলবে (1 v) এর [ক্রম বনাম]
আর
    গেমস :: কাস্টম
এন্ড
```

\--- /task \---

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks3
খেলা
শুরুর শব্দটি সংজ্ঞায়িত করুন [কাফ
ভি] 
 বলুন [খেলা শেষ!] জন্য (1) সেকেন্ড
 < (স্কোর :: ভেরিয়েবল) > (উচ্চ স্কোর) > তারপর
    বাজানো শব্দ (trumpet1 v)
    সেট [উচ্চ স্কোর v] থেকে (স্কোর)
    জিজ্ঞাসা [উচ্চ স্কোর! আপনার নাম কি?] এবং
    সেট [নাম ভি] থেকে অপেক্ষা করুন (উত্তর)
শেষ
স্টপ [সব ভী]
```

\--- /task \---