## シーケンス(順番)を再現します

さて、プレーヤーが色の順番を再現するために押す4つのボタンを追加していきましょう。

--- task ---

ボタンとして使う、4つの新しいスプライトをプロジェクトに追加します。

+ 新しいスプライトのコスチュームを編集して、4色それぞれに1つのスプライトがあるようにします。
+ コスチュームと同じ順番でスプライトをステージ上に置きます: 赤、青、緑、黄

![スクリーンショット](images/colour-drums.png)

--- /task ---

--- task ---

赤のスプライトにコードを追加して、スプライトがクリックされたとき、キャラクタースプライトに、「赤」というメッセージ `を送る`{:class="block3events"}ようにします。

![赤いドラム](images/red_drum.png)

```blocks3
    このスプライトが押されたとき
(赤 v) を送る
```

--- /task ---

`を送る`{:class="block3events"}は、たとえば学校やスーパーマーケットで聞くことができる、スピーカーで放送されたメッセージのようなものです。 すべてのスプライトは`を送る`{:class="block3events"} を聞くことができますが、応答するようになっているスプライトのみが何かを行います。

--- task ---

青、緑、黄のスプライトに同様のコードを追加して、それぞれの色のメッセージ `を送る`{:class="block3events"} ようにします。

--- /task ---

あなたは `を送る`{:class="block3events"} がスピーカーのメッセージのようであることを覚えていますか？ キャラクタースプライトが、`を送る`{:class="block3events"} メッセージに応答するようにコードを追加します。

--- task ---

キャラクタースプライトが`赤`{:class="block3events"} メッセージを受信したときに 、 数字の`1` が`シーケンス`{:class="block3variables"} リストの先頭であるかどうかをコードがチェックします(そうであれば `赤`{:class="block3events"} が次の順番ということになります) 。

`1` がリストの先頭にある場合、プレーヤーは正しい色を覚えていたことになるので、コードはリストから数字を削除します。 そうでなければゲームオーバーで、コードはゲームを終了するために `すべてを止める`{:class="block3control"} ようにします。

![バレリーナ](images/ballerina.png)

```blocks3
[赤 v] を受け取ったとき
もし <([シーケンス v] の (1 v) 番目) = [1]> なら 
  [シーケンス v] の (1 v) 番目を削除する
でなければ 
  [ゲームオーバー!] と (1) 秒言う
  stop [all v]
end
```

--- /task ---

--- task ---

キャラクタースプライトが正しい `を送る`{:class="block3events"} を受信したときにドラム音も再生するように、作成したコードに追加します。

--- hints ---


--- hint ---

それぞれの色に対応する数字を使って正しいドラム音を再生できますか？

+ 1 = 赤
+ 2 = 青
+ 3 = 緑
+ 4 = 黄

--- /hint ---

--- hint ---

`シーケンスの1番目を削除`{:class="block3variables"} ブロックの上に 、`シーケンス`{:class="block3variables"} リストの最初の音を再生する`ドラムを鳴らす`{:class="block3sound"} ブロックを追加します。

--- /hint ---

--- hint ---

追加する必要があるコードは次のとおりです。

```blocks3
when I receive [赤 v]
if <(item (1 v) of [シーケンス v])=[1]> then
+ play drum (\(1\) スネアドラム v) for (0.25) beats
delete (1 v) of [シーケンス v]
else
say [ゲームオーバー!] for (1) seconds
stop [すべてを止める v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

キャラクタースプライトが`赤`{:class="block3events"} メッセージに応答するようにするために使用したコードを複製します。 複製したコードを変更して、`青`{:class="block3events"} メッセージを送信するようにします。

--- /task ---

スプライトが`青`{:class="block3events"} メッセージに応答するとき、コードのどの部分が同じままで、どの部分が変わる必要がありますか？ 各色には対応する番号があることに注意してください。

--- task ---

キャラクターが `青`{:class="block3events"} メッセージに正しく反応するように、キャラクタースプライトのコードを変更してください。

--- hints ---


--- hint ---

これらのブロックを使いますが、すこし変更する必要があります。

![バレリーナ](images/ballerina.png)

```blocks3
<([シーケンス v] の (1 v) 番目) = [1]>

[赤 v] を受け取ったとき

(\(1\) スネアドラム v) のドラムを (0.25) 拍鳴らす
```

--- /hint ---

--- hint ---

次が `青`{:class="block3events"}を送るのためのコードです。

![バレリーナ](images/ballerina.png)

```blocks3
[青 v] を受け取ったとき
もし <([シーケンス v] の (1 v) 番目) = [2]> なら
  play drum (\(2\) バスドラム v) for (0.25) beats
  [シーケンス v] の (1 v) 番目を削除する
でなければ 
  [ゲームオーバー!] と (1) 秒言う
  stop [すべてを止める v]
end
```

--- /hint ---

--- /hints ---

--- /task ---

--- task ---

コードをあと2回複製し(緑と黄のボタン用)、必要な部分を変更して、キャラクタが新しい `を送る`{:class="block3events"} に正しく応答するようにします。

--- /task ---

コードをテストすることを忘れないでください。5つの色の順番が記憶されますか？順番は毎回異なりますか？

プレーヤーが色の順番をすべて正しく再現すると、`シーケンス`{:class="block3variables"} リストが空となり、プレーヤーが勝利します。 必要に応じて、`シーケンス`{:class="block3variables"} リストが空になったら、ごほうびとしてライトを点滅表示することもできます。

--- task ---

キャラクターの`フラグがクリックされたとき`{:class="block3events"}のスクリプトに最後にこのコードを追加します：

![バレリーナ](images/ballerina.png)

```blocks3
  wait until < (length of [シーケンス v]) = [0]>
	broadcast (勝ち v) and wait
```

--- /task ---

--- task ---

ステージに切り替えて`ドラムマシン`の音、またはあなたが好きな別の音をインポートします。

[[[generic-scratch3-sound-from-library]]]

--- /task ---

--- task ---

このコードを追加して、プレーヤーが勝ったときにサウンドを再生し、背景の色が変わるようにします。

![バレリーナ](images/stage.png)

```blocks3
    [勝ち v] を受け取ったとき
(drum machine v) の音を鳴らす
(50) 回繰り返す 
  [color v] の効果を (25) ずつ変える
  (0.1) 秒待つ
end
画像効果をなくす
```

--- /task ---