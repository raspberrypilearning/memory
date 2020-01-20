## 添加聲音

\---任務\---

幾次測試你的項目。您是否注意到有時連續兩次（或更多次）選擇相同的數字，這會使序列難以記憶？

\--- /任務\---

每次角色精靈改變服裝時，你能發出鼓聲嗎？每種顏色的鼓聲怎麼樣？

\---任務\---

將音樂擴展添加到項目中，以便您可以使用 `play drum`{：class =“block3extensions”}塊。

[[[generic-scratch3-add-music-extension]]]

\--- /任務\---

\---任務\---

播放鼓的代碼是 **非常** 相似改變人物的服裝的代碼。

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /提示\---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
播放鼓（\（1 \）Snare Drum v）for（0.25）beats

（[sequence v]的項目（[sequence v]的長度））
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

```blocks3
當標記點擊時
刪除（所有v）[序列v]
重複（5）
    添加（選擇隨機（1）到（4））到[序列v]
    播放鼓（項目（[序列v]的長度） [序列v]的[0.25]節拍
    開關服裝到[序列v]的項目（[序列v]的長度）
    等待（1）秒
結束
```

\--- /hint \---

\--- /hints \---

\--- /task \---