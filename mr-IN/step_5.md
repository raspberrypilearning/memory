## एकाधिक स्तर

आतापर्यंत, खेळाडूला फक्त पाच रंगांचा अनुक्रम लक्षात ठेवावा लागत होते. आपला स्कोअर जोडून आणि कोड जोडून आपला खेळ सुधारित करा जेणेकरून खेळाडूने गुणांची नोंद केली की हा खेळ पुढच्या स्तरावर जाईल आणि लक्षात ठेवण्यासाठी रंग अनुक्रम अधिक लांब होईल.

\--- task \---

`score`{:class="block3variables"} नावाचे एक नवीन व्हेरिएबल तयार करा.

[[[generic-scratch3-add-variable]]]

\--- /task \---

`score`{:class="block3variables"} वर आधारित, खेळ रंग क्रमांच्या लांबीवर निर्णय घेईल. `3` च्या गुण (आणि sequence (अनुक्रम) लांबी) सह प्रारंभ करा.

\--- task \---

ध्वज क्लिक केल्यावर आपल्या पात्राच्या `when flag clicked`{:class="block3events"} कोडच्या सुरूवातीस `score`{:class="block3variables"} स्कोअरला `3` सेट करण्यासाठी ब्लॉक जोडा.

\--- /task \---

नेहमी पाच रंगांचा क्रम तयार करण्याऐवजी, आपल्याला आता `score`{:class="block3variables"} (स्कोअर) पाहिजे आहे क्रम लांबी निश्चित करण्यासाठी.

\--- task \---

पात्राची `repeat`{:class="block3control"} (पुनरावृत्ती) लूप बदला (रंग अनुक्रम तयार करण्यासाठी) `score`{:class="block3variables"} (स्कोअर) वेळा पुन्हा करण्यासाठी:

![sprite](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

\--- /task \---

\--- task \---

जर खेळाडू अचूक क्रमवार पुनरावृत्ती करत असेल तर आपण `score`{:class="block3variables"} मध्ये `1` जोडावे, आणि असे केल्याने पुढील क्रमांची लांबी वाढते. पात्राच्या कोडमध्ये खालील ब्लॉक जोडा **ज्या जागे आपल्याला माहित आहे की क्रम बरोबर आहे**:

![sprite](images/ballerina.png)

```blocks3
change [score v] by (1)
```

\--- hints \---

\--- hint \---

आपल्‍याला माहित आहे की तेव्हा क्रम योग्य आहे जेव्हा खेळ 'win' विजय संदेश `broadcasts`{:class="block3events"} (प्रसारित) होईल.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

शेवटी, `forever`{:class="block3control"} लूप जोडा अनुक्रम बनावनारया कोडच्या जवळपास, जेणेकरून खेळ प्रत्येक स्तरासाठी नवीन रंग अनुक्रम तयार करेल. आपल्या पत्राचा कोड या प्रकारे दिसेल:

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

\--- task \---

आपल्या खेळाची चाचणी घेण्यासाठी आपल्या मित्रांना मिळवा. ते खेळण्यापूर्वी `sequence`{:class="block3variables"} (क्रम) list लपविणे लक्षात ठेवा!

\--- /task \---