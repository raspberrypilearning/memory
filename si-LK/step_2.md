## වර්ණ(colour) අනුක්‍රමයක්(sequence එකක්) සෑදීම

පළමුව අහඹු(random) ලෙස වර්ණ(colour) අනුක්‍රමයක්(sequence එකක්) පෙන්විය හැකි චරිතයක්(character එකක්) සාදන්න.

\--- task \--- නව Scratch ව්යාපෘතියක්(project එකක්) විවෘත්ත කරන්න.

**අන්තර්ජාල මාර්ගගත(Online):** [rpf.io/scratch-new](https://rpf.io/scratchon) හි අන්තර්ජාල මාර්ගගතව නව Scratch ව්‍යාපෘතියක් විවෘත කරන්න.

**අන්තර්ජාලයට නොබැඳිව(Offline):** නොබැඳි සංස්කාරකයේ(offline editor එකේ) නව ව්‍යාපෘතියක්(new project එකක්) විවෘත කරන්න.

ඔබට Scratch නොබැඳි(offline) සංස්කාරකය(editor එක) බාගත(download) කර ස්ථාපනය(install) කිරීමට අවශ්‍ය නම්, ඔබට එය [rpf.io/scratchoff](https://rpf.io/scratchoff) වෙතින් ලබාගත හැකිය.

\--- /task \---

\--- task \--- sprite චරිතය(character එකක්) සහ පසුබිමක්(backdrop එකක්) තෝරාගන්න. ඔබට නර්තන ශිල්පිනිය භාවිතා කළ හැකිය, නමුත් ඔබේ චරිතය(character එක) පුද්ගල චරිතයක් විය යුතු නැත, අවශ්‍ය වන්නේ විවිධ වර්ණ පෙන්වීමට ඇති හැකියාව පමණි.

![තිර රුව(screenshot)](images/colour-sprite.png) \--- /task \---

+ එක් එක් වර්ණය නියෝජනය කිරීමට ඔබගේ ක්‍රීඩාව වෙනස්(different) අංකයක්(number එකක්) භාවිතා කළ යුතුයි:
    
    + 1 = red
    + 2 = blue
    + 3 = green
    + 4 = yellow

\--- task \--- ඔබේ චරිතයට(character එකට) විවිධ වර්ණ ඇති ඇඳුම්(costumes) හතරක් ලබා දෙන්න, ඉහත පෙන්වා ඇති වර්ණ හතරෙන් එක් එක් ඇඳුම(costume එක) එන පරිදි සකසන්න. ඔබේ වර්ණවත්(coloured) ඇඳුම්(costumes) ඉහත ලැයිස්තුවට(list) සමාන පිළිවෙලට(order එකට) ඇති බවට වග බලා ගන්න.

![තිර රුව(screenshot)](images/colour-costume.png) \--- /task \---

ඔබට අවශ්‍ය නම්, ඔබට **හැඩයක් වර්ණ ගැන්වීම(color a shape)** මෙවලම භාවිතා කර, ඇඳුමේ(costume එකේ) කොටස් වෙනත් වර්ණයකින් වර්ණ ගැන්විය හැකිය.

![color-a-shape](images/color-a-shape.png)

ඊළඟට, ක්‍රීඩකයා මතක තබා ගත යුතු වර්ණවල අහඹු(random) අනුක්‍රමය(sequence එක) ගබඩා(store) කිරීම සඳහා ලැයිස්තුවක්(list එකක්) එක් කරන්න.

\--- task \--- `sequence`{:class="block3variables"} නමින් ලැයිස්තුවක්(list එකක්) සාදන්න. මෙම ලැයිස්තුව දැකීමට අවශ්‍ය වන්නේ අදාළ sprite චරිතය(character එක) පමණි, එබැවින් ඔබ ලැයිස්තුව(list එක) නිර්මාණය කරන විට **මෙම sprite එක සඳහා පමණක්(for this sprite only)** තෝරා ගත හැකිය.

[[[generic-scratch3-make-list]]]

\--- /task \---

ලැයිස්තු(lists) භාවිතා කිරීම සඳහා ඔබට දැන් නව කේත(code) කට්ටි(blocks) ගොඩක් දැකගත හැකිය. හිස්(empty) ලැයිස්තුවක්(list එකක්) වේදිකාවේ ඉහළ වම්(left-hand) කෙළවරේ(corner එකේ) දැකිය හැකිය.

![තිර රුව(screenshot)](images/colour-list-blocks-annotated.png)

සෑම වර්ණයකටම වෙනස් අංකයක්(number එකක්) ඇත, එබැවින් ඔබට අහඹු(random) ලෙස අංකයක්(number එකක්) තෝරාගෙන එය ලැයිස්තුවට(list එකට) එක් කිරීමෙන් අහඹු(random) වර්ණයක්(colour එකක්) තෝරා ගත හැකිය.

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

ඔබගේ කේතය(code එක) මෙබඳු එකක් විය යුතුයි:

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