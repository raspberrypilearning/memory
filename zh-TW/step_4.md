## 找出顏色序列

現在，你將加入四個顏色按鈕，玩家在記住角色的顏色更換順序後，要依照序列按下顏色按鈕才算成功。

--- task ---

加入四個新的角色到專案，代表四個按鈕。

+ 編輯新角色的造型，把四個圖像的主要顏色分別換成要記憶的四個顏色。
+ 把角色放到舞台，擺放順序和顏色序列一致：紅色、藍色、綠色、黃色。

![截圖](images/colour-drums.png)

--- /task ---

--- task ---

為紅色按鈕角色編寫程式，在點擊角色時`廣播`{:class="block3events"}訊息「紅色」給其它角色：

![紅色的鼓](images/red_drum.png)

```blocks3
when this sprite clicked
broadcast (紅色 v)
```

--- /task ---

`廣播`{:class="block3events"}就好像現實生活中，有人拿著大聲公說話，在場的人都聽得到這個訊息，比方說學校的廣播、市場的廣播。 所有角色都「聽」得到這個`廣播`{:class="block3events"}，不過，你可以設定哪個角色要對哪種訊息有反應。

--- task ---

為藍色、綠色、黃色的角色編寫類似的程式，讓各自`廣播`{:class="block3events"}自己的顏色訊息。

--- /task ---

記得`廣播`{:class="block3events"}就像大聲公吧？ 你還要在角色加入一些程式，讓它對`廣播`{:class="block3events"}的訊息有反應。

--- task ---

當你的角色收到`紅色`{:class="block3events"}這個訊息，要檢查所代表的數字 `1` 是不是和目前`序列`{:class="block3variables"}中的第一個項目所列的顏色代表數字一樣是`紅色`{:class="block3events"}。

如果清單的第一項是 `1`，表示玩家答對，程式會把這個項目刪除，以便玩家回覆序列的下一個答案。 如果玩家答錯，程式會`全部停止`{:class="block3control"}，表示遊戲結束。

![芭蕾舞者](images/ballerina.png)

```blocks3
when I receive [紅色 v]
if <(item (1 v) of [sequence v])=[1]> then
delete (1 v) of [sequence v]
else
say [遊戲結束!] for (1) seconds
stop [all v]
end
```

--- /task ---

--- task ---

在你剛編寫的程式裡也加入演奏節拍，這樣一來，`當角色收到的訊息`{:class="block3events"}是正確時，就會聽到音效。

--- hints ---

--- hint ---

你能為每個顏色演奏對應的鼓聲嗎？

+ 1 = 紅色
+ 2 = 藍色
+ 3 = 綠色
+ 4 = 黃色

--- /hint ---

--- hint ---

在`刪除序列的第 1 項`{:class="block3variables"}積木上方，添加`演奏節拍`{:class="block3sound"}積木， 這樣一來所演奏的音樂就會和清單中的`序列`{:class="block3variables"}一致。

--- /hint ---

--- hint ---

這是你需要添加的程式：

```blocks3
when I receive [紅色 v]
if <(item (1 v) of [sequence v])=[1]> then
+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sequence v]
else
say [遊戲結束!] for (1) seconds
stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

複製角色收到`紅色`{:class="block3events"}訊息的事件程式。 修改複製出來的積木，把它改成收到`藍色`{:class="block3events"}訊息時的反應。

--- /task ---

當角色收到`藍色`{:class="block3events"}訊息的程式中，哪些是保持不變的，哪些又是應該修改的呢？ 要注意的是，不同的數字對應了不同的顏色。

--- task ---

修改角色的程式，讓角色對`藍色`{:class="block3events"}訊息有正確的反應。

--- hints ---

--- hint ---

你需要修改這些積木的部分內容：

![芭蕾舞者](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [紅色 v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

--- /hint ---

--- hint ---

收到`藍色`{:class="block3events"}訊息時的程式應該會像這樣：

![芭蕾舞者](images/ballerina.png)

```blocks3
when I receive [藍色 v]
if <(item (1 v) of [sequence v])=[2]> then
	play drum (\(2\) Bass Drum v) for (0.25) beats
	delete (1 v) of [sequence v]
else
	say [遊戲結束!] for (1) seconds
	stop [all v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

再複製出兩段程式，用來回應綠色、黃色按鈕的廣播，記得要修改必要的部分，這樣角色才能夠對`廣播`{:class="block3events"}事件有正確的反應。

--- /task ---

記得要測試程式！你能記得住五個顏色的序列嗎？每次顏色的排列順序是不是不一樣？

當玩家正確回答出顏色的排列順序，就把`序列`{:class="block3variables"}清空，同時慶祝玩家成功。 怎麼慶祝呢？在`序列`{:class="block3variables"}清空後，可以廣播告訴舞台，讓舞台的燈光閃爍。

--- task ---

把這個程式安排到`點擊綠旗`{:class="block3events"}之後：

![芭蕾舞者](images/ballerina.png)

```blocks3
wait until < (length of [sequence v]) = [0]>
broadcast (成功 v) and wait
```

--- /task ---

--- task ---

切換到舞台的程式頁籤，播放你喜歡的音效，比方說範例庫中的音效 `Drum Machine`。

[[[generic-scratch3-sound-from-library]]]

--- /task ---

--- task ---

在舞台上編寫這個程式，玩家在記憶成功時，就會有慶祝音樂，同時背景圖像的顏色也會改變（看來就像燈光在閃爍）。

![芭蕾舞者](images/stage.png)

```blocks3
when I receive [成功 v]
start sound (drum machine v)
repeat (50)
	change [color v] effect by (25)
	wait (0.1) seconds
end
clear graphic effects
```

--- /task ---