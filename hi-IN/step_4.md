## Repeat the sequence

अब आप चार बटन जोड़ने जा रहे हैं जिन्हें खिलाड़ी को रंग क्रम दोहराने के लिए दबाना होगा।

\--- task \--- चार बटनों का प्रतिनिधित्व करने के लिए अपनी परियोजना में चार नए स्प्राइट जोड़ें।

+ नए स्प्राइट की पोशाक को संपादित करें ताकि चारों रंगों में से प्रत्येक में एक स्प्राइट हो
+ स्टेज पर स्प्राइट्स को पोशाकों के ही क्रम में डालें: लाल, नीला, हरा, पीला

![स्क्रीनशॉट](images/colour-drums.png) \--- /task \---

\--- task \--- लाल स्प्राइट में कोड जोड़ें ताकि स्प्राइट पर क्लिक करने पर यह पात्र स्प्राइट के लिए एक 'लाल' संदेश ` प्रसारित करें ` {:class="block3events"}:

![red-drum](images/red_drum.png)

```blocks3
    जब यह स्प्राइट क्लिक किया
    प्रसारित करें (लाल v)
```

\--- /task \---

` प्रसारित करें ` {"class =" block3events "} लाउडस्पीकर पर घोषित एक संदेश की तरह है, जिसे आप उदाहरण के लिए स्कूलों या सुपरमार्केटों में सुन सकते हैं। सभी स्प्राइट्स ` प्रसारित करें ` {:class="block3events"} को सुन सकते हैं, लेकिन केवल वह स्प्राइट ही कुछ करेगा जिसका काम इसका जवाब देना है।

\--- task \---

Add similar code to the blue, green, and yellow sprites to make them `broadcast`{:class="block3events"} messages about their own colour.

\--- /task \---

Do you remember that the `broadcast`{:class="block3events"} is like a loudspeaker message? You will add code to make it the character sprite's job to respond to the `broadcast`{:class="block3events"} messages.

\--- task \---

When your character sprite receives the message `red`{:class="block3events"}, the code should check whether the number `1` is at the start of the `sequence`{:class="block3variables"} list (which means that `red`{:class="block3events"} is the next colour in the sequence).

If `1` is at the start of the list, the code should remove the number from the list, because the player remembered the correct colour. Otherwise it's game over, and the code needs to `stop all`{:class="block3control"} to end the game.

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

\--- task \--- Add to the code you just wrote so that a drum beat also plays when the character sprite receives the correct `broadcast`{:class="block3events"}.

\--- hints \--- \--- hint \--- Can you use the numbers that correspond to each colour to play the correct drum beat?

+ 1 = red
+ 2 = blue
+ 3 = green
+ 4 = yellow \--- /hint \--- \--- hint \--- Above the `delete 1 of sequence`{:class="block3variables"} block, add the `play drum`{:class="block3sound"} block to play the first sound in the `sequence`{:class="block3variables"} list.

\--- /hint \--- \--- hint \--- Here is the code you will need to add:

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

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Duplicate the code you used to make your character sprite respond to the message `red`{:class="block3events"}. Change the duplicated code so that it sends the message `blue`{:class="block3events"}. \--- /task \---

When the sprite responds to the message `blue`{:class="block3events"}, which bit of code should stay the same, and which bit should change? Remember that each colour has a corresponding number.

\--- task \--- Change the character sprite's code so that the character responds correctly to the `blue`{:class="block3events"} message.

\--- hints \--- \--- hint \---

Keep these blocks, but you need to change them in some way:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

\--- /hint \--- \--- hint \--- Here is how your code should look for the `blue`{:class="block3events"} broadcast.

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

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Duplicate the code again twice (for the green and yellow buttons), and change the necessary parts so that the character responds correctly to the new `broadcasts`{:class="block3events"} . \--- /task \---

Remember to test the code! Can you memorise a sequence of five colours? Is the sequence different each time?

When the player repeats the whole colour sequence correctly, the `sequence`{:class="block3variables"} list emtpy and the player wins. If you want, you can also display some flashing lights as a reward once the `sequence`{:class="block3variables"} list is empty.

\--- task \--- Add this code to the end of your character's `when flag clicked`{:class="block3events"} script:

![ballerina](images/ballerina.png)

```blocks3
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
```

\--- /task \---

\--- task \--- Switch to the Stage, and import the `drum machine` sound or another sound you like.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \--- Add this code to play a sound and make the backdrop change colour when the player wins.

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