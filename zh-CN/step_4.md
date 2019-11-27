## 重复顺序

现在，您将添加四个按钮，玩家必须按下才能重复颜色序列。

\--- task \--- 在项目中添加四个新精灵来表示四个按钮。

+ 编辑新精灵的服装，以便四种颜色中的每一种都有一个精灵
+ 将精灵放在舞台上的顺序与服装相同：红色，蓝色，绿色，黄色

![screenshot](images/colour-drums.png) \--- /task \---

\--- task \--- 将代码添加到红色精灵中，以便在点击精灵时，该精灵能`广播` {：class =“block3events”}“红色”消息到角色精灵：

![red-drum](images/red_drum.png)

```blocks3
    when this sprite clicked
    broadcast (red v)
```

\--- /task \---

一个`广播/0>{:class="block3events"} 就像是通过扬声器宣布的消息，您可以在学校或超市中听到。 所有的精灵都可以听到 <code>广播`{:class="block3events"}, 但只有响应广播消息的精灵会做某些事情。

\--- task \---

添加类似的代码到蓝色，绿色和黄色精灵，使它们 `广播`{:class="block3events"}有关自己颜色的消息。

\--- /task \---

你还记得 `广播`{:class="block3events"}就像一个扬声器信息吗？ 您将添加代码以使其成为精灵的任务，以响应`广播`{:class="block3events"}消息。

\--- task \---

当你的精灵接收到 `红色`{:class="block3events"}信息时，代码应该检查数字 `1`是否在 `序列`{:class="block3variables"} 列表的开头(这意味着 `红色`{:class="block3events"}是序列中的下一个颜色)

如果 `1` 在列表的开头，代码应该从列表中删除数字，因为玩家记住了正确的颜色。 否则游戏结束，代码需要 `停止所有脚本`{:class="block3control"} 去结束游戏。

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end
```

\--- /task \---

\--- task \--- 添加到您刚编写的代码中，以便角色精灵收到正确的 `广播`{:class="block3events"}消息。

\--- hints \--- \--- hint \--- 你能使用与每种颜色相对应的数字来播放正确的鼓点吗？

+ 1 = 红色
+ 2 = 蓝色
+ 3 = 绿色
+ 4 =黄色 \--- /hint \--- \--- hint \--- 在 `删除序列的第1项`{:class="block3variables"} 代码中，添加 `击打鼓`{:class="block3sound"} 代码块去播放`序列`{:class="block3variables"} 列表的第一个声音。

\--- /hint \--- \--- hint \--- 下面是你需要添加的代码：

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then

+ play drum (\(1\) Snare Drum v) for (0.25) beats
delete (1 v) of [sequence v]
else
say [Game over!] for (1) seconds
stop [all v]
end

```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- 复制你用来使你的精灵响应 `红色`{:class="block3events"}信息的代码。 修改复制的代码使代码发送`蓝色`{:class="block3events"}信息。 \--- /task \---

当精灵响应 `蓝色`{:class="block3events"}消息时，哪一段代码应该保持不变，哪一段代码应该改变？ 请记住，每种颜色都有相应的数字。

\--- task \--- 更改精灵的代码，使精灵正确响应 `蓝色`{:class="block3events"} 消息。

\--- hints \--- \--- hint \---

保留这些块，但需要以某种方式改变它们：

![ballerina](images/ballerina.png)

```blocks3
<(item (1 v) of [sequence v]) = [1]>

when I receive [red v]

play drum (\(1\) Snare Drum v) for (0.25) beats
```

\--- /hint \--- \--- hint \--- 这里是你的代码应该如何接受`蓝色`{:class="block3events"}广播。

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[2]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    stop [all v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- 再次复制代码两次(对于绿色和黄色按钮)，并更改必要的部分，以便角色正确响应新的`广播`{:class="block3events"}。 \--- /task \---

记得测试代码！你能记住五种颜色的序列吗？每次序列是否不同？

当玩家正确地重复完整个颜色序列时，`序列`{:class="block3variables"}列表被清空，玩家获胜。 如果需要，一旦`序列`{:class="block3variables"} 列表变为空，你也可以显示一些闪烁的灯光作为奖励。

\--- task \--- 添加这个代码到角色的`when flag clicked`{:class="block3events"} 脚本的最后:

![ballerina](images/ballerina.png)

```blocks3
    wait until < (length of [sequence v]) = [0]>
    broadcast (won v) and wait
```

\--- /task \---

\--- task \--- 切换到舞台，然后导入 `drum machine` 的声音或其他你喜欢的 声音。

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \--- 添加此代码以播放音效，并在玩家获胜时使背景改变颜色。

![ballerina](images/stage.png)

```blocks3
    when I receive [won v]
    start sound (drum machine v)
    repeat (50)
        change [color v] effect by (25)
        wait (0.1) seconds
    end
    clear graphic effects
```

\--- /task \---