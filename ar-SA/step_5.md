## مستويات متعددة

حتى الآن، على اللاعب أن يتذكر فقط تسلسل من خمسة ألوان. يمكنك القيام بتحسين لعبتك بإضافة درجة، و ذلك عن طريق إضافة تعليمات برمجية بحيث كلما أحرز اللاعب درجة أعلى ينتقل إلى مرحلة تالية يكون فيها تسلسل الألوان المطلوب تذكره أطول من المرحلة السابقة.

\--- task \---

Create a new variable called `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \---

Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`.

\--- /task \---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \---

Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
repeat (score :: variables)
end
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
غيِّر [score v] بمقدار (1)
```

\--- hints \---

\--- hint \---

You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks3
عند نقر ⚑ :: events
اجعل [الدرجة v] مساويًا [3] :: variables
كرر باستمرار 
  احذف (الكل v) من [تسلسل v] :: list
  كرِّر (الدرجة) مرة 
    أضف (اختر عددًا عشوائيًا بين (1) و (4) :: operators) إلى [تسلسل v] :: list
    غيّر المظهر إلى (العنصر (طول [تسلسل v] :: list) من [تسلسل v] :: list) :: looks
    انتظر (1) ثانية :: control :: control
  end
  انتظر حتى <(طول [تسلسل v] :: list) = [0] :: operators> :: control
  بث (فزت! v) وانتظر :: events
  غيِّر [الدرجة v] بمقدار (1) :: variables :: control
end
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---