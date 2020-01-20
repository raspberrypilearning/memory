## कई स्तर

अब तक, खिलाड़ी को केवल पांच रंगों का एक क्रम याद रखना पड़ता है। एक स्कोर जोड़कर और कोड जोड़कर ताकि जैसे ही खिलाड़ी अंक प्राप्त करे, खेल अगले स्तर पर चला जाए और याद रखने के लिए रंग अनुक्रम लंबा हो जाए अपने खेल में सुधार करें।

\--- task \---

Create a new variable called `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \---

Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`.

\--- /task \---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \---

Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
दोहरायें (स्कोर :: variables)
अंत
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
[स्कोर v] को (1) से बदलें
```

\--- hints \---

\--- hint \---

You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks3
जब झंडा क्लिक हुआ
[स्कोर v] को [3] स्थिर करें
हमेशा के लिए
    [अनुक्रम v] का (सभी v) हटाएँ
    दोहराएँ (स्कोर)
        [अनुक्रम v] में (यादृच्छिक (1) से (4) के बीच) जोड़ें
        ([अनुक्रम v] के (मद ([अनुक्रम v] की लंबाई)) से पोशाक बदलें
        (1) सेकंड प्रतीक्षा करें
    अंत
    < ([अनुक्रम v] की लंबाई = [0]> तक प्रतीक्षा करें;
    (जीत v) प्रसारित करें और प्रतीक्षा करें
    [ स्कोर v] को (1) से बदलें
अंत
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---