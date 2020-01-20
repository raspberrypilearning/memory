## 複数レベル

これまでのところ、プレーヤーは5色のシーケンスを覚えているだけです。 スコアを追加し、プレーヤーがポイントを獲得したときにゲームが次のレベルに移動し、記憶するカラーシーケンスが長くなるようにコードを追加して、ゲームを向上させます。

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
(スコア :: 変数) 回繰り返す
終了
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
[スコア v] を(1) で変更
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
フラグが押されたとき
[スコア v] を [3] に設定
永久
    [シーケンス v] の(すべて v) を削除
    (スコア) を繰り返す
        [シーケンス v] に((1) から(4) の間の乱数) を加える
        ([シーケンス v] の([シーケンスv] の長さ) 番目にコスチュームを切り替えるする
        (1) 秒待つ
    終了
 <  ([シーケンス v] の長さ) = [0] > まで待つ
    (勝ち v) を送って待つ
    [スコア v] を(1) ずつ変える
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---