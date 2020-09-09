## শব্দ যোগ করুন

--- task ---

আপনার প্রকল্পটি কয়েকবার পরীক্ষা করুন। আপনি কি লক্ষ্য করেছেন যে কখনও কখনও একই সংখ্যার পরপর দু'বার (বা তারও বেশি বার) বাছাই করা হয়েছে, যা ক্রমটি মুখস্থ করাকে শক্ত করে তোলে?

--- /task ---

আপনি কি প্রতিবার character sprite এর costume বাদলের জন্য ড্রামের শব্দ চালাতে চান? এবং প্রতিটি রঙের জন্য কী আলাদা ড্রামের শব্দ করতে চান?

--- task ---

আপনার প্রকল্পে muisc extension যুক্ত করতে আপনি `play drum`{:class="block3extensions"} ব্লক যোগ করুন.

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

ড্রাম বাজানো code **very** করে অনেকটা costume পাল্টানোর code এর মতো.

--- hints ---


--- hint ---

আপনাকে দুটো block যোগ করতে হবে: `play drum for (0.25) beats`{:class="block3sound"} block এবং `item (length of sequence) of sequence`{:class="block3variables"} block.

--- /hint ---

--- hint ---

আপনার যে blocks দরকার তা এখানে রয়েছে:

![ballerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

--- /hint ---

--- hint ---

আপনার সমাপ্ত code এখানে দেখতে কেমন হবে:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
    play drum (item (length of [sequence v]) of [sequence v]) for (0.25) beats
    switch costume to (item (length of [sequence v]) of [sequence v])
    wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---