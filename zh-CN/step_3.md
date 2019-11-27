## 添加音效

\--- task \---

测试你的项目几次。您是否注意到，有时同一个数字在一行中被选择两次（或更多），这会使序列难以记忆？

\--- /task \---

每次角色精灵改变服装时，你能使程序发出鼓声吗？每种颜色的鼓声怎么样？

\--- task \---

将音乐扩展添加到你的项目中，以便您可以使用`播放鼓声`{:class="block3extensions"} 模块。

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

播放鼓声的代码 **非常**类似于改变角色服装的代码。

\--- hints \--- \--- hint \--- 你只需要添加两个块：一个 `击打鼓(0.25) 拍`{:class="block3sound"} 和`序列的第(序列的项目数)项`{:class="block3variables"}。 \--- /hint \--- \--- hint \---

以下是你需要的代码块：

![ballerina](images/ballerina.png)

```blocks3
play drum (\(1\) Snare Drum v) for (0.25) beats

(item (length of [sequence v]) of [sequence v])
```

\--- /hint \---

\--- hint \--- 你完成的代码应该像下面这样：

![ballerina](images/ballerina.png)

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

\--- /hint \---

\--- /hints \---

\--- /task \---