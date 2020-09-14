## उच्च गुण

आता उच्च गुण जतन करा जेणेकरून आपण आपल्या मित्रांविरुद्ध खेळू शकाल.

--- task ---

`high score`{:class="block3variables"} आणि `name`{:class="block3variables"} नावाचे दोन नवीन variables (व्हरीएबलस) प्रकल्पात तयार करा.

--- /task ---

जेव्हा खेळ संपतो कारण खेळाडूला अनुक्रम चुकीचा मिळतो, तेव्हा खेळाला सध्याच्या उच्च स्कोअरपेक्षा स्कोअर जास्त आहे की नाही हे तपासले पाहिजे. जर तसे असेल तर खेळाने उच्च स्कोअर म्हणून स्कोअर जतन केले पाहिजेत आणि खेळाडूचे नाव देखील संग्रहित केले पाहिजे.

--- task ---

`high score`{:class="block3variables"} उच्च स्कोअर संचयित करण्यासाठी आपल्या पात्र spriteमध्ये कोड जोडा. तसेच खेळाडूचे नाव विचारा आणि ते `name`{:class="block3variables"} व्हरीएबल मध्ये संचयित करा.

[[[generic-scratch3-high-score]]]

--- hints ---


--- hint ---

आपल्या नवीन कोडला या पद्धतीचे अनुसरण करणे आवश्यक आहे:

`Game over`{:class="block3looks"} संदेशानंतर जर `If`{:class="block3control"} `score`{:class="block3variables"} (सध्याचे गुण) `greater than`{:class="block3operators"} `high score`{:class="block3variables"} (उच्च गुणं) पेक्षा जास्त असले `Set`{:class="block3variables"} `high score`{:class="block3variables"} `score`{:class="block3variables"} उच्च गुणं ला गुण च्या समान करा `Ask`{:class="block3sensing"} खेळाडूचे नाव विचारा `Set`{:class="block3variables"} `name`{:class="block3variables"} नावाला उत्तरा मध्ये संग्रहिट करा `answer`{:class="block3sensing"}

--- /hint ---

--- hint ---

आपल्याला खालील ब्लॉक्सची आवश्यकता आहे:

![ballerina](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```

--- /hint ---

--- hint ---

जेव्हा red बटण दाबले जाते तेव्हा आपला कोड कसा दिसावा ते येथे आहे:

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (high score) > then
        set [high score v] to (score :: variables)
        ask [High score! What is your name?] and wait
        set [name v] to (answer)
    end
    stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

आपल्याला इतर तीन रंगांसाठी देखील हा नवीन कोड पात्र sprite मध्ये जोडण्याची आवश्यकता आहे!

आपण पाहू शकता की चारी रंगांचा 'Game over' (गेम ओव्हर) कोड एकसारखाच आहे?

![ballerina](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

आपल्याला एखादा 'Game over' (गेम ओवर) कोड बदलण्याची आवश्यकता असल्यास, उदाहरणार्थ आवाज जोडण्यासाठी किंवा 'गेम ओव्हर' संदेश बदलण्यासाठी, आपल्याला तो चार वेळा बदलावा लागेल. ते त्रासदायक आहे आणि बराच वेळ वाया घालवते.

त्याऐवजी आपण आपला स्वतःचा कोड ब्लॉक परिभाषित करू शकता आणि तो आपल्या प्रकल्पात कोठेही वापरू शकता.

--- task ---

`My blocks`{:class="block3myblocks"} वर क्लिक करा आणि नंतर **Make a Block**. या नवीन ब्लॉकला नाव द्या `Game over`{:class="block3myblocks"}.

--- /task ---

--- task ---

`Game over`{:class="block3myblocks"} ब्लॉकवर `red`{:class="block3events"} ब्रॉडकास्टला कनेक्ट केलेल्या `else`{:class="block3control"} ब्लॉकमधील कोड जोडा जेणेकरुन हे दिसते:

![ballerina](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

--- /task ---

--- task ---

आता `red`{:class="block3events"} ब्रॉडकास्टला कनेक्ट केलेला `else`{:class="block3control"} ब्लॉकमध्ये असलेला कोड काढा आणि त्याऐवजी `Game over`{:class="block3myblocks"} ब्लॉकमध्ये जोडा:

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

--- /task ---

--- task ---

आपल्या नवीन ब्लॉकची चाचणी करण्यासाठी खेळ खेळतांना red बटण चुकीच्या रंग अनुक्रमात दाबून बघा.

--- /task ---

आपला नवीन `Game over`{:class="block3myblocks"} ब्लॉक हे **function** (फंक्शन) आहे, एक छोटी स्क्रिप्ट जी आपण आपल्या कोडमध्ये `Game over` जोडून आपल्या आवडीनुसार कोठेही वापरू शकता.

--- task ---

आता बाकीच्या रंगांच्या `broadcasts`{:class="block3events"} ब्रॉडकास्टला कनेक्ट केलेला `else`{:class="block3control"} ब्लॉकमध्ये असलेला कोड काढा आणि त्याऐवजी नवीन `Game over`{:class="block3myblocks"} ब्लॉक जोडा. `blue`{:class="block3events"} संदेशासाठी कोडे येथे आहे

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

--- /task ---

--- task ---

चुकीचे बटण दाबल्यावर वाजत असलेला आवाज जोडा. आपल्याला हा कोड केवळ `Game over`{:class="block3myblocks"} ब्लॉक मध्ये एकदा जोडण्याची आवश्यकता आहे, आणि चार वेगळ्या वेळा नाही!

![ballerina](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

--- /task ---