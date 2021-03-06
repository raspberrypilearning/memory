## ハイスコア

ハイスコアを保存して、友達と対戦できるようにしましょう。

--- task ---

`ハイスコア`{:class="block3variables"}と `名前`{:class="block3variables"}という2つの新しい変数をプロジェクトに追加します。

--- /task ---

プレイヤーが色の順番を間違えてゲームが終了したとき、ゲームはスコアが現在のハイスコアより高いかどうかをチェックする必要があります。 もしそうであれば、ゲームはそのスコアをハイスコアとして保存し、またプレイヤーの名前も保存します。

--- task ---

あなたのキャラクタースプライトに `ハイスコア`{:class="block3variables"}を保存するコードを追加してください。 また、プレイヤーの名前をたずね、それを `名前`{:class="block3variables"}変数に保存するようにします。

[[[generic-scratch3-high-score]]]

--- hints ---


--- hint ---

新しく作っているコードは次のパターンのとおりにします。

`ゲームオーバー`{:class="block3looks"}メッセージの後 `もし`{:class="block3control"} `スコア`{:class="block3variables"}が `ハイスコア`{:class=" block3variables"} `より大きいければ`{:class="block3operators"} `ハイスコア`{:class="block3variables"} を`スコア`{:class="block3variables"} に `し`{:class="block3variables"}、プレイヤーの名前を`たずね`{:class="block3sensing"}、その`名前`{:class="block3variables"} を`答え`{:class="block3sensing"} に`する`{:class="block3variables"}

--- /hint ---

--- hint ---

次のブロックが必要です。

![バレリーナ](images/ballerina.png)

```blocks3
もし <> なら
end

(スコア)

(スコア)

<[ ] > [ ]>

(答え)

(ハイスコア)

[あなたのお名前は？] と聞いて待つ

[ハイスコア v] を[ ] にする

[名前 v] を[ ] にする 
```

--- /hint ---

--- hint ---

赤いボタンが押されたときのコードは次のようになります。

![バレリーナ](images/ballerina.png)

```blocks3
when I receive [赤 v]
if <(item (1 v) of [シーケンス v])=[1]> then
	play drum (item (1 v) of [シーケンス v]) for (0.25) beats
	delete (1 v) of [シーケンス v]
else
	say [ゲームオーバー！] for (1) seconds
	if < (スコア :: variables) > (ハイスコア) > then
		set [ハイスコア v] to (スコア :: variables)
		ask [ハイスコア！ あなたのお名前は？] and wait
		set [名前 v] to (答え)
	end
	stop [すべてを止める v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

他の3色についても、この新しいコードをキャラクタースプライトに追加する必要があります。

4色それぞれの「ゲームオーバー」コードがまったく同じであることがわかりますか？

![バレリーナ](images/ballerina.png)

```blocks3
[ゲームオーバー！] と (1) 秒言う
もし <(スコア:: variables) > (ハイスコア)> なら
    [ハイスコア v] を (スコア:: variables) にする
    [ハイスコア！ あなたのお名前は？] と聞いて待つ
    [名前 v] を (答え) にする
end
stop [すべてを止める v]
```

例えば、音を追加したり、「ゲームオーバー」メッセージを変更するなど、「ゲームオーバー」コードを変更する必要がある場合は、4回変更する必要があります。それはめんどうなことであり、多くの時間を無駄にします。

代わりに、独自のコードブロックを定義すれば、プロジェクト内のどこでも使うことができます。

--- task ---

`ブロック定義`{:class="block3myblocks"}を押し、そして **ブロックを作る**を押してください。この新しいブロックを`ゲームオーバー`{:class="block3myblocks"}と名前を付けます。

--- /task ---

--- task ---

`赤`{:class="block3events"}メッセージ送信に接続された`でなければ`{:class="block3control"}ブロックを`ゲームオーバー`{:class="block3myblocks"}ブロックに追加します、すると、次のようになります。

![バレリーナ](images/ballerina.png)

```blocks3
定義 ゲームオーバー
[ゲームオーバー！] と (1) 秒言う
もし <(スコア:: variables) > (ハイスコア)> なら
    [ハイスコア v] を (スコア:: variables) にする
    [ハイスコア！ あなたのお名前は？] と聞いて待つ
    [名前 v] を (答え) にする
end
stop [すべてを止める v]
```

--- /task ---

--- task ---

`赤`{:class="block3events"}メッセージ送信に接続された `でなければ`{:class="block3control"}ブロックにあるコードを削除し、 `ゲームオーバー`{:class="block3myblocks"}ブロックを追加します:

![バレリーナ](images/ballerina.png)

```blocks3
[赤 v] を受け取ったとき
もし <([シーケンス v] の (1 v) 番目) = [1]> なら
    play drum (\(1\) スネアドラム v) for (0.25) beats
    [シーケンス v] の (1 v) 番目を削除する 
でなければ
    ゲームオーバー:: custom
end
```

--- /task ---

--- task ---

ゲームをプレイし、色の順番の間違った箇所で赤いボタンを押して、新しいブロックをテストしてください。

--- /task ---

あなたの新しい `ゲームオーバー`{:class="block3myblocks"}ブロックは **関数**(`ゲームオーバー`{:class="block3myblocks"}ブロックを追加することであなたのコードの好きな場所で使える小さなスクリプト)です。

--- task ---

ほかの色についても、`を送る`{:class="block3events"}に接続された `でなければ`{:class="block3control"}ブロックを、あなたの新しい`ゲームオーバー`{:class="block3myblocks"}ブロックに置き換えます。 `青`{:class="block3events"}メッセージのコードは次のようになります。

![バレリーナ](images/ballerina.png)

```blocks3
[青 v] を受け取ったとき
もし <([シーケンス v] の (1 v) 番目) = [1]> なら
    play drum (\(2\) バスドラム v) for (0.25) beats
    [シーケンス v] の (1 v) 番目を削除する
でなければ
    ゲームオーバー:: custom
end
```

--- /task ---

--- task ---

次に、間違ったボタンが押されたときに再生されるサウンドを追加します。 このコードを追加するのは、あなたが作成した `ゲームオーバー`{:class="block3myblocks"}ブロックに対しての1回だけで、4回追加する必要はありません。

![バレリーナ](images/ballerina.png)

```blocks3
定義 ゲームオーバー
[Cough v] の音を鳴らす
[ゲームオーバー！] と (1) 秒言う
もし <(スコア:: variables) > (ハイスコア)> なら
    (トランペット v) の音を鳴らす
    [ハイスコア v] を (スコア) にする
    [ハイスコア！ あなたのお名前は？] と聞いて待つ
    [名前 v] を (答え) にする
end
stop [すべてを止める v]
```

--- /task ---