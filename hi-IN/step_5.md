## कई स्तर

अब तक, खिलाड़ी को केवल पांच रंगों का एक क्रम याद रखना पड़ता है। एक स्कोर जोड़कर और कोड जोड़कर ताकि जैसे ही खिलाड़ी अंक प्राप्त करे, खेल अगले स्तर पर चला जाए और याद रखने के लिए रंग अनुक्रम लंबा हो जाए अपने खेल में सुधार करें।

\--- task \--- `स्कोर`{:class="block3variables"} नामक एक नया चर बनाएं।

[[[generic-scratch3-add-variable]]] \--- /task \---

`स्कोर`{:class="block3variables"} के आधार पर, खेल रंग अनुक्रम की लंबाई पर फैसला करेगा। `3` के स्कोर (और एक अनुक्रम लंबाई) से शुरू करें।

\--- task \--- `स्कोर`{:class="block3variables"} को `3` पर स्थिर करने के लिए अपने पात्र के `जब ध्वज पर क्लिक किया`{:class="block3events"} कोड के प्रारंभ में एक खंड जोड़ें। \--- /task \---

हमेशा पांच रंगों के अनुक्रम को बनाने के बजाय, आप अब अनुक्रम की लम्बाई निर्धारित करने के लिए `स्कोर`{:class="block3variables"} चाहते हैं।

\--- task \--- Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

\--- /task \---

\--- task \--- If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
change [score v] by (1)
```

\--- hints \--- \--- hint \--- You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message. \--- /hint \--- \--- /hints \---

\--- /task \---

\--- task \--- Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

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

\--- /task \---

\--- task \--- Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it! \--- /task \---