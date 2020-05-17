## Repeat the sequence

Now you're going to add four buttons the player has to press to repeat the colour sequence.

\--- task \---

चार बटनों का प्रतिनिधित्व करने के लिए अपनी प्रोजेक्ट में चार नए स्प्राइट जोड़ें।

+ नए स्प्राइट की पोशाक (costume) को संपादित (edit) करें ताकि चारों रंगों में से प्रत्येक में एक स्प्राइट हो
+ Put the sprites in the same order on the stage as the costumes: red, blue, green, yellow

![screenshot](images/colour-drums.png)

\--- /task \---

\--- task \---

लाल स्प्राइट में कोड जोड़ें ताकि स्प्राइट पर क्लिक करने पर यह पात्र स्प्राइट के लिए एक `broadcasts`{:class="block3events"} 'लाल' संदेश प्रसारित करें:

![red-drum](images/red_drum.png)

```blocks3
    when this sprite clicked
    broadcast (red v)
```

\--- /task \---

`broadcasts`{:class="block3events"} बटन एक लाउडस्पीकर पर घोषित एक संदेश की तरह है, जिसे आप उदाहरण के लिए स्कूलों या सुपरमार्केटों में सुन सकते हैं। सभी स्प्राइट्स `broadcast`{:class="block3events"}को सुन सकते हैं लेकिन केवल वह स्प्राइट ही कुछ करेगा जिसका काम इसका जवाब देना है।

\--- task \---

नीले, हरे और पीले स्प्राइट में भी ऐसा ही कोड जोड़ें, ताकि वे भी अपने रंग के बारे में `broadcast`{:class="block3events"} संदेश सुन पाएं |

\--- /task \---

क्या आपको याद है कि `broadcast`{:class="block3events"} एक लाउडस्पीकर संदेश की तरह है? आप `broadcast`{:class="block3events"} संदेशों का जवाब देने को पात्र स्प्राइट की ज़िम्मेदारी बनाने के लिए कोड जोडेंगे।

\--- task \---

जब आपका पात्र स्प्राइट `red`{:class="block3events"} संदेश प्राप्त करता है, तो कोड को जांचना चाहिए कि संख्या `1` `sequence`{:class="block3variables"} सूची के शुरुआत में है या नहीं (जिसका अर्थ है कि `red`{:class="block3events"} अनुक्रम में अगला रंग है)।

यदि `1` सूची की शुरुआत में है, कोड को सूची से संख्या को हटा देना चाहिए, क्योंकि खिलाड़ी को सही रंग याद था। अन्यथा खेल खत्म और खेल को समाप्त करने के लिए कोड में `stop all`{:class="block3control"} जोड़ें।

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /task \---

\--- task \---

Add to the code you just wrote so that a drum beat also plays when the character sprite receives the correct `broadcast`{:class="block3events"}.

\--- hints \---

\--- hint \---

Can you use the numbers that correspond to each colour to play the correct drum beat?

+ 1 = red
+ 2 = blue
+ 3 = green
+ 4 = yellow

\--- /hint \---

\--- hint \---

Above the `delete 1 of sequence`{:class="block3variables"} block, add the `play drum`{:class="block3sound"} block to play the first sound in the `sequence`{:class="block3variables"} list.

\--- /hint \---

\--- hint \---

Here is the code you will need to add:

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then

+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code you used to make your character sprite respond to the message `red`{:class="block3events"}. Change the duplicated code so that it sends the message `blue`{:class="block3events"}.

\--- /task \---

When the sprite responds to the message `blue`{:class="block3events"}, which bit of code should stay the same, and which bit should change? Remember that each colour has a corresponding number.

\--- task \---

Change the character sprite's code so that the character responds correctly to the `blue`{:class="block3events"} message.

\--- hints \---

\--- hint \---

Keep these blocks, but you need to change them in some way:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

\--- /hint \---

\--- hint \---

Here is how your code should look for the `blue`{:class="block3events"} broadcast.

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[2]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    stop [all v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code again twice (for the green and yellow buttons), and change the necessary parts so that the character responds correctly to the new `broadcasts`{:class="block3events"}.

\--- /task \---

Remember to test the code! Can you memorise a sequence of five colours? Is the sequence different each time?

When the player repeats the whole colour sequence correctly, the `sequence`{:class="block3variables"} list emtpy and the player wins. If you want, you can also display some flashing lights as a reward once the `sequence`{:class="block3variables"} list is empty.

\--- task \---

Add this code to the end of your character's `when flag clicked`{:class="block3events"} script:

![ballerina](images/ballerina.png)

```blocks3
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
```

\--- /task \---

\--- task \---

Switch to the Stage, and import the `drum machine` sound or another sound you like.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \---

Add this code to play a sound and make the backdrop change colour when the player wins.

![ballerina](images/stage.png)

```blocks3
    when I receive [won v]
    start sound (drum machine v)
    repeat (50)
        change [color v] effect by (25)
        wait (0.1) seconds
    end
    clear graphic effects
```

\--- /task \---