## उच्च स्कोर

अब उच्च स्कोर को सहेजें ताकि आप अपने दोस्तों के खिलाफ खेल सकें।

\--- task \--- अपनी परियोजना में `उच्च स्कोर`{:class="block3variables"} और `नाम`{:class="block3variables"} नामक दो नए चर जोड़ें। \--- /task \---

खिलाड़ी का अनुक्रम गलत होने पर जब खेल समाप्त हो जाता है, तो खेल को यह जाँचना चाहिए कि स्कोर वर्तमान उच्च स्कोर से अधिक है या नहीं। यदि ऐसा है, तो खेल को स्कोर को उच्च स्कोर के रूप में सहेजना चाहिए, और खिलाड़ी का नाम भी संग्रहित करना चाहिए।

\--- task \--- `उच्च स्कोर`{:class="block3variables"} को सहेजने के लिए अपने पात्र स्प्राइट मे कोड जोड़ें । खिलाड़ी का नाम भी पूछें, और उसे `नाम`{:class="block3variables"} चर में संग्रहित करें।

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- आपके नए कोड को इस स्वरूप का पालन करने की आवश्यकता है:

`खेल समाप्त`{:class="block3looks"} संदेश के बाद `यदि`{:class="block3control"} `स्कोर`{:class="block3variables"} `उच्च स्कोर`{:class="block3variables"} `से ज़्यादा`{:class="block3operators"} है तो `उच्च स्कोर`{:class="block3variables"} को `स्कोर`{:class="block3variables"} से `स्थिर करें`{:class="block3variables"} खिलाड़ी का नाम `पूछें`{:class="block3sensing"} `नाम`{:class="block3variables"} को `उत्तर`{:class="block3sensing"} से `स्थिर करें`{:class="block3variables"}

आपको निम्नलिखित ब्लॉक चाहिए:

![ballerina](images/ballerina.png)

```blocks3
यदि < > तो
अंत

(स्कोर)

(स्कोर)

[] > []

उत्तर

(उच्च स्कोर)

[आपका नाम क्या है?] पूछें और प्रतीक्षा करें

[उच्च स्कोर v] को [] से स्थिर करें 

[नाम v] को [] से स्थिर करें 
```

\--- /hint \--- \--- hint \--- जब लाल बटन दबाया गया के लिए आपका कोड इस प्रकार दिखाई देना चाहिए:

![ballerina](images/ballerina.png)

```blocks3
जब मुझे [लाल v] प्राप्त हो
यदि < ([अनुक्रम v] का मद (1 v))=[1]> तो
    (0.25) बीट्स के लिए ([अनुक्रम v] का मद (1 v)) ड्रम बजाएँ
    [अनुक्रम v] का (1 v) हटाएँ 
अन्यथा
    (1) सेकंड के लिए [खेल समाप्त!] कहें 
    यदि < (स्कोर :: variables) > (उच्च स्कोर) > तो
        [उच्च स्कोर v] को (स्कोर :: variables) से स्थिर करें
        पूछें [उच्च स्कोर! आपका नाम क्या है?] और प्रतीक्षा करें
        [नाम v] को (उत्तर) से स्थिर करें
    अंत
    [सभी v] को रोकें
अंत
```

\--- /hint \--- \--- /hints \--- \--- /task \---

आपको इस नए कोड को अन्य तीन रंगों के लिए भी पात्र स्प्राइट में जोड़ने की आवश्यकता है!

क्या आप देख सकते हैं कि चारों रंगों के लिए 'खेल समाप्त' कोड बिल्कुल समान है?

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

If you need to change any of the 'Game over' code, for example to add a sound or change the 'Game over' message, you have to change it four times. That's annoying and wastes a lot of time.

Instead, you can define your own code block, and use it anywhere in your project.

\--- task \--- Click on `My blocks`{:class="block3myblocks"}, and then on **Make a Block**. Call this new block `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \--- Add the code from the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast to the `Game over`{:class="block3myblocks"} block so that it looks like this:

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

\--- /task \---

\--- task \--- Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

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

\--- /task \---

\--- task \--- Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence. \--- /task \---

Your new `Game over`{:class="block3myblocks"} block is a **function**, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="block3myblocks"} block in.

\--- task \--- Also replace the code in the `else`{:class="block3control"} block connected to the `broadcasts`{:class="block3events"} for the other colours with your new `Game over`{:class="block3myblocks"} block. Here is what the code for the `blue`{:class="block3events"} message should look like

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

\--- /task \---

\--- task \--- Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

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