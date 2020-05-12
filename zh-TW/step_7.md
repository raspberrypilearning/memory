## 挑戰：遊戲改良

### 建立更多函式積木

觀察看看，四個顏色按鈕的其它代碼有沒有相似的地方？

```blocks3
when I receive [紅色 v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(1\) Snare Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	遊戲結束 :: custom
end

when I receive [藍色 v]
if <(item (1 v) of [sequence v])=[1]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	遊戲結束 :: custom
end
```

你能建立另一種所有按鈕都可以通用的函式積木嗎？

### 遊戲前後的造型

你發現了嗎？每次遊戲開始，角色會隨機顯示對應顏色的造型，但最後一個顏色根本不需要記，因為舞台上的角色已經顯示了。

也許你可以讓角色多一個白色的造型，寫個程式，讓角色在開始遊戲前，還有變換完造型後，都顯示這個白色的造型。

![截圖](images/colour-white.png)

### 遊戲的難度選擇

讓不同程度的玩家能享受你的遊戲，比方說，玩家可以選擇簡單模式（只記紅色和藍色）還有普通模式（記三個顏色）…等。

如果你有記憶力超強的朋友，為他加設「硬漢」模式，用五個顏色的序列殺光他的腦細胞！