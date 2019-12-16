## අනුක්‍රමය නැවත නැවත(repeat) ක්‍රියාත්මක කිරීම

දැන් ඔබ සූදානම් වන්නෙ බොත්තම්(buttons) හතරක් එක් කිරීමටයි, ක්‍රීඩකයාට එම බොත්තම් එබීම මගින් වර්ණ(colour) අනුක්‍රමය(sequence එක) නැවත නැවත(repeat) ක්‍රියාත්මක කරවිය හැකියි.

\--- task \--- බොත්තම්(buttons) හතර නියෝජනය කිරීම සඳහා, ඔබේ ව්‍යාපෘතියට නව sprite හතරක් එක් කරන්න.

+ නව sprite වල ඇඳුම්(costume) වෙනස් කරන්න, එවිට වර්ණ හතරට sprite එක බැගින් ඇත.
+ රතු(red), නිල්(blue), කොළ(green) සහ කහ(yellow) යන වර්ණ ඇඳුම්(costume): අනුපිළිවෙලටම sprites වේදිකා මත තබන්න

![තිර රුව(screenshot)](images/colour-drums.png) \--- /task \---

\--- task \--- රතු(red) sprite එක මත ක්ලික් කළ විට එය 'රතු'('red') පණිවිඩයක්(message එකක්) sprite: චරිතයට(character sprite එකට), `විකාශනය(broadcasts)`{:class="block3events"} කරන පරිදි, එයට කේතයක්(code එකක්) එක් කරන්න

![red-drum](images/red_drum.png)

```blocks3
    when this sprite clicked
    broadcast (red v)
```

\--- /task \---

`විකාශනයක්(broadcast)`{:class="block3events"} යනු ශබ්ද විකාශන යන්ත්‍රයක් හරහා විකාශනය කරන පණිවිඩයකට සමානය දෙයකි, එය ඔබට පාසැල්වල හෝ සුපිරි වෙළඳසැල්වල ඇසෙන විකාශන වලට සමාන වේ. සියලුම sprite වලට `විකාශනය(broadcast)`{:class="block3events"} ඇසෙනු ඇත, නමුත් ප්‍රතිචාර දැක්විය හැක්කේ ප්‍රතිචාර දැක්විය යුතු sprite පමණි.

\--- task \---

නිල්(blue), කොළ(green) සහ කහ(yellow) sprite මගින් ඔවුන්ගේම වර්ණය පිළිබඳ පණිවිඩ `විකාශනය(broadcast)`{:class="block3events"} කරවීමට, පෙර මෙන් සමාන කේත(code) එක් කරන්න.

\--- /task \---

`විකාශනය(broadcast)`{:class="block3events"}, ශබ්ද විකාශන පණිවිඩයකට සමාන බව ඔබට මතකද? `විකාශනයට(broadcast)`{:class="block3events"} පණිවිඩයට(message එකට) ප්‍රතිචාර දැක්වීම චරිත(character) sprite ගේ කාර්යය බවට පත් කිරීම සඳහා ඔබ එයට කේතයක්(code එකක්) එක් කරනු ඇත.

\--- task \---

ඔබේ sprite චරිතයට `රතු(red)`{:class="block3events"} පණිවිඩය(message එක) ලැබුණු විට, කේතය(code එක) මගින් අංක `1` `අනුක්‍රමය(sequence එකේ)`{:class="block3variables"} ලැයිස්තුව(list) ආරම්භයේ ඇති දැයි පරීක්ෂා කළ යුතු අතර (එයින් අදහස් වන්නේ `රතු(red)`{:class="block3events"} යනු අනුක්‍රමයේ ඊළඟ වර්ණය බවයි).

`1` ලැයිස්තුව(list එක) ආරම්භයේ ඇත්නම්, කේතය(code එක) ලැයිස්තුවෙන්(list එකෙන්) අංකය ඉවත් කළ යුතුය, මන්ද ක්‍රීඩකයාට නිවැරදි වර්ණය මතක ඇති බැවිනි. එසේ නොමැතිනම් තරඟය අවසන් කළයුතු අතර කේතය(code එක) ක්‍රීඩාව අවසන් කිරීමට `සියල්ල නැවැත්විය යුතුය(stop all)`{:class="block3control"}.

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

\--- task \--- ඔබ දැන් ලියා ඇති කේතයට(code එකට) කේතයක් එක් කර, sprite චරිතයට නිවැරදි `විකාශනය(broadcast එක)` {:class="block3events"} ලැබුන විට බෙර පද(drum beat එක) වාදනය වන පරිදි සකසන්න.

\--- hints \--- \--- hint \--- එක් එක් වර්ණයට අනුරූප සංඛ්‍යා භාවිතා කර, ඒවාට අදාල නිවැරදි බෙර(drum) පද(beats) වාදනය කරවීම ඔබට කළ හැකිද?

+ 1 = red
+ 2 = blue
+ 3 = green
+ 4 = yellow \--- /hint \--- \--- hint \--- `අනුක්‍රම(sequence)`{:class="block3variables"} ලැයිස්තුවේ පළමු ශබ්දය වාදනය කිරීමට `අනුක්‍රමයේ 1 මකන්න(delete 1 of sequence)`{:class="block3variables"} කට්ටියට ඉහළින්, `බෙර වාදනය(play drum)`{:class="block3sound"} කට්ටිය එක් කරන්න. 

\--- /hint \--- \--- hint \--- ඔබ එකතු කළයුතු කේතය(code) මෙහි දැක්වේ:

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

\--- task \--- ඔබ ඔබේ sprite චරිතය සඳහා භාවිතා කළ කේතය(code එක) `රතු(red)`{:class="block3events"} පණිවිඩයට ප්‍රතිචාර දැක්වීමට හැකිවන පරිදි අනුපිටපත්(duplicate) කරන්න. `නිල්(blue)` {:class="block3events"} පණිවිඩය(message) යවන පරිදි, අනුපිටපත්(duplicate) කේතය(code එක) වෙනස් කරන්න. \--- /task \---

`නිල්(blue)`{:class="block3events"} යන පණිවිඩයට sprite ප්‍රතිචාර දක්වන විට, කුමන කේත(code) කොටස(bit) නොවෙනස්ව පැවතිය යුතුද, කුමන කේත(code) කොටස(bit) වෙනස් විය යුතුද? සෑම වර්ණයකටම අනුරූප(corresponding) අංකයක් ඇති බව මතක තබා ගන්න.

\--- task \--- `නිල්(blue)`{:class="block3events"} පාට පණිවිඩයට නිවැරදිව ප්‍රතිචාර දක්වනපරිදි sprite චරිතයේ කේතය(code එක) වෙනස් කරන්න. 

\--- hints \--- \--- hint \---

මෙම කට්ටි(blocks) තබා ගන්න, නමුත් ඔබ ඒවා යම් යම් ආකාරයෙන් වෙනස් කළ යුතුවේ:

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

\--- /hint \--- \--- hint \--- ඔබේ කේතය(code එක) `නිල්`{:class="block3events"} විකාශනය(broadcast) සෙවිය යුත්තේ මේ ආකාරයටයි.

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

\--- කාර්යය \--- කේතය දෙවරක් අනුපිටපත්(Duplicate) කරන්න (කොළ සහ කහ බොත්තම් වලට යෙදීම සඳහා), දැන් එහි අවශ්‍ය කොටස් වෙනස් කරන්න, එවිට චරිතය(character එක) නව `විකාශන(broadcasts)` {:class="block3events"} වලට නිවැරදිව ප්‍රතිචාර දක්වයි. \--- /task \---

කේතය(code එක) පරීක්ෂා(test) කිරීමට මතක තබා ගන්න! ඔබට වර්ණ පහක අනුක්‍රමයක් මතක තබාගත හැකිද? සෑම අවස්ථාවකම අනුක්‍රමය(sequence එක) වෙනස් වන්නේද?

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