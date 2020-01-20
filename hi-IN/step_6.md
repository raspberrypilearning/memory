## उच्च स्कोर

अब उच्च स्कोर को सहेजें ताकि आप अपने दोस्तों के खिलाफ खेल सकें।

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

\--- /hint \---

\--- hint \---

Here's how your code for when the red button is pressed should look:

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

\--- /hint \---

\--- /hints \---

\--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks3
(1) सेकंड के लिए [खेल समाप्त!] कहें
यदि < (स्कोर :: variables) > (उच्च स्कोर) > तो
    [उच्च स्कोर v] को (स्कोर :: variables) से स्थिर करें
    पूछें [उच्च स्कोर! आपका नाम क्या है?] और प्रतीक्षा करें
        [नाम v] को (उत्तर) से स्थिर करें
    अंत
    [सभी v] को रोकें
अंत
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
खेल समाप्त को परिभाषित करें
(1) सेकंड के लिए [खेल समाप्त!] कहें
यदि < (स्कोर :: variables) > (उच्च स्कोर) > तो
    [उच्च स्कोर v] को (स्कोर :: variables) से स्थिर करें
    पूछें [उच्च स्कोर! आपका नाम क्या है?] और प्रतीक्षा करें
        [नाम v] को (उत्तर) से स्थिर करें
    अंत
    [सभी v] को रोकें
```

\--- /task \---

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks3
जब मुझे [लाल v] प्राप्त हो
अगर <[अनुक्रम v] का (मद (1 v))=[1]> फिर
    (0.25) बीट्स के लिए (\(1\) फंदे वाला ड्रम v) बजाएँ
    [अनुक्रम v] का (1 v) हटाएँ
अन्यथा
    खेल समाप्त :: custom
अंत
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
जब मुझे [नीला v] प्राप्त हो
अगर <[अनुक्रम v] का (मद (1 v))=[1]> फिर
    (0.25) बीट्स के लिए (\(2\) बेस वाला ड्रम v) बजाएँ
    [अनुक्रम v] का (1 v) हटाएँ
अन्यथा
    खेल समाप्त :: custom
अंत
```

\--- /task \---

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks3
खेल समाप्त को परिभाषित करें
[खाँसी1 v] आवाज़ शुरू करें 
(1) सेकंड के लिए  [खेल समाप्त!] कहें 
यदि < (स्कोर :: variables) > (उच्च स्कोर) > तो
    (तुरही1 v) आवाज़ बजाएँ
    [उच्च स्कोर] v] को (स्कोर) से स्थिर करें
    पूछें [उच्च स्कोर! आपका नाम क्या है?] और प्रतीक्षा करें
    [नाम v] को (उत्तर) से स्थिर करें
अंत
[सभी v] को रोकें
```

\--- /task \---