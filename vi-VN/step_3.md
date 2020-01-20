## Thêm âm thanh

\--- task \---

Kiểm tra dự án của bạn một vài lần. Bạn có để ý rằng đôi khi cùng một số được chọn hai lần (hoặc nhiều hơn) liên tiếp, điều này làm cho trình tự ghi nhớ khó hơn không?

\--- /task \---

Bạn có thể tạo ra một âm thanh trống mỗi khi nhân vật thay đổi trang phục? Và làm thế nào về một âm thanh trống khác nhau cho mỗi màu?

\--- task \---

Thêm tiện ích mở rộng Âm nhạc vào dự án của bạn để bạn có thể sử dụng khối `phát trống`{: class = "block3extensions"}.

[[[generic-scratch3-add-music-extension]]]

\--- /task \---

\--- task \---

Mã chơi trống là **rất** tương tự như mã thay đổi trang phục của nhân vật.

\--- hints \---

\--- hint \---

You only need to add two blocks: a `play drum for (0.25) beats`{:class="block3sound"} block and a `item (length of sequence) of sequence`{:class="block3variables"} block.

\--- /hint \---

\--- hint \---

Here are the blocks you need:

![ballerina](images/ballerina.png)

```blocks3
chơi trống (\ (1 \) Snare Drum v) trong (0,25) nhịp

(mục (độ dài của [chuỗi v]) của [chuỗi v])
```

\--- /hint \---

\--- hint \---

Here is how your finished code should look:

![ballerina](images/ballerina.png)

```blocks3
khi cờ nhấp
xóa (tất cả v) của [chuỗi v]
lặp lại (5)
    thêm (chọn ngẫu nhiên (1) đến (4)) vào [chuỗi v]
    phát trống (mục (độ dài của [chuỗi v]) của [chuỗi v]) cho (0,25) nhịp
    trang phục chuyển sang (vật phẩm (độ dài của [chuỗi v]) của [chuỗi v])
    chờ (1) giây
kết thúc
```

\--- /hint \---

\--- /hints \---

\--- /task \---