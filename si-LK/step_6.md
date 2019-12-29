## වැඩිම(high) ලකුණු(score)

දැන් ඔබේ මිතුරන්ට එරෙහිව ක්‍රීඩා කිරීමට හැකි වන පරිදි, ඔබ ලබාගත් වැඩිම(high) ලකුණු(score එක) සුරැකුම(save) කරන්න.

\--- task \--- `වැඩිම ලකුණු(high score)` {:class="block3variables"} සහ `නම(name)`{:class="block3variables"} ලෙස නව(new) විචල්‍ය(variables) දෙකක් ඔබේ ව්‍යාපෘතියට එක් කර. \--- /task \---

ක්‍රීඩකයා විසින් අනුක්‍රමය වැරදියට ලබාදීම නිසා ක්‍රීඩාව අවසන් වන විට, ක්‍රීඩකයාට වත්මන් ඉහළම ලකුණු(high score) සංඛ්‍යාවට වඩා වැඩි ලකුණු ඇත් දැයි පරීක්ෂා කළ යුතුය. එය එසේ නම්, එම ලකුණු සංඛ්‍යාව ක්‍රීඩාවේ ඉහළම ලකුණු(high score එක) ලෙස සුරැකුම්(save) කළ යුතු අතර ක්‍රීඩකයාගේ නමද සුරැකුම්(save) කළ යුතුය.

\--- task \--- `ඉහළම ලකුණු(high score එක)`{:class="block3variables"} සුරැකුම කිරීම සඳහා ඔබේ sprite චරිතය වෙත කේතයක්(code එකක්) එක් කරන්න. ක්‍රීඩකයාගේ නම විමසා එය `නම(name)`{:class="block3variables"} යන විචල්‍යයේ සුරැකුම(save) කරන්න.

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- ඔබේ නව(new) කේතය(code) මෙම රටාව(pattern එක) අනුගමනය කළ යුතුයි:

`ක්‍රීඩාව අවසන්(Game over)`{:class="block3looks"} පණිවුඩයට(message එකට) පසුව ලබාගත් `ලකුණු(score)`{:class="block3variables"} සංඛ්‍යාව `වැඩිම ලකුණු(high score)`{:class="block3variables"} වලට `වඩා වැඩි(greater than)`{:class="block3operators"} `නම්(If)`{:class="block3control"} `ලකුණු`{:class="block3variables"} `වැඩිම ලකුණු(high score)`{:class="block3variables"} විචල්‍යට `ස්ථාපනය(Set)`{:class="block3variables"} කරන්න. ක්‍රීඩකයාගේ නම `විමසා(Ask)`{:class="block3sensing"} `පිළිතුර(answer)`{:class="block3sensing"} `නම(name)`{:class="block3variables"} නම් විචල්‍යට `ස්ථාපනය(Set)`{:class="block3variables"} කරන්න. \--- /hint \--- \--- hint \---

ඔබට පහත ඇති කට්ටි(blocks) අවශ්‍ය වේවි:

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

\--- /hint \--- \--- hint \--- රතු(red) බොත්තම(button එක) එබූ විට, ඔබේ කේතය(code එක) මෙවැනි එකක් වියයුතුයි:

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

\--- /hint \--- \--- /hints \--- \--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

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

If you need to change any of the 'Game over' code, for example to add a sound or change the 'Game over' message, you have to change it four times. That's annoying and wastes a lot of time.

Instead, you can define your own code block, and use it anywhere in your project.

\--- task \--- Click on `My blocks`{:class="block3myblocks"}, and then on **Make a Block**. Call this new block `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \--- Add the code from the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast to the `Game over`{:class="block3myblocks"} block so that it looks like this:

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

\--- /task \---

\--- task \--- Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

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

\--- /task \---

\--- task \--- Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence. \--- /task \---

Your new `Game over`{:class="block3myblocks"} block is a **function**, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="block3myblocks"} block in.

\--- task \--- Also replace the code in the `else`{:class="block3control"} block connected to the `broadcasts`{:class="block3events"} for the other colours with your new `Game over`{:class="block3myblocks"} block. Here is what the code for the `blue`{:class="block3events"} message should look like

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

\--- /task \---

\--- task \--- Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

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

\--- /task \---