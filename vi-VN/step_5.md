## Nhiều cấp độ

Cho đến nay, người chơi chỉ phải nhớ một chuỗi năm màu. Cải thiện trò chơi của bạn bằng cách thêm điểm và thêm mã để khi người chơi ghi điểm, trò chơi sẽ chuyển sang cấp độ tiếp theo và chuỗi màu cần nhớ trở nên dài hơn.

\--- task \--- Tạo một biến mới gọi là `điểm`{: class = "block3variables"}.

[[[generic-scratch3-add-variable]]] \--- / nhiệm vụ \---

Dựa trên `điểm`{: class = "block3variables"}, trò chơi sẽ quyết định độ dài của chuỗi màu. Bắt đầu với số điểm (và độ dài chuỗi) là `3`.

\--- task \--- Thêm một khối khi bắt đầu `ký tự của bạn khi cờ nhấp vào mã`{: class = "block3events"} để đặt `điểm`{: class = "block3variables"} thành `3`. \--- /task \---

Thay vì luôn tạo một chuỗi năm màu, giờ đây bạn muốn `điểm`{: class = "block3variables"} để xác định độ dài chuỗi.

\--- Nhiệm vụ \--- Thay đổi của nhân vật `lặp lại`{: class = "block3control"} loop (cho việc tạo chuỗi màu sắc) để lặp lại `điểm`{: class = "block3variables"} lần:

![sprite](images/ballerina.png)

```blocks3
lặp lại (điểm :: biến)
kết thúc
```

\--- /task \---

\--- task \--- Nếu người chơi lặp lại trình tự chính xác, bạn nên thêm `1` vào `điểm`{: class = "block3variables"} và làm như vậy sẽ tăng độ dài của chuỗi tiếp theo. Thêm khối sau vào mã **của ký tự tại điểm bạn biết chuỗi là đúng**:

![sprite](images/ballerina.png)

```blocks3
thay đổi [điểm v] bằng (1)
```

\--- gợi ý \--- \--- gợi ý \--- Bạn biết trình tự là chính xác tại điểm khi trò chơi `phát`{: class = "block3events"} thông báo 'win'. \--- / gợi ý \--- \--- / gợi ý \---

\--- /task \---

\--- task \--- Cuối cùng, thêm một vòng lặp `mãi mãi`{: class = "block3control"} xung quanh mã tạo ra chuỗi, để trò chơi tạo ra một chuỗi màu mới cho mỗi cấp độ. Đây là cách mã của nhân vật của bạn có thể trông:

![diễn viên ba lê](images/ballerina.png)

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

\--- nhiệm vụ \--- Hãy nhờ bạn bè kiểm tra trò chơi của bạn. Hãy nhớ ẩn danh sách `chuỗi`{: class = "block3variables"} trước khi họ chơi nó! \--- / nhiệm vụ \---