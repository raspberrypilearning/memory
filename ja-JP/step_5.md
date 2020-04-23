## 複数のレベル

これまでのところ、プレーヤーは5つの色の順番を覚えるだけです。 スコアを追加し、プレーヤーがポイントを獲得したときにゲームが次のレベルに移動し、記憶する色の順番が長くなるようにコードを追加して、ゲームを向上させましょう。

--- task ---

`スコア`{:class="block3variables"}という名前の新しい変数を作成します。

[[[generic-scratch3-add-variable]]]

--- /task ---

`スコア`{:class="block3variables"}に基づいて、ゲームは色の順番の長さを決定します。スコア(および色の順番の長さ) `3`から始めます。

--- task ---

キャラクターの`フラグが押されたとき`{:class="block3events"}のコードの先頭に `スコア`{:class="block3variables"}を `3` にセットするブロックを追加します。

--- /task ---

常に5つの色の順番を作成するのではなく、色の順番の長さを決めるのに `スコア`{:class="block3variables"}が必要になります。

--- task ---

(色の順番を作成するための)キャラクターの `繰り返し`{:class="block3control"}ループを `スコア`{:class="block3variables"}回繰り返すように変更します。

![スプライト](images/ballerina.png)

```blocks3
(スコア :: variables) 回繰り返す
end
```

--- /task ---

--- task ---

もしプレーヤーが正しい色の順番を再現したら、 `スコア`{:class="block3variables"}に `1` を追加します。これを行うと、次の回の色の順番が長くなります。 キャラクターのコードの **色の順番が正しく再現されたことが確認できるところに** 次のブロックを追加します:

![スプライト](images/ballerina.png)

```blocks3
[スコア v] を (1) ずつ変える
```

--- hints ---


--- hint ---

色の順番が正しいことは、ゲームが'勝ち'メッセージ `を送る`{:class="block3events"}ことから知ることができます。

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

最後に、色の順番を生成するコード全体に `ずっと`{:class="block3control"}ループを追加して、ゲームがレベルごとに新しい色の順番を作成するようにします。 キャラクターのコードは次のようになります:

![バレリーナ](images/ballerina.png)

```blocks3
when flag clicked
set [スコア v] to [3]
forever
	delete (全て v) of [シーケンス v]
	repeat (スコア)
		add (pick random (1) to (4)) to [シーケンス v]
		switch costume to (item (length of [シーケンス v]) of [シーケンス v]
		wait (1) seconds
	end
	wait until < (length of [シーケンス v]) = [0]>
	broadcast (勝ち v) and wait
	change [スコア v] by (1)
end
```

--- /task ---

--- task ---

友達にゲームを試してもらいましょう。始める前に、 `シーケンス`{:class="block3variables"}リストを隠すことを忘れないでください。

--- /task ---