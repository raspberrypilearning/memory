## Tạo một chuỗi màu

Đầu tiên tạo một nhân vật có thể hiển thị một chuỗi màu sắc ngẫu nhiên.

\--- task \--- Mở một dự án Scratch mới.

**Online**: open a new online Scratch project at [rpf.io/scratch-new](https://rpf.io/scratch-new){:target="_blank"}.

**Ngoại tuyến**: mở một dự án mới trong trình chỉnh sửa ngoại tuyến.

If you need to download and install the Scratch offline editor, you can find it at [rpf.io/scratchoff](https://rpf.io/scratchoff){:target="_blank"}.

\--- /bài tập \---

\--- task \--- Chọn một nhân vật và bối cảnh. Bạn có thể sử dụng nữ diễn viên ballet, nhưng nhân vật của bạn không phải là một người, họ chỉ cần có thể hiển thị các màu sắc khác nhau.

![ảnh chụp màn hình](images/colour-sprite.png) \--- /task \---

+ Trò chơi của bạn nên sử dụng một số khác nhau để thể hiện mỗi màu:
    
    + 1 = đỏ
    + 2 = màu xanh
    + 3 = xanh
    + 4 = màu vàng

\--- task \--- Cung cấp cho nhân vật của bạn bốn trang phục có màu sắc khác nhau, một trang phục cho mỗi bốn màu được hiển thị ở trên. Hãy chắc chắn rằng trang phục màu của bạn theo thứ tự như danh sách trên.

![ảnh chụp màn hình](images/colour-costume.png) \--- /task \---

Nếu bạn muốn, bạn có thể sử dụng công cụ **color a shape** để tô các phần của trang phục bằng một màu khác.

![màu sắc](images/color-a-shape.png)

Tiếp theo, thêm một danh sách để lưu trữ chuỗi màu ngẫu nhiên mà người chơi phải nhớ.

\--- task \--- Tạo một danh sách gọi là `chuỗi`{: class = "block3variables"}. Chỉ sprite ký tự cần xem danh sách này, vì vậy bạn có thể chọn **Đối với sprite này chỉ** khi bạn tạo danh sách.

[[[generic-scratch3-make-list]]]

\--- /task \---

Bây giờ bạn sẽ thấy nhiều khối mã mới để sử dụng danh sách. Danh sách trống sẽ hiển thị ở góc trên bên trái của Sân khấu.

![ảnh chụp màn hình](images/colour-list-blocks-annotated.png)

Mỗi màu có một số khác nhau, vì vậy bạn có thể chọn một màu ngẫu nhiên bằng cách chọn ngẫu nhiên một số và thêm nó vào danh sách.

\--- task \--- Thêm mã này vào ký tự sprite để chọn một số ngẫu nhiên và thêm nó vào `chuỗi`{: class = "block3variables"}:

![diễn viên ba lê](images/ballerina.png)

```blocks3
khi cờ nhấp
thêm (chọn ngẫu nhiên (1) đến (4)) vào [chuỗi v]
```

\--- /task \---

\--- nhiệm vụ \--- Kiểm tra mã của bạn. Kiểm tra xem, mỗi lần bạn nhấp vào cờ, một số ngẫu nhiên từ 1 đến 4 sẽ được thêm vào danh sách. \--- / nhiệm vụ \---

\--- task \--- Bạn có thể thêm mã vào chương trình của mình để tạo năm số ngẫu nhiên cùng một lúc không?

\--- gợi ý \--- \--- gợi ý \--- Thêm a `xóa tất cả chuỗi`{: class = "block3variables"} để trước tiên xóa tất cả các mục trong danh sách, sau đó thêm `lặp lại`{: class = "block3control"} thêm năm số ngẫu nhiên vào danh sách. \--- / gợi ý \--- \--- gợi ý \---

Đây là mã của bạn sẽ trông như thế nào:

![diễn viên ba lê](images/ballerina.png)

```blocks3
khi cờ nhấp
xóa (tất cả v) của [chuỗi v]
lặp lại (5)
    thêm (chọn ngẫu nhiên (1) đến (4)) vào [chuỗi v]
kết thúc
```

\--- / gợi ý \--- \--- / gợi ý \--- \--- / nhiệm vụ \---

\--- task \--- Mỗi khi một số được thêm vào danh sách, nhân vật nên thay đổi trang phục để màu của trang phục phù hợp với số đó. Đặt các khối này vào mã của bạn ngay bên dưới, nơi một số ngẫu nhiên được thêm vào `chuỗi`{: class = "block3variables"}:

![diễn viên ba lê](images/ballerina.png)

```blocks3
chuyển trang phục sang (mục (độ dài của [chuỗi v]) của [chuỗi v])
chờ (1) giây
```

\--- /task \---