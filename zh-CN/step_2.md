## 创建一个颜色序列

首先，让我们创建一个角色，该角色将展示一个需要记住的随机颜色序列。

\--- task \--- 打开一个新的Scratch项目。

**在线： **在[rpf.io/scrath-new](https://rpf.io/scratchon)打开一个新的Scratch在线项目。

**离线： **在离线编辑器中打开一个新项目。

如果您需要下载并安装Scratch离线编辑器，可以在[ rpf.io/scratchoff ](https://rpf.io/scratchoff)中获取。

\--- /task \---

-- task -- 选择一个角色和一个背景。比如你可以用芭蕾舞演员。你的角色也不一定是一个人，只要能展示不同颜色就够了。

![screenshot](images/colour-sprite.png) \--- /task \---

+ 您的游戏应使用不同的数字来表示每种颜色：
    
    + 1 = 红色
    + 2 = 蓝色
    + 3 = 绿色
    + 4 = 黄色

\---任务\--- 你的角色提供四种不同颜色的服装，以上四种颜色各一套。 确保您的服装颜色的顺序与上面的列表顺序相同。

![screenshot](images/colour-costume.png) \--- /task \---

如果需要，可以使用**填充**工具来给服装不同部分填上不同的颜色。

![color-a-shape](images/color-a-shape.png)

接下来，添加一个列表，用于存储玩家必须记住的随机颜色序列。

\--- task \--- 创建一个列表，名字是 `sequence`{:class="block3variables"}. Only the character sprite needs to see this list, so you can select **For this sprite only** when you create the list.

[[[generic-scratch3-make-list]]]

\--- /task \---

You should now see lots of new code blocks for using lists. The empty list should be visible in the top left-hand corner of the Stage.

![screenshot](images/colour-list-blocks-annotated.png)

Each colour has a different number, so you can choose a random colour by randomly choosing a number and adding it to the list.

\--- task \--- Add this code to the character sprite to choose a random number and add it to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
add (pick random (1) to (4)) to [sequence v]
```

\--- /task \---

\--- task \--- Test your code. Check that, each time you click the flag, a random number between 1 and 4 gets added to the list. \--- /task \---

\--- task \--- Can you add code to your program to generate five random numbers at once?

\--- hints \--- \--- hint \--- Add a `delete all of sequence`{:class="block3variables"} to first delete all the items on the list, and then add a `repeat`{:class="block3control"} block that adds five random numbers to the list. \--- /hint \--- \--- hint \---

This is what your code should look like:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
end
```

\--- /hint \--- \--- /hints \--- \--- /task \---

\--- task \--- Each time a number gets added to the list, the character should change its costume so the costume's colour matches the number. Put these blocks into your code immediately below where a random number is added to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
switch costume to (item (length of [sequence v]) of [sequence v])
wait (1) seconds
```

\--- /task \---