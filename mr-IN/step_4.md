## क्रम पुन्हा करा

आता आपण चार बटणे जोडणार आहोत जे रंग क्रम पुन्हा पुन्हा करण्यासाठी खेळाडूला दाबावे लागेल.

--- task ---

चार बटणे दर्शवण्यासाठी आपल्या प्रकल्पात चार नवीन sprite जोडा.

+ नवीन spritesचे पोशाख संपादित करा जेणेकरुन चारही रंगात एकspriteअसेल
+ पोशाखांप्रमाणेच स्टेजवर त्याच क्रमाने sprites ठेवा: red, blue, green, yellow

![screenshot](images/colour-drums.png)

--- /task ---

--- task ---

'red' sprite मध्ये असा कोड जोडा जेणेकरून जेव्हा हा sprite क्लिक केला जाईल तेव्हा "red" संदेश `broadcasts`{:class="block3events"} पात्र sprite ला प्रसारित होईल:

![red-drum](images/red_drum.png)

```blocks3
    when this sprite clicked
    broadcast (red v)
```

--- /task ---

एक `broadcast`{:class="block3events"} लाउडस्पीकरद्वारे घोषित केलेल्या संदेशासारखे आहे, जे आपण उदाहरणार्थ शाळा किंवा सुपरमार्केटमध्ये ऐकू शकता. सर्व sprite `broadcast`{:class="block3events"} ऐकू शकतात, परंतु ज्या sprite ला कार्य उत्तर देणे आहे फक्त त्यालाच ते करावा लागेल.

--- task ---

Blue,green आणि yellow रंगाच्या spriteमध्ये समान कोड जोडा जे त्यांच्या स्वतःच्या रंगाविषयी संदेश `broadcast`{:class="block3events"} (प्रसारित) करेल.

--- /task ---

आपणास हे आठवते की `broadcast`{:class="block3events"} लाउडस्पीकर संदेशासारखे आहे? आपण `broadcast`{:class="block3events"} (प्रसारणास) प्रतिसाद देण्यासाठी पात्र sprite मध्ये कार्य करण्यासाठी कोड जोडणार.

--- task ---

जेव्हा आपल्या पात्र sprite ला `red`{:class="block3events"} रंगाचा संदेश प्राप्त होतो, कोड संख्या `1` आहे की नाही ते तपासा `sequence`{:class="block3variables"} list च्या सुरूवातीस आहे (ज्याचा अर्थ `red`{:class="block3events"} अनुक्रमातील पुढील रंग आहे).

जर `1` यादीच्या सुरूवातीस आहे, कोडने यादीतून संख्या काढून टाकला पाहिजे, कारण खेळाडूला योग्य रंग आठवला. अन्यथा हा खेळ संपला आहे आणि कोडला `stop all`{:class="block3control"} (सर्व थांबविणे) आवश्यक आहे खेळ समाप्त करण्यासाठी.

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

--- /task ---

--- task ---

आपण आत्ताच लिहिलेला कोड जोडा जेणेकरुन जेव्हा पत्राचे sprite योग्य `broadcast`{:class="block3events"} (प्रसारण) प्राप्त करेल तेव्हा ड्रम बीट देखील वाजेल.

--- hints ---


--- hint ---

योग्य ड्रम बीट वाजविण्यासाठी आपण प्रत्येक रंगाशी संबंधित क्रमांक वापरू शकता का?

+ 1 = red
+ 2 = blue
+ 3 = green
+ 4 = yellow

--- /hint ---

--- hint ---

`delete 1 of sequence`{:class="block3variables"} ब्लॉक च्या वर, `play drum`{:class="block3sound"} ब्लॉक जोडा ज्यांनी `sequence`{:class="block3variables"} list मधली पहिला आवाज प्ले हुईल.

--- /hint ---

--- hint ---

आपल्याला जोडण्यासाठी आवश्यक असलेला कोड येथे आहे:

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

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

आपण आपल्या पात्र sprite ला `red`{:class="block3events"} संदेशास प्रतिसाद देण्यासाठी कोडचा नक्कल बनवा. नक्कल कोड बदला जेणेकरून तो `blue`{:class="block3events"}. निरोप पाठवेल.

--- /task ---

जेव्हा sprite `blue`{:class="block3events"}. संदेशास प्रतिसाद देते, कोणता कोडचा अंश समान राहिला पाहिजे आणि कोणता अंश बदलला पाहिजे? लक्षात ठेवा प्रत्येक रंगात एक समान संख्या आहे.

--- task ---

पात्राच्या spriteचा कोड बदला जेणेकरून पात्र `blue`{:class="block3events"} संदेशाला योग्य प्रतिसाद दिल.

--- hints ---


--- hint ---

हे ब्लॉक ठेवा, परंतु आपल्याला काही बदल करावा लागेल:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

--- /hint ---

--- hint ---

आपला कोड `blue`{:class="block3events"} प्रसारण साठी कसा दिसला पाहिजे ते येथे आहे.

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

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

कोडची पुन्हा पुन्हा नक्कल करा (green आणि yellowबटणासाठी) आणि आवश्यक भाग बदला जेणेकरुन पात्र नवीन `broadcasts`{:class="block3events"} (प्रसारणास) योग्य प्रतिसाद देईल.

--- /task ---

कोडची चाचणी करणे लक्षात ठेवा! आपण पाच रंगांचा क्रम लक्षात ठेवू शकता? प्रत्येक वेळी क्रम वेगळा आहे का?

जेव्हा खेळाडू संपूर्ण रंग अनुक्रम योग्यरित्या पुनरावृत्ती करतो तेव्हा `sequence`{:class="block3variables"} यादी रिकामी होईल आणि खेळाडू जिंकेल. आपण इच्छित असल्यास, `sequence`{:class="block3variables"} यादी रिकामी झाल्यानंतर आपण बक्षीस म्हणून काही चमकणारे दिवे देखील प्रदर्शित करू शकता.

--- task ---

आपल्या पात्रच्या `when flag clicked`{:class="block3events"} (ध्वज क्लिक केल्यावर) स्क्रिप्ट च्या शेवटी हा कोड जोडा:

![ballerina](images/ballerina.png)

```blocks3
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
```

--- /task ---

--- task ---

स्टेजवर स्विच करा आणि `drum machine` चा आवाज किंवा आपल्याला आवडत असलेला दुसरा आवाज.

[[[generic-scratch3-sound-from-library]]]

--- /task ---

--- task ---

ध्वनी प्ले करण्यासाठी आणि जेव्हा खेळाडू जिंकतो तेव्हा पार्श्वभूमी बदलण्यासाठी हा कोड जोडा.

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

--- /task ---