## 多個關卡

目前為止，玩家固定要記住五個顏色的排列順序。 加入一些東西可以讓這個機制有變化，比方說，在玩家成功時得分，然後遊戲進入下一關，要記住的顏色序列變得更多。

--- task ---

建立一個新的變數，名稱叫`得分`{:class="block3variables"}。

[[[generic-scratch3-add-variable]]]

--- /task ---

我們用`得分`{:class="block3variables"}作為顏色數量的依據。遊戲一開始，我們把得分設為 `3`，也就是玩家一開始要記住的數量是 3 個顏色。

--- task ---

在角色中加入程式，使得在`點擊綠旗`後，`得分`{:class="block3variables"}設為 `3`。

--- /task ---

現在我們不再用固定的五個顏色的序列，取而代之，我們依據`得分`{:class="block3variables"}決定顏色序列的長度。

--- task ---

修改角色上用來創建顏色序列的`重複`{:class="block3control"}迴圈，改成重複`得分`{:class="block3variables"}次：

![角色](images/ballerina.png)

```blocks3
repeat (得分 :: variables)
end
```

--- /task ---

--- task ---

如果玩家能正確找出顏色序列，`得分`{:class="block3variables"}就多 `1` 分，那麼，下次序列的長度也會跟著增加。 在**當你知道序列為正確**之後添加以下程式：

![角色](images/ballerina.png)

```blocks3
change [得分 v] by (1)
```

--- hints ---

--- hint ---

想不到要寫在哪嗎？把程式寫在`廣播訊息成功並等待`{:class="block3events"} 之後。

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

最後，在建立序列的這個程式外添加`重複無限次`{:class="block3control"}迴圈，這樣一來，玩家每次成功時，就會不斷的往下一個關卡邁進。 你的程式看起來會像這樣：

![芭蕾舞者](images/ballerina.png)

```blocks3
when flag clicked
set [得分 v] to [3]
forever
	delete (all v) of [sequence v]
	repeat (得分)
		add (pick random (1) to (4)) to [sequence v]
		switch costume to (item (length of [sequence v]) of [sequence v]
		wait (1) seconds
	end
	wait until < (length of [sequence v]) = [0]>
	broadcast (成功 v) and wait
	change [得分 v] by (1)
end
```

--- /task ---

--- task ---

邀請朋友測試你的遊戲，別忘了，先把`序列`{:class="block3variables"}清單隱藏起來，不然答案都被朋友看光光了！

--- /task ---