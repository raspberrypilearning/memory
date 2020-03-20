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

+ ゲームではそれぞれの色を表現するために異なる数字を使います:
    
    + 1 = 赤
    + 2 = 青
    + 3 = 緑
    + 4 = 黄

\--- task \---

キャラクターに異なる色の衣装を4つ、上記の4つの色ごとに1つの衣装を与えます。衣装の色が上記のリストと同じ順序であることを確認してください。

![スクリーンショット](images/colour-costume.png)

\--- /task \---

If you want, you can use the **color a shape** tool to fill parts of the costume with a different colour.

![color-a-shape](images/color-a-shape.png)

Next, add a list for storing the random sequence of colours that the player has to remember.

\--- task \---

Create a list called `sequence`{:class="block3variables"}. Only the character sprite needs to see this list, so you can select **For this sprite only** when you create the list.

[[[generic-scratch3-make-list]]]

\--- /task \---

You should now see lots of new code blocks for using lists. The empty list should be visible in the top left-hand corner of the Stage.

![screenshot](images/colour-list-blocks-annotated.png)

Each colour has a different number, so you can choose a random colour by randomly choosing a number and adding it to the list.

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