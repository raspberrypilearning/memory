## সর্বচ্চ স্কোর

এখন সর্বচ্চ স্কোরটি সংরক্ষণ করুন যাতে আপনি আপনার বন্ধুদের বিরুদ্ধে খেলতে পারেন।.

--- task ---

আপনার প্রকল্পে দুটি নতুন variable যুক্ত করুন। `high score`{:class="block3variables"} এবং `name`{:class="block3variables"}.

--- /task ---

খেলোয়াড়টি ক্রম ভুল পেলে যখন খেলাটি শেষ হয়, তখন খেলাটির বর্তমান সর্বচ্চ স্কোরের চেয়ে স্কোর বেশি কিনা তা পরীক্ষা করা উচিত।. যদি এটি হয় তবে গেমটি সর্বচ্চ স্কোর হিসাবে শেষ স্কোরটি সংরক্ষণ করবে এবং প্লেয়ারের নামও সংরক্ষণ করবে।.

--- task ---

সর্বচ্চ স্কোর সংরক্ষণ করতে আপনার character sprite কোড যুক্ত করুন `high score`{:class="block3variables"}. এছাড়াও প্লেয়ারটির নাম জিজ্ঞাসা করুন এবং variable এ এটি সংরক্ষণ করুন `name`{:class="block3variables"}.

[[[generic-scratch3-high-score]]]

--- hints ---


--- hint ---

আপনার নতুন কোডটির এই প্যাটার্নটি অনুসরণ করা দরকার:

After the `Game over`{:class="block3looks"} message `If`{:class="block3control"} the `score`{:class="block3variables"} is `greater than`{:class="block3operators"} the `high score`{:class="block3variables"} `Set`{:class="block3variables"} the `high score`{:class="block3variables"} to the `score`{:class="block3variables"} `Ask`{:class="block3sensing"} for the player's name `Set`{:class="block3variables"} the `name`{:class="block3variables"} to the `answer`{:class="block3sensing"}

--- /hint ---

--- hint ---

আপনার নিম্নলিখিত ব্লকগুলি দরকার:

![ballerina](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```

--- /hint ---

--- hint ---

লাল বোতামটি চাপলে আপনার কোডটি কীভাবে দেখতে হবে:

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (high score) > then
        set [high score v] to (score :: variables)
        ask [High score! What is your name?] and wait
        set [name v] to (answer)
    end
    stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

অন্যান্য তিনটি রঙের জন্য আপনাকে এই নতুন কোডটিতে character sprite যুক্ত করতে হবে!

আপনি দেখতে পাচ্ছেন যে চারটি রঙের প্রতিটিটির জন্য 'game over' কোডটি এক রকম?

![ballerina](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

আপনার যদি কোনও 'game over' কোড পরিবর্তন করতে হয়, উদাহরণস্বরূপ কোনও শব্দ যোগ করতে বা 'game over' বার্তাটি পরিবর্তন করতে আপনাকে চারবার পরিবর্তন করতে হবে। এটি বিরক্তিকর এবং প্রচুর সময় নষ্ট করে।.

পরিবর্তে, আপনি নিজের কোড ব্লক সংজ্ঞায়িত করতে পারেন এবং এটি আপনার প্রকল্পের যে কোনও জায়গায় ব্যবহার করতে পারেন।.

--- task ---

এ ক্লিক করুন এবং তারপরে `My blocks`{:class="block3myblocks"} **Make a Block**। এই নতুন ব্লক এর উপরে কল করুন `Game over`{:class="block3myblocks"}.

--- /task ---

--- task ---

`else`{:class="block3control"} ব্লক থেকে কোড যুক্ত করুন যেটি `red`{:class="block3events"} এ যুক্ত ও `Game over`{:class="block3myblocks"} ব্লকে সম্প্রচার করুন যাতে এটি এমন দেখায়:

![ballerina](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

--- /task ---

--- task ---

এখন `else`{:class="block3control"} টির মধ্যে থাকা কোডটি মুছে ফেলুন, ব্লকের সাথে সংযুক্ত `red`{:class="block3events"}সম্প্রচার, এবং যুক্ত করুন `Game over`{:class="block3myblocks"} ব্লক এর পরিবর্তে:

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

--- /task ---

--- task ---

গেমটি খেলে এবং রঙের ক্রমের ভুল পয়েন্টে লাল বোতামটি ক্লিক করে আপনার নতুন ব্লকটি পরীক্ষা করুন।.

--- /task ---

আপনার নতুন `Game over`{:class="block3myblocks"} ব্লকটি একটি **function**, একটি ছোট স্ক্রিপ্ট যা আপনি আপনার কোডটিতে যে কোনও জায়গায় ব্লক হিসাবে যুক্ত করতে পারেন `Game over`{:class="block3myblocks"}.

--- task ---

`else`{:class="block3control"} টির মধ্যে কোডটি প্রতিস্থাপন করুন, `broadcasts`{:class="block3events"}সাথে সংযুক্ত ব্লক অন্যান্য রঙের জন্য `Game over`{:class="block3myblocks"} এই নতুন ব্লক. বার্তার কোডটি দেখতে কেমন হবে তা এখানে `blue`{:class="block3events"}

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

--- /task ---

--- task ---

এখন একটি শব্দ যুক্ত করুন যা ভুল বাটনটি টিপতে গেলে প্লে হয়।. আপনার কেবলমাত্র এই কোডটি `Game over`{:class="block3myblocks"} আপনি যে ব্লক তৈরী করেছেন তাতে একবার যুক্ত করতে হবে, চার বার নয়!

![ballerina](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

--- /task ---