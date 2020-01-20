## 高分

現在保存高分，以便您可以與朋友對戰。

\--- task \---

Add two new variables called `high score`{:class="block3variables"} and `name`{:class="block3variables"} to your project.

\--- /task \---

When the game ends because the player gets the sequence wrong, the game should check whether the score is higher than the current high score. If it is, the game should save the score as the high score, and also store the name of the player.

\--- task \---

Add code to your character sprite to store the `high score`{:class="block3variables"}. Also ask for the player's name, and store it in the `name`{:class="block3variables"} variable.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Your new code needs to follow this pattern:

After the `Game over`{:class="block3looks"} message `If`{:class="block3control"} the `score`{:class="block3variables"} is `greater than`{:class="block3operators"} the `high score`{:class="block3variables"} `Set`{:class="block3variables"} the `high score`{:class="block3variables"} to the `score`{:class="block3variables"} `Ask`{:class="block3sensing"} for the player's name `Set`{:class="block3variables"} the `name`{:class="block3variables"} to the `answer`{:class="block3sensing"}

\--- /hint \---

\--- hint \---

You need the following blocks:

![ballerina](images/ballerina.png)

```blocks3
如果 < > 則
結束

（得分）

（得分）

[] > []

回答

（高分）

問[你的名字是什麼？]並等待

套[高分v]至[] 

套[名稱v]到[] 
```

\--- /hint \---

\--- hint \---

Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

```blocks3
當我收到[紅色v]
如果 <（[序列v]的項目（1 v））=[1]> 那麼
    播放鼓（[序列v]的項目（1 v））為（0.25）節拍
    刪除（1 v）[sequence v]
else
    說[Game over！] for（1）seconds
    if < （score :: variables） > （high score） > then
        set [high score v] to（score :: variables） ）
        問[高分！ 你的名字是什麼？]並等待
        集[名字v]到（回答）
    結束
    停止[全v]
結束
```

\--- /hint \---

\--- /hints \---

\--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks3
說[遊戲結束！]為（1）秒
如果 < （得分::變量） > （高分） > 然後
    設置[高分v]到（得分::變量）
    問[高分！ 你的名字是什麼？]並等待
    集[名字v]到（回答）
結束
停止[全部v]
```

If you need to change any of the 'Game over' code, for example to add a sound or change the 'Game over' message, you have to change it four times. That's annoying and wastes a lot of time.

Instead, you can define your own code block, and use it anywhere in your project.

\--- task \---

Click on `My blocks`{:class="block3myblocks"}, and then on **Make a Block**. Call this new block `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Add the code from the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast to the `Game over`{:class="block3myblocks"} block so that it looks like this:

![ballerina](images/ballerina.png)

```blocks3
定義遊戲超過
說[遊戲結束！]為（1）秒
如果 < （得分::變量） > （高分） > 然後
    設置[高分v]到（得分::變量）
    問[高分] ！ 你的名字是什麼？]並等待
    集[名字v]到（回答）
結束
停止[全部v]
```

\--- /task \---

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks3
當我收到[紅色v]
如果 <（[序列v]的項目（1 v））=[1]> 則
    播放鼓（\（1 \）Snare Drum v）for（0.25）beats
    delete（1 v） [序列v]
其他
    遊戲結束::自定義
結束
```

\--- /task \---

\--- task \---

Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence.

\--- /task \---

Your new `Game over`{:class="block3myblocks"} block is a **function**, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="block3myblocks"} block in.

\--- task \---

Also replace the code in the `else`{:class="block3control"} block connected to the `broadcasts`{:class="block3events"} for the other colours with your new `Game over`{:class="block3myblocks"} block. Here is what the code for the `blue`{:class="block3events"} message should look like

![ballerina](images/ballerina.png)

```blocks3
當我收到[藍色v]
如果 <（[序列v]的項目（1 v））=[1]> 然後
    播放鼓（\（2 \）Bass Drum v）for（0.25）beats
    delete（1 v） [序列v]
其他
    遊戲結束::自定義
結束
```

\--- /task \---

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks3
定義遊戲超過
開始聲音[Cough1 v]
說[遊戲結束！]為（1）秒
如果 < （得分::變量） > （高分） > 然後
    播放聲音（trumpet1 v）
    集[高分] v]到（得分）
    問[高分！ 你的名字是什麼？]並等待
    集[名字v]到（回答）
結束
停止[全部v]
```

\--- /task \---