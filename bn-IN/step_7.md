## Challenge: আপনার গেমটি উন্নত করুন

### আরও ব্লক বানান

আপনি কি অন্য কোনও কোড দেখতে পান যা চারটি বোতামের জন্য একই?

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game Over :: custom
end

when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

আপনি কি অন্য কাস্টম ব্লক তৈরী করতে পারবেন যা সমস্ত বোতাম ব্যবহার করতে পারে?

### আরেকটি costume

আপনি দেখতে পাচ্ছেন যে আপনার গেমটি চারটি বর্ণের একটিতে আপনার character দেখানো দিয়ে শুরু হয়েছিল এবং প্লেয়ারটি বর্ণ ক্রমটি পুনরাবৃত্তি করার সময় character সর্বদা ক্রমের শেষ রঙটি প্রদর্শন করে?

আপনি কি আপনার চরিত্রের জন্য অন্য একটি সরল সাদা costume যুক্ত করতে পারেন এবং কোড যুক্ত করতে পারেন যাতে গেমের শুরুতে চরিত্রটি এই costume প্রদর্শন করে যখন প্লেয়ার ক্রমটি পুনরাবৃত্তি করে?

![screenshot](images/colour-white.png)

### কাঠিন্যের মাত্রা

আপনি কী 'খেলোয়াড়কে' ইজি মোড'/easy mode (কেবল লাল এবং নীল রঙ ব্যবহার করে) এবং 'সাধারণ মোড'/normal mode (যা চারটি রঙ ব্যবহার করে) এর মধ্যে গেম খেলার জন্য বেছে নেওয়ার অনুমতি দিতে পারেন?

আপনি যদি চান, আপনি এমনকি একটি 'হার্ড' মোড যুক্ত করতে পারেন, যা পঞ্চম ড্রাম ব্যবহার করে!