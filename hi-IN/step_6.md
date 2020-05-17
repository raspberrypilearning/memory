## High score

अब उच्च स्कोर को सहेजें (save) ताकि आप अपने दोस्तों के खिलाफ खेल सकें।

\--- task \---

अपनी परियोजना में `high score`{:class="block3variables"} और `name`{:class="block3variables"} नामक दो नए वेरिएबल्स (variables) जोड़ें।

\--- /task \---

When the game ends because the player gets the sequence wrong, the game should check whether the score is higher than the current high score. यदि ऐसा है तो खेल को स्कोर को उच्च स्कोर के रूप में सहेजना चाहिए, और खिलाड़ी का नाम भी संग्रहित करना चाहिए।

\--- task \---

`high score`{:class="block3variables"} को सहेजने के लिए अपने पात्र स्प्राइट मे कोड जोड़ें । खिलाड़ी का नाम भी पूछें, और उसे `name`{:class="block3variables"} वेरिएबल में संग्रहित करें।

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

Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

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

You need to add this new code to the character sprite for the other three colours too!

क्या आप देख सकते हैं कि चारों रंगों के लिए 'खेल समाप्त' ('Game over') कोड बिल्कुल समान है?

![ballerina](images/ballerina.png)

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

![ballerina](images/ballerina.png)

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

![ballerina](images/ballerina.png)

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

Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence.

\--- /task \---

आपका नया `Game over`{:class="block3myblocks"} ब्लॉक एक **function** है, एक छोटी स्क्रिप्ट जिसे आप अपने कोड में `Game over`{:class="block3myblocks"} जोड़कर कहीं भी उपयोग कर सकते हैं।

\--- task \---

अब अन्य रंगो के लिए `broadcasts`{:class="block3events"} से जुड़े `else`{:class="block3control"} ब्लॉक के कोड को भी `Game over`{:class="block3myblocks"} ब्लॉक से बदलें। यहाँ दिखाया गया है कि `blue`{:class="block3events"} संदेश के लिए कोड कैसा दिखना चाहिए

![ballerina](images/ballerina.png)

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

Now add a sound that plays when the wrong button is pressed. आपको `Game over`{:class="block3myblocks"} ब्लाक जो आपने बनाया था में इस कोड को केवल एक बार जोड़ना होगा, और चार अलग-अलग जगहों पर नहीं!

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

\--- /task \---