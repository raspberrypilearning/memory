## उच्च स्कोर

अब उच्च स्कोर को सहेजें (save) ताकि आप अपने दोस्तों के खिलाफ खेल सकें।

\--- task \---

अपनी परियोजना में `high score`{:class="block3variables"} और `name`{:class="block3variables"} नामक दो नए वेरिएबल्स (variables) जोड़ें।

\--- /task \---

खिलाड़ी का अनुक्रम गलत होने पर जब खेल समाप्त हो जाता है, तो खेल को यह जाँचना चाहिए कि स्कोर वर्तमान उच्च स्कोर से अधिक है या नहीं। यदि ऐसा है तो खेल को स्कोर को उच्च स्कोर के रूप में सहेजना चाहिए, और खिलाड़ी का नाम भी संग्रहित करना चाहिए।

\--- task \---

`high score`{:class="block3variables"} को सहेजने के लिए अपने पात्र स्प्राइट मे कोड जोड़ें । खिलाड़ी का नाम भी पूछें, और उसे `name`{:class="block3variables"} वेरिएबल में संग्रहित करें।

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

इस पैटर्न का पालन करने के लिए आपके नए कोड की आवश्यकता है:

`Game over`{:class="block3looks"} संकेत के बाद `If`{:class="block3control"} यदि `score`{:class="block3variables"} इससे `greater than`{:class="block3operators"} `high score`{:class="block3les"} तब `Set`{:class="block3variables"} `high score`{:class="block3variables"} उस `score`{:class="block3variables"} `Ask`{:class="block3sensing"} प्लेयर का नाम `Set`{:class="block3variables"} `name`{:class="block3variables"} करके `answer`{:clasck3sensing"}

\--- /hint \---

\--- hint \---

आपको निम्नलिखित ब्लॉक चाहिए:

![बैलरीना](images/ballerina.png)

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

\--- /hint \---

\--- hint \---

जब लाल बटन दबाया गया के लिए आपका कोड इस प्रकार दिखाई देना चाहिए:

![बैलरीना](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for 
(0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (high score) 
> then
        set [high score v] to (score :: variables)
        ask [High score! What is your name?] and wait
        set [name v] to (answer)
    end
    stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

आपको इस नए कोड को अन्य तीन रंगों के लिए भी पात्र स्प्राइट में जोड़ने की आवश्यकता है!

क्या आप देख सकते हैं कि चारों रंगों के लिए 'खेल समाप्त' ('Game over') कोड बिल्कुल समान है?

![बैलरीना](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > 
then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

यदि आपको 'खेल समाप्त' कोड में से किसी को बदलने की आवश्यकता है, उदाहरण के लिए ध्वनि जोड़ने या 'खेल समाप्त' संदेश को बदलने के लिए आपको इसे चार बार बदलना होगा। यह सरदर्दी है और बहुत समय बर्बाद करता है।

इसके बजाय आप अपने स्वयं के कोड ब्लॉक को परिभाषित कर सकते हैं और इसे अपनी परियोजना में कहीं भी उपयोग कर सकते हैं।

\--- task \---

`My blocks`{:class="block3myblocks"} पर क्लिक करें, और फिर **Make a block** पर क्लिक करें। इस नए ब्लॉक को `Game over`{:class="block3myblocks"} कहें।

\--- /task \---

\--- task \---

`red`{:class="block3events"} प्रसारण से जुड़े `else`{:class="block3control"} ब्लॉक के कोड को `Game over`{:class="block3myblocks"} ब्लॉक में जोड़ें ताकि यह इस तरह दिखे:

![बैलरीना](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > 
then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---

\--- task \---

अब `red`{:class="block3events"} प्रसारण से जुड़े `else`{:class="block3control"} ब्लॉक के कोड को हटाएँ और इसकी जगह `Game over`{:class="block3myblocks"} ब्लॉक को जोड़ें:

![बैलरीना](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) 
beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

खेल खेलते हुए और रंग क्रम में गलत स्थिति में लाल बटन पर क्लिक करके अपने नए ब्लॉक का परीक्षण करें।

\--- /task \---

आपका नया `Game over`{:class="block3myblocks"} ब्लॉक एक **function** है, एक छोटी स्क्रिप्ट जिसे आप अपने कोड में `Game over`{:class="block3myblocks"} जोड़कर कहीं भी उपयोग कर सकते हैं।

\--- task \---

अब अन्य रंगो के लिए `broadcasts`{:class="block3events"} से जुड़े `else`{:class="block3control"} ब्लॉक के कोड को भी `Game over`{:class="block3myblocks"} ब्लॉक से बदलें। यहाँ दिखाया गया है कि `blue`{:class="block3events"} संदेश के लिए कोड कैसा दिखना चाहिए

![बैलरीना](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) 
beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \---

अब एक आवाज़ जोड़ें जो गलत बटन दबाने पर बजेगी। आपको `Game over`{:class="block3myblocks"} ब्लाक जो आपने बनाया था में इस कोड को केवल एक बार जोड़ना होगा, और चार अलग-अलग जगहों पर नहीं!

![बैलरीना](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > 
then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---