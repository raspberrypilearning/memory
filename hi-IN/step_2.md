## एक रंगो का अनुक्रम बनाएँ

पहले एक पात्र बनाएं जो रंगों के यादृच्छिक अनुक्रम को प्रदर्शित कर सके।

\---task \--- एक नया स्क्रैच प्रोजेक्ट खोलें।

** ऑनलाइन **: [ rpf.io/scratch-new ](https://rpf.io/scratchon) पर एक नया ऑनलाइन स्क्रैच प्रोजेक्ट खोलें ।

**ऑफ़लाइन**: ऑफ़लाइन संपादक में एक नया प्रोजेक्ट खोलें।

यदि आपको स्क्रैच ऑफ़लाइन संपादक को डाउनलोड और इंस्टॉल करने की आवश्यकता है, तो आप इसे [rpf.io/scratchoff](https://rpf.io/scratchoff) {:target="_blank"} पर पा सकते हैं।

\--- /task \---

\--- task \--- एक पात्र स्प्राइट और एक पृष्ठभूमि चुनें। आप बैलेरीना का उपयोग कर सकते हैं, लेकिन आपके पात्र को एक व्यक्ति होने की आवश्यकता नहीं है, उन्हें केवल अलग-अलग रंग दिखाने में सक्षम होने की आवश्यकता है।

![स्क्रीनशॉट](images/colour-sprite.png) \--- /task \---

+ Your game should use a different number to represent each colour:
    
    + 1 = red
    + 2 = blue
    + 3 = green
    + 4 = yellow

\--- task \--- Give your character four costumes that have different colours, one costumes for each of the four colours shown above. Make sure that your coloured costumes are in the same order as the list above.

![स्क्रीनशॉट](images/colour-costume.png) \--- /task \---

If you want, you can use the **color a shape** tool to fill parts of the costume with a different colour.

![color-a-shape](images/color-a-shape.png)

Next, add a list for storing the random sequence of colours that the player has to remember.

\--- task \--- Create a list called `sequence`{:class="block3variables"}. Only the character sprite needs to see this list, so you can select **For this sprite only** when you create the list.

[[[generic-scratch3-make-list]]]

\--- /task \---

You should now see lots of new code blocks for using lists. The empty list should be visible in the top left-hand corner of the Stage.

![स्क्रीनशॉट](images/colour-list-blocks-annotated.png)

Each colour has a different number, so you can choose a random colour by randomly choosing a number and adding it to the list.

\--- task \--- Add this code to the character sprite to choose a random number and add it to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
add (pick random (1) to (4)) to [sequence v]
```

\--- /task \---

\--- task \--- Test your code. Check that, each time you click the flag, a random number between 1 and 4 gets added to the list. \--- /task \---

\--- task \--- Can you add code to your program to generate five random numbers at once?

\--- hints \--- \--- hint \--- Add a `delete all of sequence`{:class="block3variables"} to first delete all the items on the list, and then add a `repeat`{:class="block3control"} block that adds five random numbers to the list. \--- /hint \--- \--- hint \---

यहाँ दिखाया गया है कि आपका कोड कैसा दिखना चाहिए:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Each time a number gets added to the list, the character should change its costume so the costume's colour matches the number. Put these blocks into your code immediately below where a random number is added to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
switch costume to (item (length of [sequence v]) of [sequence v])
wait (1) seconds
```

\--- /task \---