## サウンドを追加

\--- task \---

プロジェクトを数回テストします。あなたは時々同じ数が連続して2回 (またはそれ以上) 選ばれると、シーケンスを覚えることが難しくなることに気付きました？

\--- /task \---

キャラクタースプライトがコスチュームを変えるたびにドラムサウンドを鳴らすことができますか？そして、それぞれの色ごとに異なるドラムサウンドはどうでしょうか。

\--- task \---

プロジェクトに音楽拡張機能を追加し、 `play drum`{:class="block3extensions"} ブロックを使えるようにします。

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

ドラムを鳴らすコードは **非常に** キャラクタのコスチュームを変更するコードに似ています。

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /hint \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
(\(1\) スネアドラム v) のドラムを(0.25) 拍鳴らす

([シーケンス v] の アイテム ([シーケンス v] の長さ))
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

```blocks3
フラグがクリックされたとき
[シーケンス v] の (すべて v) を削除する
繰り返し(5)
    ((1) から(4) までの乱数) を[シーケンス v] に追加する
    ([シーケンス v] の([シーケンス v] の長さ) 番目) のドラムを(0.25) 拍鳴らす
    ([シーケンス v] の([シーケンス v] の長さ) 番目) のコスチュームに変える
    (1) 秒待つ
終了
```

\--- /hint \---

\--- /hints \---

\--- /task \---