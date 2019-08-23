## 多重水平

到目前为止，玩家只需要记住五种颜色的序列。 通过添加分数和添加代码来改善您的游戏，以便当玩家得分时，游戏移动到下一级别并且要记住的颜色序列变得更长。

\--- task \--- 创建一个新的变量叫做 `分数`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]] \--- /task \---

基与 `分数`{:class="block3variables"}, 游戏将决定颜色序列的长度。以分数 (和序列长度) 为`3`开始。

\--- task \--- 添加一个块到精灵的`当 ⚑ 被点击`{:class="block3events"} 代码的开始，将`分数`{:class="block3variables"} 设为`3`。 \--- /task \---

您现在想要`分数`{:class="block3variables"} 来决定序列长度，而不是总是创建一个五种颜色序列。

\--- task \--- 改变角色的`重复执行`{:class="block3control"}循环(用于创建颜色序列)为重复 `分数`{:class="block3variables"} 次：

![精灵](images/ballerina.png)

```blocks3
重复执行 (分数 :: variables) 次
结束
```

\--- /task \---

\--- task \--- 如果玩家重复正确的序列，你就应该给 `分数`{:class="block3variables"}加`1` ，这样做会增加下一个序列的长度。 添加下面的块到角色的代码 **在你知道颜色顺序正确的时候**:

![精灵](images/ballerina.png)

```blocks3
将[分数] 增加(1)
```

\--- hints \--- \--- hint \--- 在游戏`广播`{:class="block3events"} ‘won' 的消息时你知道序列是正确的。 \--- /hint \--- \--- /hints \---

\--- /task \---

\--- task \--- 最后，添加一个`重复执行`{:class="block3control"} 循环在产生序列的代码周围，以至于游戏为每个水平建立一个新的颜色序列。 这是您的角色代码的外观：

![芭蕾舞演员](images/ballerina.png)

```blocks3
当 ⚑ 被点击
将 [分数] 设为 [3]
重复执行 
  删除 [序列] 的第 (全部) 项
  重复执行 (分数) 次 
    将 (在 (1) 和 (4) 之间取随机数) 加入 [序列]
    换成 ([序列] 的第 ([序列] 的项目数) 项) 造型
    等待 (1) 秒
  结束
  等待 <([序列] 的项目数) = [0]>
  广播 (won v) 并等待
  将 [分数 v] 增加 (1)
结束
```

\--- /task \---

\--- task \--- 让你的朋友测试你的游戏。在他们玩之前记着隐藏`序列`{:class="block3variables"}！