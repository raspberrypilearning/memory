## 添加音效

--- task ---

在你測試專案時，有沒有注意到，在相同數字連續出現兩次以上時，就看不出造型的更換了？

--- /task ---

那麼，我們在角色改變造型時帶個音效怎麼樣？用「鼓」來試試？

--- task ---

為專案加入「音樂」擴展，這樣你就能利用`演奏節拍`{:class="block3extensions"} 積木上的鼓聲了。

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

用不同的鼓演奏節拍，和讓角色變換不同造型，兩者的程式**非常相似**。

--- hints ---

--- hint ---

你只需要再加上兩個積木：`演奏節拍 (0.25) 拍`{:class="block3sound"}還有`(序列)的第(序列長度)項`{:class="block3variables"}。

--- /hint ---

--- hint ---

這裡是你需要的程式積木：

![芭蕾舞者](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

--- /hint ---

--- hint ---

你的程式看起來應該會像這樣：

![芭蕾舞者](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
	add (pick random (1) to (4)) to [sequence v]
    play drum (item (length of [sequence v]) of [sequence v]) for (0.25) beats
    switch costume to (item (length of [sequence v]) of [sequence v])
    wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---