## একাধিক স্তর

এখনও অবধি খেলোয়াড়কে কেবল পাঁচটি রঙের ক্রম মনে রাখতে হবে।. স্কোর যোগ করে এবং কোড যুক্ত করে আপনার গেমটি উন্নত করুন যাতে খেলোয়াড়ের স্কোর পয়েন্ট হিসাবে গেমটি পরবর্তী স্তরে চলে যায় এবং রঙের ক্রমটি যাতে দীর্ঘক্ষণ মনে রাখতে হয়.

--- task ---

Score নামে একটি নতুন variable তৈরি করুন `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

--- /task ---

`score`{:class="block3variables"}এর উপর ভিত্তি করে গেমটি রঙের ক্রমের দৈর্ঘ্যের বিষয়ে সিদ্ধান্ত নেবে। `3` এর স্কোর (এবং একটি ক্রম দৈর্ঘ্য) দিয়ে শুরু করুন।.

--- task ---

আপনার character টি শুরুতে একটি ব্লক যুক্ত করুন `when flag clicked`{:class="block3events"} কোড `score`{:class="block3variables"} থেকে `3`।.

--- /task ---

সর্বদা পাঁচটি রঙের ক্রম তৈরির পরিবর্তে, আপনি `score`{:class="block3variables"} কে দৈর্ঘ্য নির্ধারণ করতে দিন.

--- task ---

Character এর `repeat`{:class="block3control"} লুপ পরিবর্তন করুন (রঙের অনুক্রম তৈরির জন্য) `score`{:class="block3variables"} এর সময় পুনরাবৃত্তি করতে:

![sprite](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

--- /task ---

--- task ---

যদি প্লেয়ারটি সঠিক ক্রম পুনরাবৃত্তি করে তবে আপনার `1` `score`{:class="block3variables"} এ যোগ করা উচিত, এবং এর ফলে পরবর্তী ক্রমের দৈর্ঘ্য বৃদ্ধি পায়।. Character কোডের সাথে নীচের ব্লকটি যুক্ত করুন **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
change [score v] by (1)
```

--- hints ---


--- hint ---

আপনি জানেন ক্রমটি সঠিক যখন খেলাটি `broadcasts`{:class="block3events"} করে 'জয়' এর বার্তা দেয়.

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

অবশেষে, কোডটিতে একটা `forever`{:class="block3control"} লুপ যোগ করুন যেটি ক্রম বা sequence উত্পন্ন করে এবং যাতে খেলার প্রতিটি স্তরের জন্য একটি নতুন রঙ তৈরি করে।. আপনার character কোডটি এইরকম দেখতে হবে:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
set [score v] to [3]
forever
    delete (all v) of [sequence v]
    repeat (score)
        add (pick random (1) to (4)) to [sequence v]
        switch costume to (item (length of [sequence v]) of [sequence v]
        wait (1) seconds
    end
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
    change [score v] by (1)
end
```

--- /task ---

--- task ---

গেমটি পরীক্ষা করার জন্য আপনার বন্ধুদের ডাকুন। খেলার আগে `sequence`{:class="block3variables"} টি লুকাতে মনে রাখবেন!

--- /task ---