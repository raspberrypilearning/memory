## Nhiều cấp độ

Cho đến nay, người chơi chỉ phải nhớ một chuỗi năm màu. Cải thiện trò chơi của bạn bằng cách thêm điểm và thêm mã để khi người chơi ghi điểm, trò chơi sẽ chuyển sang cấp độ tiếp theo và chuỗi màu cần nhớ trở nên dài hơn.

\--- task \---

Create a new variable called `score`{:class="block3variables"}.

[[[generic-scratch3-add-variable]]]

\--- /task \---

Based on the `score`{:class="block3variables"}, the game will decide on the length of the colour sequence. Start with a score (and a sequence length) of `3`.

\--- task \---

Add a block at the start of your character's `when flag clicked`{:class="block3events"} code to set the `score`{:class="block3variables"} to `3`.

\--- /task \---

Instead of always creating a sequence of five colours, you now want the `score`{:class="block3variables"} to determine the sequence length.

\--- task \---

Change the character's `repeat`{:class="block3control"} loop (for creating the colour sequence) to repeat `score`{:class="block3variables"} times:

![sprite](images/ballerina.png)

```blocks3
lặp lại (điểm :: biến)
kết thúc
```

\--- /task \---

\--- task \---

If the player repeats the correct sequence, you should add `1` to `score`{:class="block3variables"}, and doing so increases the length of the next sequence. Add the following block to the character's code **at the point you know the sequence is correct**:

![sprite](images/ballerina.png)

```blocks3
thay đổi [điểm v] bằng (1)
```

\--- hints \---

\--- hint \---

You know the sequence is correct at the point when the game `broadcasts`{:class="block3events"} the 'win' message.

\--- /hint \---

\--- /hints \---

\--- /task \---

\--- task \---

Finally, add a `forever`{:class="block3control"} loop around the code that generates the sequence, so that the game creates a new colour sequence for each level. This is how your character's code might look:

![ballerina](images/ballerina.png)

```blocks3
khi cờ nhấp
đặt [điểm v] thành [3]
mãi mãi
    xóa (tất cả v) của [chuỗi v]
    lặp lại (điểm)
        thêm (chọn ngẫu nhiên (1) thành (4)) thành [chuỗi v]
        chuyển trang phục đến (mục (độ dài của [chuỗi v]) của [chuỗi v]
        chờ (1) giây
    kết thúc
    đợi đến < (độ dài của [chuỗi v]) = [0]>
    phát (thắng v) và chờ
    thay đổi [ điểm v] bởi (1)
kết thúc
```

\--- /task \---

\--- task \---

Get your friends to test out your game. Remember to hide the `sequence`{:class="block3variables"} list before they play it!

\--- /task \---