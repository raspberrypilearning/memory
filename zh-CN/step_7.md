## 挑战：完善你的游戏

### 制作更多模块

你看到所有四个按钮的其他代码是否相同？

```blocks3
when I receive [red v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(1\) Snare Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game Over :: custom
end

when I receive [blue v]
if <(item (1 v) of [sequence v])=[1]> then
    play drum (\(2\) Bass Drum v) for (0.25) beats
    delete (1 v) of [sequence v]
else
    Game over :: custom
end
```

你能制作另一个所有按钮都可以使用的自定义块吗？

### 另一种服装

你能看到你的游戏开始时你的角色显示四种颜色中的一种，并且当玩家重复颜色序列时，角色总是显示序列中的最后一种颜色吗？

你可以为你的角色添加另一个纯白色服装，并添加代码，以便角色在游戏开始时和玩家重复序列时显示这个服装吗？

![screenshot](images/colour-white.png)

### 难度级别

你可以让你的玩家在“简单模式”(仅使用红色和蓝色) 和“普通模式”(使用所有四种颜色) 之间进行选择吗？

如果你愿意，你甚至可以添加一个“困难”模式，这可以使用第五个鼓！