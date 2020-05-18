## ध्वनि जोड़ें

--- task ---

अपनी परियोजना का कुछ समय परीक्षण करें। क्या आपने ध्यान दिया कि कभी-कभी एक ही संख्या को एक लगातार दो (या अधिक) बार चुना जाता है, जिससे अनुक्रम को याद रखना कठिन हो जाता है?

--- /task ---

क्या आप हर बार जब भी पात्र स्प्राइट कॉस्ट्यूम (costume) बदलती है, एक ड्रम की आवाज़ बजा सकते हैं? और कैसा रहेगा कि प्रत्येक रंग के लिए एक अलग ड्रम की आवाज़ बजाई जाये?

--- task ---

अपनी परियोजना में संगीत एक्सटेंशन (music extension) जोड़ें ताकि आप `play drum`{:class="block3extensions"} ब्लॉक का प्रयोग कर सकें।

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

ड्रम बजाने वाला कोड पात्र की पोशाक को बदलने वाले कोड के **बहुत** ही समान है।

--- hints ---

--- hint ---

आपको केवल दो ब्लॉक जोड़ने की जरूरत है: एक `play drum for (0.25) beats`{:class="block3sound"} ब्लॉक और एक `item (length of sequence) of sequence`{:class="block3variables"} ब्लॉक।

--- /hint ---

--- hint ---

इन ब्लॉक्स की आपको आवश्यकता होगी:

![बैलरीना](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

--- /hint ---

--- hint ---

यहां बताया गया है कि आपका तैयार कोड कैसा दिखना चाहिए:

![बैलरीना](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
    play drum (item (length of [sequence v]) of [sequence v]) for (0.25) beats
    switch costume to (item (length of [sequence v]) of [sequence v])
    wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---