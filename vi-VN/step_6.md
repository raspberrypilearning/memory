## Điểm cao

Bây giờ hãy lưu điểm số cao để bạn có thể chơi với bạn bè của mình.

\--- task \--- Thêm hai biến mới gọi là `điểm cao`{: class = "block3variables"} và `tên`{: class = "block3variables"} vào dự án của bạn. \--- / nhiệm vụ \---

Khi trò chơi kết thúc vì người chơi bị sai trình tự, trò chơi nên kiểm tra xem điểm số có cao hơn điểm số cao hiện tại hay không. Nếu có, trò chơi nên lưu điểm dưới dạng điểm cao, đồng thời lưu tên của người chơi.

\--- task \--- Thêm mã vào sprite nhân vật của bạn để lưu trữ `điểm cao`{: class = "block3variables"}. Đồng thời hỏi tên người chơi và lưu nó trong biến `name`{: class = "block3variables"}.

[[[generic-scratch3-high-score]]]

\--- gợi ý \--- \--- gợi ý \--- Mã mới của bạn cần tuân theo mẫu này:

Sau `Trò chơi trên`{: class = "block3looks"} tin nhắn `Nếu`{: class = "block3control"} `điểm`{: class = "block3variables"} là `lớn hơn`{: class = "block3operators "} `điểm cao`{: class =" block3variabled "} `Đặt`{: class =" block3variabled "} `điểm cao`{: class =" block3variabled "} thành `điểm`{: class =" block3variabled "} `Hỏi`{: class =" block3sensing "} cho tên người chơi `Đặt`{: class =" block3variabled "} `tên`{: class =" block3variabled "} cho `câu trả lời`{: class = "block3sensing"} \--- / gợi ý \--- \--- gợi ý \---

Bạn cần các khối sau:

![diễn viên ba lê](images/ballerina.png)

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

\--- / gợi ý \--- \--- gợi ý \--- Đây là cách mã của bạn khi nhấn nút màu đỏ sẽ trông như thế nào:

![diễn viên ba lê](images/ballerina.png)

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

\--- / gợi ý \--- \--- / gợi ý \--- \--- / nhiệm vụ \---

Bạn cần thêm mã mới này vào sprite ký tự cho ba màu khác!

Bạn có thể thấy rằng mã 'Trò chơi kết thúc' cho mỗi bốn màu hoàn toàn giống nhau không?

![diễn viên ba lê](images/ballerina.png)

```blocks3
nói [Trò chơi kết thúc!] trong (1) giây
nếu < (điểm :: biến) > (điểm cao) > rồi
    đặt [điểm cao v] thành (điểm :: biến)
    hỏi [Điểm cao! Tên của bạn là gì?] Và đợi
    đặt [name v] thành (answer)
end
stop [all v]
```

Nếu bạn cần thay đổi bất kỳ mã 'Trò chơi nào', ví dụ để thêm âm thanh hoặc thay đổi thông báo 'Trò chơi kết thúc', bạn phải thay đổi bốn lần. Điều đó gây phiền nhiễu và lãng phí rất nhiều thời gian.

Thay vào đó, bạn có thể xác định khối mã của riêng mình và sử dụng nó ở bất cứ đâu trong dự án của bạn.

\--- task \--- Nhấp vào `Khối của tôi`{: class = "block3myblocks"}, và sau đó vào **Tạo khối**. Gọi khối mới này `Trò chơi trên`{: class = "block3myblocks"}.

\--- /task \---

\--- task \--- Thêm mã từ khối `khác`{: class = "block3control"} được kết nối với `màu đỏ`{: class = "block3events"} phát đến `Trò chơi trên`{: class = "block3myblocks"} chặn để nó trông như thế này:

![diễn viên ba lê](images/ballerina.png)

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

\--- task \--- Bây giờ hãy xóa mã trong khối `khác`{: class = "block3control"} được kết nối với phát `màu đỏ`{: class = "block3events"} và thêm vào `Trò chơi kết thúc Thay vào đó,`{: class = "block3myblocks"}:

![diễn viên ba lê](images/ballerina.png)

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

\--- task \--- Kiểm tra khối mới của bạn bằng cách chơi trò chơi và nhấp vào nút màu đỏ ở điểm sai trong chuỗi màu. \--- / nhiệm vụ \---

Khối `Trò chơi mới của bạn trên`{: class = "block3myblocks"} là khối **chức năng**, một tập lệnh nhỏ mà bạn có thể sử dụng bất cứ nơi nào bạn muốn trong mã của mình bằng cách thêm khối `Trò chơi trên`{: class = "block3myblocks"} trong.

\--- task \--- Cũng thay thế mã trong khối `khác`{: class = "block3control"} được kết nối với `chương trình phát sóng`{: class = "block3events"} cho các màu khác với `Trò chơi mới của bạn Khối`{: class = "block3myblocks"}. Đây là mã của thông báo `blue`{: class = "block3events"} sẽ như thế nào

![diễn viên ba lê](images/ballerina.png)

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

\--- task \--- Bây giờ thêm âm thanh phát khi nhấn nút sai. Bạn chỉ cần thêm mã này một lần trong khối `Trò chơi trên`{: class = "block3myblocks"} mà bạn đã tạo và không phải bốn lần riêng biệt!

![diễn viên ba lê](images/ballerina.png)

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