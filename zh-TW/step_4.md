## 重複序列

現在，您將添加四個按鈕，玩家必須按下才能重複顏色序列。

\--- task \---

Add four new sprites to your project to represent the four buttons.

+ 編輯新精靈的服裝，以便四種顏色中的每一種都有一個精靈
+ 將精靈放在舞台上的順序與服裝相同：紅色，藍色，綠色，黃色

![screenshot](images/colour-drums.png)

\--- /task \---

\--- task \---

Add code to the red sprite so that, when the sprite is clicked, it `broadcasts`{:class="block3events"} a 'red' message to the character sprite:

![red-drum](images/red_drum.png)

```blocks3
    當這個精靈點擊
    廣播（紅色v）
```

\--- /task \---

A `broadcast`{:class="block3events"} is like a message announced over a loudspeaker, which you can for example hear in schools or supermarkets. All of the sprites can hear the `broadcast`{:class="block3events"}, but only the sprite whose job it is to respond will do something.

\--- task \---

Add similar code to the blue, green, and yellow sprites to make them `broadcast`{:class="block3events"} messages about their own colour.

\--- /task \---

Do you remember that the `broadcast`{:class="block3events"} is like a loudspeaker message? You will add code to make it the character sprite's job to respond to the `broadcast`{:class="block3events"} messages.

\--- task \---

When your character sprite receives the message `red`{:class="block3events"}, the code should check whether the number `1` is at the start of the `sequence`{:class="block3variables"} list (which means that `red`{:class="block3events"} is the next colour in the sequence).

If `1` is at the start of the list, the code should remove the number from the list, because the player remembered the correct colour. Otherwise it's game over, and the code needs to `stop all`{:class="block3control"} to end the game.

![ballerina](images/ballerina.png)

```blocks3
當我收到[red v]
if <（[sequence v]的項目（1 v））=[1]> 然後
刪除（1 v）[sequence v]
else
說[Game over！] for（1）秒
停止[全v]
結束
```

\--- /task \---

\--- task \---

Add to the code you just wrote so that a drum beat also plays when the character sprite receives the correct `broadcast`{:class="block3events"}.

\--- hints \---

\--- hint \---

Can you use the numbers that correspond to each colour to play the correct drum beat?

+ 1 =紅色
+ 2 =藍色
+ 3 =綠色
+ 4 = yellow

\--- /hint \---

\--- hint \---

Above the `delete 1 of sequence`{:class="block3variables"} block, add the `play drum`{:class="block3sound"} block to play the first sound in the `sequence`{:class="block3variables"} list.

\--- /hint \---

\--- hint \---

Here is the code you will need to add:

```blocks3
當我收到[紅色v]
如果 <（[序列v]的項目（1 v））=[1]> 然後

+播放鼓（\（1 \）Snare Drum v）for（0.25）beats
delete（1 v ）[序列v]
其他
說[遊戲結束！]為（1）秒
停止[全v]
結束
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code you used to make your character sprite respond to the message `red`{:class="block3events"}. Change the duplicated code so that it sends the message `blue`{:class="block3events"}.

\--- /task \---

When the sprite responds to the message `blue`{:class="block3events"}, which bit of code should stay the same, and which bit should change? Remember that each colour has a corresponding number.

\--- task \---

Change the character sprite's code so that the character responds correctly to the `blue`{:class="block3events"} message.

\--- hints \---

\--- hint \---

Keep these blocks, but you need to change them in some way:

![ballerina](images/ballerina.png)

```blocks3
<（[序列v]的項目（1 v））= [1]>

當我收到[red v]

play drum（\（1 \）Snare Drum v）for（0.25）beats
```

\--- /hint \---

\--- hint \---

Here is how your code should look for the `blue`{:class="block3events"} broadcast.

![ballerina](images/ballerina.png)

```blocks3
當我收到[藍色v]
如果 <（[序列v]的項目（1 v））=[2]> 然後
    播放鼓（\（2 \）Bass Drum v）for（0.25）beats
    delete（1 v） [序列v]
其他
    說[遊戲結束！]為（1）秒
    停止[全v]
結束
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Duplicate the code again twice (for the green and yellow buttons), and change the necessary parts so that the character responds correctly to the new `broadcasts`{:class="block3events"}.

\--- /task \---

Remember to test the code! Can you memorise a sequence of five colours? Is the sequence different each time?

When the player repeats the whole colour sequence correctly, the `sequence`{:class="block3variables"} list emtpy and the player wins. If you want, you can also display some flashing lights as a reward once the `sequence`{:class="block3variables"} list is empty.

\--- task \---

Add this code to the end of your character's `when flag clicked`{:class="block3events"} script:

![ballerina](images/ballerina.png)

```blocks3
    等到 < （[序列v]的長度）= [0]>
    廣播（贏了v）並等待
```

\--- /task \---

\--- task \---

Switch to the Stage, and import the `drum machine` sound or another sound you like.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \---

Add this code to play a sound and make the backdrop change colour when the player wins.

![ballerina](images/stage.png)

```blocks3
    當我收到[won v]
    開始聲音（鼓機v）
    重複（50）
        改變[color v]效果（25）
        等待（0.1）秒
    結束
    清除圖形效果
```

\--- /task \---