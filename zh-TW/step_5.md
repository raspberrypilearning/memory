## 多個級別

到目前為止，玩家只需要記住五種顏色的序列。 通過添加分數和添加代碼來改善您的遊戲，以便當玩家得分時，遊戲移動到下一級別並且要記住的顏色序列變得更長。

\--- task \--- 創建一個名為 `score`{：class =“block3variables”}的新變量。

[[[generic-scratch3-add-variable]]] \--- /任務\---

基於 `得分`{：class =“block3variables”}，遊戲將決定顏色序列的長度。以分數（和序列長度） `3`。

\--- task \--- 當標記點擊</code>{：class =“block3events”}代碼時，在角色 `的開頭添加一個塊，將 <code>得分`{：class =“block3variables”}設置為 `3`。 \--- /任務\---

您現在希望 `得分`{：class =“block3variables”}來確定序列長度，而不是始終創建五種顏色的序列。

\--- task \--- 更改角色的 `重複`{：class =“block3control”}循環（用於創建顏色序列）以重複 `分`{：class =“block3variables”}次：

![精靈](images/ballerina.png)

```blocks3
repeat（score :: variables）
結束
```

\--- /任務\---

\--- task \--- 如果玩家重複正確的序列，你應該添加 `1` 到 `得分`{：class =“block3variables”}，這樣做會增加下一個序列的長度。 在您知道序列正確的位置將以下塊添加到字符的代碼 ****：

![精靈](images/ballerina.png)

```blocks3
通過（1）改變[得分v]
```

\---提示\--- \---提示\--- 當遊戲 `廣播`{：class =“block3events”}'win'消息時，你知道序列是正確的。 \--- /提示\--- \--- /提示\---

\--- /任務\---

\--- task \--- 最後，在生成序列的代碼周圍添加 `永久`{：class =“block3control”}循環，以便遊戲為每個級別創建一個新的顏色序列。 這是您的角色代碼的外觀：

![芭蕾舞演員](images/ballerina.png)

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

\--- /任務\---

\---任務\--- 讓你的朋友測試你的遊戲。記得在播放之前隱藏 `序列`{：class =“block3variables”}列表！ \--- /任務\---