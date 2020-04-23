## 音を追加します

--- task ---

プロジェクトを数回テストしてみてください。時々同じ数が連続して2回 (またはそれ以上) 選ばれことに気付きましたか？これがあるので順番をを覚えることが難しくなるのです。

--- /task ---

キャラクタースプライトがコスチュームを変えるたびにドラムの音を鳴らすことができますか？そして、それぞれの色ごとにドラムの音を変えることはできますか。

--- task ---

プロジェクトに音楽拡張機能を追加し、 `ドラムを鳴らす`{:class="block3extensions"} ブロックを使えるようにします。

[[[generic-scratch3-add-music-extension]]]

--- /task ---

--- task ---

ドラムを鳴らすコードはキャラクタのコスチュームを変更するコードに **非常に** 似ています。

--- hints ---


--- hint ---

2つのブロックを追加するだけです: `ドラムを(0.25) 拍鳴らす`{:class="block3sound"}ブロックと `アイテム(シーケンスの長さ)`{:class="block3variables"}ブロック。

--- /hint ---

--- hint ---

必要なブロックは次のとおりです:

![バレリーナ](images/ballerina.png)

```blocks3
(\(1\) スネアドラム v) のドラムを (0.25) 拍鳴らす

(item (length of [シーケンス v]) of [シーケンス v])
```

--- /hint ---

--- hint ---

完成したコードは次のようになります:

![バレリーナ](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
	add (pick random (1) to (4)) to [sequence v]
    play drum (item (length of [シーケンス v]) of [シーケンス v]) for (0.25) beats
    switch costume to (item (length of [シーケンス v]) of [シーケンス v])
    wait (1) seconds
end
```

--- /hint ---

--- /hints ---

--- /task ---