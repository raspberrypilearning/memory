## 高分

現在保存高分，以便您可以與朋友對戰。

\--- task \--- 添加兩個名為 `high score`{：class =“block3variables”}和 `name`{：class =“block3variables”}的新變量。 \--- /任務\---

當遊戲結束時因為玩家得到錯誤的序列，遊戲應該檢查得分是否高於當前的高分。 如果是，遊戲應該將得分保存為高分，並且還存儲玩家的名字。

\--- task \--- 將代碼添加到角色精靈中以存儲 `高分`{：class =“block3variables”}。 同時詢問玩家的名字，並將其存儲在 `名`{：class =“block3variables”}變量中。

[[[generic-scratch3-high-score]]]

\---提示\--- \---提示\--- 您的新代碼需要遵循以下模式：

後 `遊戲結束`{：類=“block3looks”}消息 `如果`{：類=“block3control”}的 `分`{：類=“block3variables”}是 `大於`{：類=“block3operators “} `高分`{：class =”block3variables“} `將` `高分`{：class =”block3variables“}設為</code> {：class =”block3variables“}到 `分`{：class =” block3variables“} `問`{：class =”block3sensing“}為玩家的名字 `設置`{：class =”block3variables“} `名`{：class =”block3variables“}到 `回答`{： class =“block3sensing”} \--- /提示\--- \---提示\---

您需要以下塊：

![芭蕾舞演員](images/ballerina.png)

```blocks3
如果 < > 則
結束

（得分）

（得分）

[] > []

回答

（高分）

問[你的名字是什麼？]並等待

套[高分v]至[] 

套[名稱v]到[] 
```

\--- /提示\--- \---提示\--- 以下是按下紅色按鈕的代碼應如下所示：

![芭蕾舞演員](images/ballerina.png)

```blocks3
當我收到[紅色v]
如果 <（[序列v]的項目（1 v））=[1]> 那麼
    播放鼓（[序列v]的項目（1 v））為（0.25）節拍
    刪除（1 v）[sequence v]
else
    說[Game over！] for（1）seconds
    if < （score :: variables） > （high score） > then
        set [high score v] to（score :: variables） ）
        問[高分！ 你的名字是什麼？]並等待
        集[名字v]到（回答）
    結束
    停止[全v]
結束
```

\--- /提示\--- \--- /提示\--- \--- /任務\---

你需要將這個新代碼添加到其他三種顏色的角色精靈中！

你能看到四種顏色中每種顏色的“遊戲結束”代碼是完全相同的嗎？

![芭蕾舞演員](images/ballerina.png)

```blocks3
說[遊戲結束！]為（1）秒
如果 < （得分::變量） > （高分） > 然後
    設置[高分v]到（得分::變量）
    問[高分！ 你的名字是什麼？]並等待
    集[名字v]到（回答）
結束
停止[全部v]
```

如果您需要更改任何“遊戲結束”代碼，例如添加聲音或更改“遊戲結束”消息，則必須更改四次。這很煩人，浪費了很多時間。

相反，您可以定義自己的代碼塊，並在項目的任何位置使用它。

\--- task \--- 點擊 `My blocks`{：class =“block3myblocks”}，然後點擊 **一個Block**。將這個新區塊稱為 `遊戲超過`{：class =“block3myblocks”}。

\--- /任務\---

\--- task \--- 添加來自 `其他`{：class =“block3control”}塊的代碼連接到 `red`{：class =“block3events”}廣播到 `遊戲超過`{：class = “block3myblocks”}阻止它看起來像這樣：

![芭蕾舞演員](images/ballerina.png)

```blocks3
定義遊戲超過
說[遊戲結束！]為（1）秒
如果 < （得分::變量） > （高分） > 然後
    設置[高分v]到（得分::變量）
    問[高分] ！ 你的名字是什麼？]並等待
    集[名字v]到（回答）
結束
停止[全部v]
```

\--- /任務\---

\--- task \--- 現在刪除 `其他`{：class =“block3control”}塊中連接到 `紅色`{：class =“block3events”}廣播的代碼，並在 `遊戲中添加`{：class =“block3myblocks”}阻止：

![芭蕾舞演員](images/ballerina.png)

```blocks3
當我收到[紅色v]
如果 <（[序列v]的項目（1 v））=[1]> 則
    播放鼓（\（1 \）Snare Drum v）for（0.25）beats
    delete（1 v） [序列v]
其他
    遊戲結束::自定義
結束
```

\--- /任務\---

\--- task \--- 通過玩遊戲並單擊顏色序列中錯誤點的紅色按鈕來測試新塊。 \--- /任務\---

你的新 `遊戲超過`{：class =“block3myblocks”}塊是一個 **函數**，一個小腳本，你可以在你的代碼中任何你喜歡的地方添加 `遊戲超過`{：class =“block3myblocks”}塊在。

\--- task \--- 還替換了 `其他`{：class =“block3control”}塊中的代碼連接到 `廣播`{：class =“block3events”}用於其他顏色的新 `遊戲結束`{：class =“block3myblocks”}阻止。 以下是 `blue`{：class =“block3events”}消息的代碼應該是什麼樣子

![芭蕾舞演員](images/ballerina.png)

```blocks3
當我收到[藍色v]
如果 <（[序列v]的項目（1 v））=[1]> 然後
    播放鼓（\（2 \）Bass Drum v）for（0.25）beats
    delete（1 v） [序列v]
其他
    遊戲結束::自定義
結束
```

\--- /任務\---

\--- task \--- 現在添加按下錯誤按鈕時播放的聲音。 你只需要在一次添加此代碼 `比賽結束`{：類=“block3myblocks”}所做塊，而不是四個單獨倍！

![芭蕾舞演員](images/ballerina.png)

```blocks3
定義遊戲超過
開始聲音[Cough1 v]
說[遊戲結束！]為（1）秒
如果 < （得分::變量） > （高分） > 然後
    播放聲音（trumpet1 v）
    集[高分] v]到（得分）
    問[高分！ 你的名字是什麼？]並等待
    集[名字v]到（回答）
結束
停止[全部v]
```

\--- /任務\---