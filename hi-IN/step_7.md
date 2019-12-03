## चुनौती: अपने गेम में सुधार करें

### और ब्लॉक बनाएँ

क्या आपको कोई अन्य कोड दिखाई देता है जो चारों बटन के लिए समान है?

```blocks3
जब मुझे [लाल v] प्राप्त हो
अगर <[अनुक्रम v] का (मद (1 v))=[1]> फिर
    (0.25) बीट्स के लिए (\(1\) फंदे वाला ड्रम v) बजाएँ
    [अनुक्रम v] का (1 v) हटाएँ
अन्यथा
    खेल समाप्त :: custom
अंत

जब मुझे [नीला v] प्राप्त हो
अगर <[अनुक्रम v] का (मद (1 v))=[1]> फिर
    (0.25) बीट्स के लिए (\(2\) बेस वाला ड्रम v) बजाएँ
    [अनुक्रम v] का (1 v) हटाएँ
अन्यथा
    खेल समाप्त :: custom
अंत
```

क्या आप एक और कस्टम ब्लॉक बना सकते हैं जिसे सभी बटन उपयोग कर सकें?

### एक और पोशाक

क्या आप देख सकते हैं कि आपका खेल चार रंगों में से एक को दिखाने वाले आपके पात्र के साथ शुरू होता है, और जब खिलाड़ी रंग क्रम को दोहरा रहा होता है तो यह पात्र हमेशा अनुक्रम में अंतिम रंग दिखाता है?

Can you add another plain white costume to your character, and add code so that the character displays this costume at the start of the game and while the player is repeating the sequence?

![स्क्रीनशॉट](images/colour-white.png)

### Difficulty level

Can you allow your player to choose between playing the game in 'easy mode' (using just the red and blue colours) and 'normal mode' (which uses all four colours)?

If you want, you can even add a 'hard' mode, which makes use of a fifth drum!