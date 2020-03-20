## カラーシーケンス(色の順番)を作成する

まず、色のばらばらの順番を表示できるキャラクタを作成します。

\--- task \---

新しいScratchプロジェクトを開きます。

**オンライン**: 新しいオンラインScratchプロジェクトを[rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}で開きます。

**Offline**: 新しいプロジェクトを オフラインエディターで開きます。

Scratchオフラインエディタをダウンロードしてインストールする必要がある場合は、 [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}で見つけることができます。

\--- /task \---

\--- task \---

キャラクターのスプライトと背景を選択します。バレリーナを使用することもできますが、キャラクターは人である必要はなく、異なる色を見せることができれば十分です。

![スクリーンショット](images/colour-sprite.png)

\--- /task \---

+ ゲームではそれぞれの色を表現するために異なる番号を使います:
    
    + 1 = 赤
    + 2 = 青
    + 3 = 緑
    + 4 = 黄

\--- task \---

キャラクターに異なる色の衣装を4つ、上記の4つの色ごとに1つの衣装を与えます。衣装の色が上記のリストと同じ順序であることを確認してください。

![スクリーンショット](images/colour-costume.png)

\--- /task \---

**塗りつぶし** ツールを使えば、衣装の各部を違う色で塗りつぶすこともできます。

![塗りつぶす](images/color-a-shape.png)

次に、色のばらばらの順番を格納するリストを追加します。プレーヤーはこの順番を覚えなければなりません。

\--- task \---

`シーケンス`{:class = "block3variables"}というリストを作成します。 このリストを見る必要があるのはキャラクタースプライトだけなので、リストを作成するときに **このスプライトのみ**を選びます。

[[[generic-scratch3-make-list]]]

\--- /task \---

リストを使用するための多くの新しいコードブロックが表示されます。ステージの左上隅には空のリストが表示されてます。

![スクリーンショット](images/colour-list-blocks-annotated.png)

各色には異なる番号があるため、番号をばらばらに選択してリストに追加することにより、ばらばらな色を選択できます。

\--- task \---

Add this code to the character sprite to choose a random number and add it to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
add (pick random (1) to (4)) to [sequence v]
```

\--- /task \---

\--- task \---

Test your code. Check that, each time you click the flag, a random number between 1 and 4 gets added to the list.

\--- /task \---

\--- task \---

Can you add code to your program to generate five random numbers at once?

\--- hints \---

\--- hint \---

Add a `delete all of sequence`{:class="block3variables"} to first delete all the items on the list, and then add a `repeat`{:class="block3control"} block that adds five random numbers to the list.

\--- /hint \---

\--- hint \---

This is what your code should look like:

![ballerina](images/ballerina.png)

```blocks3
when flag clicked
delete (all v) of [sequence v]
repeat (5)
    add (pick random (1) to (4)) to [sequence v]
end
```

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Each time a number gets added to the list, the character should change its costume so the costume's colour matches the number. Put these blocks into your code immediately below where a random number is added to `sequence`{:class="block3variables"}:

![ballerina](images/ballerina.png)

```blocks3
switch costume to (item (length of [sequence v]) of [sequence v])
wait (1) seconds
```

\--- /task \---