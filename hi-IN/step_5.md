## कई स्तर

अब तक खिलाड़ी को केवल पांच रंगों का एक क्रम याद रखना पड़ता है। एक स्कोर जोड़कर और कोड जोड़कर ताकि जैसे ही खिलाड़ी अंक प्राप्त करे, खेल अगले स्तर पर चला जाए और याद रखने के लिए रंग अनुक्रम लंबा हो जाए अपने खेल में सुधार करें।

--- task ---

`score`{:class="block3variables"} नामक वेरिएबल (variable) बनाएँ।

[[[generic-scratch3-add-variable]]]

--- /task ---

`score`{:class="block3variables"} के आधार पर, खेल रंग अनुक्रम की लंबाई पर फैसला करेगा। `3` के स्कोर (और एक अनुक्रम लंबाई) से शुरू करें।

--- task ---

`score`{:class="block3variables"} को `3` पर स्थिर करने के लिए अपने पात्र के `when flag clicked`{:class="block3events"} कोड के प्रारंभ में एक खंड जोड़ें।

--- /task ---

हमेशा पांच रंगों के अनुक्रम को बनाने के बजाय, आप अब अनुक्रम की लम्बाई निर्धारित करने के लिए `score`{:class="block3variables"} चाहते हैं।

--- task ---

पात्र के `repeat`{:class="block3control"} लूप (रंग अनुक्रम बनाने के लिए) को `score`{:class="block3variables"} बार दोहराने के लिए बदलें:

![स्प्राइट](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

--- /task ---

--- task ---

यदि खिलाड़ी सही अनुक्रम दोहराता है, तो आपको `score`{:class="block3variables"} में `1` जोड़ना चाहिए, और ऐसा करने से अगले अनुक्रम की लंबाई बढ़ जाती है। निम्न ब्लाक को पात्र के कोड में **उस बिंदु पर जोड़ें जहाँ आपको पता है कि अनुक्रम सही है**:

![स्प्राइट](images/ballerina.png)

```blocks3
change [score v] by (1)
```

--- hints ---

--- hint ---

जब खेल 'जीत' संदेश `broadcasts`{:class="block3events"} तो उस बिंदु पर आपको पता होता है कि अनुक्रम सही है।

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

अंत में, एक `forever`{:class="block3control"} लूप को अनुक्रम उत्पन्न करने वाले कोड के इर्द-गिर्द जोड़ें, जिससे गेम प्रत्येक स्तर पर एक नया रंग अनुक्रम बनाये। आपके पात्र का कोड ऐसा दिख सकता है:

![बैलरीना](images/ballerina.png)

```blocks3
when flag clicked
set [score v] to [3]
forever
    delete (all v) of [sequence v]
    repeat (score)
        add (pick random (1) to (4)) to [sequence v]
        switch costume to (item (length of 
[sequence v]) of [sequence v]
        wait (1) seconds
    end
    wait until < (length of [sequence v]) = 
[0]>
    broadcast (won v) and wait
    change [score v] by (1)
end
```

--- /task ---

--- task ---

अपने खेल का परीक्षण करने के लिए अपने दोस्तों को सहायता लें। उनके खेलने से पहले `sequence`{:class="block3variables"} सूची को छिपाने के लिए याद रखें!

--- /task ---