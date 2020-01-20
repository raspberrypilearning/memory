## Điểm cao

Bây giờ hãy lưu điểm số cao để bạn có thể chơi với bạn bè của mình.

\--- task \---

Add two new variables called `high score`{:class="block3variables"} and `name`{:class="block3variables"} to your project.

\--- /task \---

When the game ends because the player gets the sequence wrong, the game should check whether the score is higher than the current high score. If it is, the game should save the score as the high score, and also store the name of the player.

\--- task \---

Add code to your character sprite to store the `high score`{:class="block3variables"}. Also ask for the player's name, and store it in the `name`{:class="block3variables"} variable.

[[[generic-scratch3-high-score]]]

\--- hints \---

\--- hint \---

Your new code needs to follow this pattern:

After the `Game over`{:class="block3looks"} message `If`{:class="block3control"} the `score`{:class="block3variables"} is `greater than`{:class="block3operators"} the `high score`{:class="block3variables"} `Set`{:class="block3variables"} the `high score`{:class="block3variables"} to the `score`{:class="block3variables"} `Ask`{:class="block3sensing"} for the player's name `Set`{:class="block3variables"} the `name`{:class="block3variables"} to the `answer`{:class="block3sensing"}

\--- /hint \---

\--- hint \---

You need the following blocks:

![ballerina](images/ballerina.png)

```blocks3
nếu < > thì
kết thúc

(điểm)

(điểm)

[] > []

câu trả lời

(điểm cao)

hỏi [Tên bạn là gì?] và đợi

đặt [điểm cao v] thành [] 

bộ [ tên v] thành [] 
```

\--- /hint \---

\--- hint \---

Here's how your code for when the red button is pressed should look:

![ballerina](images/ballerina.png)

```blocks3
khi tôi nhận được [đỏ v]
nếu <(mục (1 v) của [trình tự v]) =[1]> thì
    phát trống (mục (1 v) của [trình tự v]) cho (0,25) nhịp
    xóa (1 v) của [chuỗi v]
khác
    nói [Trò chơi kết thúc!] trong (1) giây
    nếu < (điểm :: biến) > (điểm cao) > sau đó
        đặt [điểm cao v] thành (điểm :: biến )
        hỏi [Điểm cao! Tên bạn là gì?] Và đợi
        đặt [tên v] thành (câu trả lời)
    kết thúc
    điểm dừng [tất cả v]
kết thúc
```

\--- /hint \---

\--- /hints \---

\--- /task \---

You need to add this new code to the character sprite for the other three colours too!

Can you see that the 'Game over' code for each of the four colours is exactly the same?

![ballerina](images/ballerina.png)

```blocks3
nói [Trò chơi kết thúc!] trong (1) giây
nếu < (điểm :: biến) > (điểm cao) > rồi
    đặt [điểm cao v] thành (điểm :: biến)
    hỏi [Điểm cao! Tên của bạn là gì?] Và đợi
    đặt [name v] thành (answer)
end
stop [all v]
```

If you need to change any of the 'Game over' code, for example to add a sound or change the 'Game over' message, you have to change it four times. That's annoying and wastes a lot of time.

Instead, you can define your own code block, and use it anywhere in your project.

\--- task \---

Click on `My blocks`{:class="block3myblocks"}, and then on **Make a Block**. Call this new block `Game over`{:class="block3myblocks"}.

\--- /task \---

\--- task \---

Add the code from the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast to the `Game over`{:class="block3myblocks"} block so that it looks like this:

![ballerina](images/ballerina.png)

```blocks3
xác định Trò chơi trên
nói [Trò chơi kết thúc!] trong (1) giây
nếu < (điểm :: biến) > (điểm cao) > sau đó
    đặt [điểm cao v] thành (điểm :: biến)
    hỏi [Điểm cao ! Tên của bạn là gì?] Và đợi
    đặt [name v] thành (answer)
end
stop [all v]
```

\--- /task \---

\--- task \---

Now remove the code that's in the `else`{:class="block3control"} block connected to the `red`{:class="block3events"} broadcast, and add in the `Game over`{:class="block3myblocks"} block instead:

![ballerina](images/ballerina.png)

```blocks3
khi tôi nhận được [red v]
nếu <(mục (1 v) của [chuỗi v]) =[1]> thì
    trống chơi (\ (1 \) Snare Drum v) cho (0,25) nhịp
    xóa (1 v) của [chuỗi v]
khác
    Trò chơi kết thúc :: tùy chỉnh
kết thúc
```

\--- /task \---

\--- task \---

Test your new block by playing the game and clicking the red button at the wrong point in the colour sequence.

\--- /task \---

Your new `Game over`{:class="block3myblocks"} block is a **function**, a little script that you can use anywhere you like in your code by adding the `Game over`{:class="block3myblocks"} block in.

\--- task \---

Also replace the code in the `else`{:class="block3control"} block connected to the `broadcasts`{:class="block3events"} for the other colours with your new `Game over`{:class="block3myblocks"} block. Here is what the code for the `blue`{:class="block3events"} message should look like

![ballerina](images/ballerina.png)

```blocks3
khi tôi nhận được [blue v]
nếu <(mục (1 v) của [chuỗi v]) =[1]> thì
    trống chơi (\ (2 \) Bass Drum v) cho (0,25) nhịp
    xóa (1 v) của [chuỗi v]
khác
    Trò chơi kết thúc :: tùy chỉnh
kết thúc
```

\--- /task \---

\--- task \---

Now add a sound that plays when the wrong button is pressed. You only need to add this code once in the `Game over`{:class="block3myblocks"} block that you made, and not four separate times!

![ballerina](images/ballerina.png)

```blocks3
xác định Trò chơi trên
bắt đầu âm thanh [Cough1 v]
nói [Trò chơi kết thúc!] trong (1) giây
nếu < (điểm :: biến) > (điểm cao) > rồi
    phát âm thanh (kèn1 v)
    đặt [điểm cao v] đến (điểm)
    hỏi [Điểm cao! Tên của bạn là gì?] Và đợi
    đặt [name v] thành (answer)
end
stop [all v]
```

\--- /task \---