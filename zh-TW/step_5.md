## 多個級別

到目前為止，玩家只需要記住五種顏色的序列。 通過添加分數和添加代碼來改善您的遊戲，以便當玩家得分時，遊戲移動到下一級別並且要記住的顏色序列變得更長。

\--- task \---

Create a new variable called `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \---

Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`.

\--- /任務\---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \---

Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
repeat（score :: variables）
結束
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
通過（1）改變[得分v]
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
當標誌點擊
設置[得分v]到 [3]
永遠
    刪除（所有v）[序列v]
    重複（得分）
        加（選擇隨機（1）到（4））到[序列v]
        開關服裝至（序列v的項目（[序列v]的長度）
        等待（1）秒
    結束
    等待 < （[序列v]的長度）= [0]>
    廣播（贏得v）並等待
    改變[得分v]由（1）
結束
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---