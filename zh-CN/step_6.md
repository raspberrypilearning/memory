## 高分

现在保存高分，以便您可以与朋友对战。

\--- task \--- 添加两个名为`高分` {:class="block3variables"}和`姓名` {:class="block3variables"}到你的项目中。 \--- /任务\---

当游戏结束时因为玩家得到错误的序列，游戏应该检查得分是否高于当前的高分。 如果是，游戏应该将得分保存为高分，并且还存储玩家的名字。

\--- task \--- 将代码添加到角色精灵中以存储`高分`{:class="block3variables"}. 同时询问玩家的名字，并将其存储在`姓名`{:class="block3variables"}变量。

[[[generic-scratch3-high-score]]]

\--- hints \--- \--- hint \--- 你的新代码需要遵循以下模式：

在 `游戏结束`{:class="block3looks"} 消息之后 `如果`{:class="block3control"} `分数`{:class="block3variables"} `高于`{:class="block3operators"} `高分`{:class="block3variables"} `设置`{:class="block3variables"}`高分`{:class="block3variables"} 为`分数`{:class="block3variables"} <0询问</code>{:class="block3sensing"}玩家的姓名 `设置/0>{:class="block3variables"} <code>姓名`{:class="block3variables"} 为玩家的`回答`{:class="block3sensing"} \--- /hint \--- \--- hint \---

您需要以下块：

![ballerina](images/ballerina.png)

```blocks3
if < > then
end

(score)

(score)

[ ] > [ ]

answer

(high score)

ask [What's your name?] and wait

set [high score v] to [ ] 

set [name v] to [ ] 
```

\--- /hint \--- \--- hint \--- 下面是你按下红色按钮的应该包含的代码：

![ballerina](images/ballerina.png)

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (item (1 v) of [sequence v]) for (0.25) beats
    delete (1 v) of [sequence v]
else
    say [Game over!] for (1) seconds
    if < (score :: variables) > (high score) > then
        set [high score v] to (score :: variables)
        ask [High score! What is your name?] and wait
        set [name v] to (answer)
    end
    stop [all v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

你需要将这个新代码添加到其他三种颜色的角色精灵中！

你能看到四种颜色中每种颜色的“游戏结束”代码是完全相同的吗？

![ballerina](images/ballerina.png)

```blocks3
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

如果您需要更改任何“游戏结束”代码，例如添加声音或更改“游戏结束”消息，则必须更改四次。这很烦人，浪费了很多时间。

相反，您可以定义自己的代码块，并在项目的任何位置使用它。

\--- task \--- 单击`自制积木`{:class="block3myblocks"}，然后在**制作新的积木** 。将此新块称为`游戏结束`{:class="block3myblocks"}。

\--- /task \---

\--- task \--- 从连接 `红色`{:class="block3events"} 广播的 `否则`{:class="block3control"} 模块到`游戏结束`{:class="block3myblocks"}添加代码，像下面这样：

![ballerina](images/ballerina.png)

```blocks3
define Game over
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    set [high score v] to (score :: variables)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---

\--- task \--- 现在移除在 `否则`{:class="block3control"}块中连接`红色`{:class="block3events"} 广播的代码，然后加入`游戏结束/0>{:class="block3myblocks"} 模块：</p>

<p><img src="images/ballerina.png" alt="ballerina" /></p>

<pre><code class="blocks3">when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
`</pre> 

\--- /task \---

\--- task \--- 通过玩游戏并在错误的时间点点击红色按钮来测试新块。 \--- /task\---

你的新的`游戏结束`{:class="block3myblocks"}块是一个 **函数**, 你可以在任何地方使用这一段脚本通过添加`游戏结束`{:class="block3myblocks"} 块：

\--- task \--- 现在将对于接收其他颜色`广播`{:class="block3events"} 的代码块的 `否则`{:class="block3control"}块内的代码替换为你的新的 `游戏结束`{:class="block3myblocks"} 模块。 对于`蓝色`{:class="block3events"} 消息的代码应该像这样：

![ballerina](images/ballerina.png)

```blocks3
when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

\--- /task \---

\--- task \--- 现在添加按下错误按钮时播放的声音。 您只需要在 `游戏结束`{:class="block3myblocks"} 模块中添加此代码一次，而不是四次！

![ballerina](images/ballerina.png)

```blocks3
define Game over
start sound [Cough1 v]
say [Game over!] for (1) seconds
if < (score :: variables) > (high score) > then
    play sound (trumpet1 v)
    set [high score v] to (score)
    ask [High score! What is your name?] and wait
    set [name v] to (answer)
end
stop [all v]
```

\--- /task \---