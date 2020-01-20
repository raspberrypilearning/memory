## ハイスコア

ハイスコアを保存して、友達と対戦できるようにしましょう。

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
もし < > なら
終了

(スコア)

(スコア)

[ ] > [ ]

答え

(ハイスコア)

[あなたの名前は何ですか] と聞いて、

[ハイスコア v] を[ ] にする

[名前 v] を[ ] にする 
```

\--- /hint \---

\--- hint \---

Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

```blocks3
[赤 v] を受け取ったとき
もし < ([シーケンス v] の(1 v) 番目)=[1] > なら
    ([シーケンス v] の(1 v) 番目) ドラムを(0.25) 拍鳴らす
    [シーケンス v] の(1 v) 番目を削除する
でなければ
    [ゲームオーバー！] と(1) 秒間言う
　もし < (スコア:: 変数) > (ハイスコア) > なら
        [ハイスコア v] を(スコア:: 変数) にセットします
        [ハイスコア！ あなたの名前は何ですか？] 聞いて待っ
        [名前 v] を(答え) にする
    終了
    [すべて v] を止める
終了
```

\--- /hint \---

\--- /hints \---

\--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks3
[ゲームオーバー！] と(1) 秒間言う
もし < (スコア:: 変数) > (ハイスコア) > なら
    [ハイスコアV] を(スコア:: 変数) にする
    [ハイスコア！ あなたの名前は何ですか？] と聞いて待っ
    [名前 v] を(答え) にする
終了
[すべて v] を止める
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
定義ゲームオーバー
[ゲームオーバー！] と(1) 秒言う
もし < (スコア:: 変数) > (ハイスコア) > なら
    [ハイスコア v] を(スコア:: 変数) にする
    [ハイスコア！ あなたの名前は何ですか？] と聞いて待っ
    [名前 v] を(答え) にする
終了
[すべて v] を止める
```

\--- /task \---

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks3
[赤 v] を受け取ったとき
もし < ([シーケンス v] の(1 v) 番目) =[1] > なら
    (\(1\) スネアドラム v) ドラムを(0.25) 拍鳴らす
    [シーケンス v] の(1 v) を削除する 
でなければ
    ゲームオーバー:: カスタム
終了
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
[青 v] を受信したとき
もし < ([シーケンス v] の(1 v) 番目) =[1] > なら
    (\(2\) バスドラム v) ドラムを(0.25) 拍鳴らす
    [シーケンス v] の(1 v) を削除する
でなければ
    ゲームオーバー:: カスタム
終了
```

\--- /task \---

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks3
定義ゲームオーバー
[せき v] の音を鳴らす
[ゲームオーバー！] と(1) 秒言う
もし < (スコア:: 変数) > (ハイスコア) > なら
    (トランペット v) の音を鳴らす
    [ハイスコア v] を(スコア) にする
    [ハイスコア！ あなたの名前は何ですか？] と聞いて待っ
    [名前 v] を(答え) にする
終了
[すべて v] を止める
```

\--- /task \---