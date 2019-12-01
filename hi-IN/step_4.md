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

नीले, हरे और पीले स्प्राइट में भी ऐसा ही कोड जोड़ें, ताकि वे भी अपने रंग के बारे में संदेश ` प्रसारित करें ` {:class="block3events"}

\--- /task \---

क्या आपको याद है कि ` प्रसारित करें ` {:class="block3events"} एक लाउडस्पीकर संदेश की तरह है? आप ` प्रसारित करें `{:class="block3events"} संदेशों का जवाब देने को पात्र स्प्राइट की ज़िम्मेदारी बनाने के लिए कोड जोडेंगे।

\--- task \---

जब आपका पात्र स्प्राइट `लाल` {:class="block3events"} संदेश प्राप्त करता है, तो कोड को जांचना चाहिए कि संख्या `1` `अनुक्रम`{:class="block3variables"} सूची के प्रारंभ में है या नहीं (जिसका अर्थ है कि `लाल` {:class="block3events"} अनुक्रम में अगला रंग है)।

यदि `1` सूची की प्रारम्भ में है, कोड को सूची से संख्या को हटा देना चाहिए, क्योंकि खिलाड़ी को सही रंग याद था। अन्यथा खेल खत्म, और खेल को समाप्त करने के लिए कोड में `सभी को रोकें`{:class="block3control"}।

![ballerina](images/ballerina.png)

```blocks3
जब मुझे [लाल v] प्राप्त हो
अगर <[अनुक्रम v] का (मद (1 v))=[1]> फिर
[अनुक्रम v] का(1 v) हटाएँ
अन्यथा
(1) सेकंड के लिए [खेल समाप्त!] कहें
[सभी v] को रोकें
अंत
```

\--- /task \---

\--- task \--- आपके द्वारा लिखे गए कोड में जोड़ें ताकि जब पात्र स्प्राइट को सही `प्रसारित करें`{:class="block3events"} प्राप्त हो तो एक ड्रम की आवाज़ भी बजे।

\--- hints \--- \--- hint \--- क्या आप सही ड्रम की अवाज बजाने के लिए प्रत्येक रंग के अनुरूप संख्याओं का उपयोग कर सकते हैं?

+ 1 = लाल
+ 2 = नीला
+ 3 = हरा
+ 4 = पीला \--- /hint \--- \--- hint \--- `अनुक्रम का 1 हटाएं`{:class="block3variables"} ब्लॉक के ऊपर, `अनुक्रम`{:class="block3variables"} सूची में पहली ध्वनि बजाने के लिए `ड्रम बजाएँ`{:class="block3sound"} ब्लॉक जोड़ें।

\--- /hint \--- \--- hint \--- यहाँ आपको जोड़ने के लिए आवश्यक कोड है:

```blocks3
जब मुझे [लाल v] प्राप्त हो
अगर <[अनुक्रम v] का (मद (1 v))=[1]> फिर
+ (0.25) बीट्स के लिए (\(1\) फंदे वाला ड्रम v) बजाएँ
[अनुक्रम v] का(1 v) हटाएँ
अन्यथा
(1) सेकंड के लिए [खेल समाप्त!] कहें
[सभी v] को रोकें
अंत

```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- अपने पात्र स्प्राइट द्वारा `लाल`{:class="block3events"} संदेश के प्रति प्रतिक्रिया देने के लिए आपके द्वारा उपयोग किए गए कोड को दोहराएँ। दोहराए गए कोड को बदलें ताकि यह `नीला`{:class="block3events"} संदेश भेजे। \--- /task \---

जब स्प्राइट `नीला`{:class="block3events"} संदेश का जवाब देता है, तब कौन सा कोड समान रहना चाहिए, और कौन सा कोड बदलना चाहिए? याद रखें कि प्रत्येक रंग के अनुरूप एक संख्या है।

\--- task \--- पात्र स्प्राइट के कोड को बदलें ताकि पात्र `नीला`{:class="block3events"} संदेश को सही तरीके से प्रतिक्रिया दे।

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