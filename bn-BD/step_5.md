## একাধিক মাত্রা

এ পর্যন্ত, প্লেয়ার শুধুমাত্র পাঁচ রং একটি ক্রম মনে আছে। স্কোর যুক্ত করে এবং কোড যোগ করে আপনার গেমটি উন্নত করুন যাতে প্লেয়ার স্কোর পয়েন্ট হিসাবে, খেলাটি পরবর্তী স্তরের দিকে যায় এবং মনে রাখতে রঙ ক্রমটি আরও বেশি হয়ে যায়।

\--- টাস্ক \--- একটি নতুন পরিবর্তনশীল তৈরি করুন `স্কোর`{: class = "block3variables"}।

[[[generic-scratch3-add-variable]]] \--- / টাস্ক \---

`স্কোর`উপর ভিত্তি করে {: class = "block3variables"}, খেলা রঙ ক্রমটির দৈর্ঘ্য নির্ধারণ করবে। `3`এর স্কোর (এবং একটি ক্রম দৈর্ঘ্য) দিয়ে শুরু করুন।

\--- কাজের \--- শুরুতে একটি ব্লক যুক্ত করো আপনার চরিত্র এর `যখন পতাকা ক্লিক`{: শ্রেণি = "block3events"} সেট করতে কোড `স্কোর`{: শ্রেণি = "block3variables"} থেকে `3`। \--- /কাজ \---

সর্বদা পাঁচটি বর্ণের ক্রম তৈরি করার পরিবর্তে, আপনি এখন অনুক্রমের দৈর্ঘ্য নির্ধারণ করতে `স্কোর`{: class = "block3variables"} চান।

\--- টাস্ক \--- অক্ষরটির `পুনরাবৃত্তি`{শ্রেণী = "ব্লক 3control"} লুপ পরিবর্তন করুন (রঙের ক্রম তৈরির জন্য) `স্কোর পুনরাবৃত্তি করতে {`: class = "block3variables"} বার:

![পরী](images/ballerina.png)

```blocks3
পুনরাবৃত্তি (স্কোর :: ভেরিয়েবল)
শেষ
```

\--- /কাজ \---

\--- টাস্ক \--- প্লেয়ার সঠিক অনুক্রমটি পুনরাবৃত্তি করলে, আপনাকে `1` থেকে `স্কোর`যোগ করতে হবে {: class = "block3variables"}, এবং এর ফলে পরবর্তী ক্রমটির দৈর্ঘ্য বাড়ায়। নিম্নোক্ত ব্লকটিকে চরিত্রের কোড **এ যোগ করুন যেখানে আপনি জানেন যে ক্রমিকটি সঠিক**:

![পরী](images/ballerina.png)

```blocks3
পরিবর্তন [স্কোর v] দ্বারা (1)
```

\--- নির্দেশ \--- \--- ইঙ্গিতটি \--- তুমি জানো ক্রম সময়ে সঠিক যখন খেলা `সম্প্রচার`{: শ্রেণি = "block3events"} বার্তা 'জয়'। \--- / ইঙ্গিত \--- \--- / ইঙ্গিত \---

\--- /কাজ \---

\--- কাজের \--- অবশেষে, একটি যোগ `সব সময় প্রবেশ করুন`{: শ্রেণি = "block3control"} কোডটি, ক্রম উত্পন্ন যাতে খেলা প্রতিটি স্তরের জন্য একটি নতুন রঙ ক্রম তৈরি করে প্রায় লুপ। আপনার চরিত্রের কোডটি কীভাবে দেখতে পারে:

![নর্তকী](images/ballerina.png)

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

\--- /কাজ \---

\--- টাস্ক \--- আপনার গেম পরীক্ষা করার জন্য আপনার বন্ধুদের পান। `ক্রম`লুকানোর কথা মনে রাখবেন: {ক্লাস = "ব্লক 3variables"} তারা এটি খেলা আগে তালিকা! \--- / টাস্ক \---