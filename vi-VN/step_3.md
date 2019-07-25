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

\--- gợi ý \--- \--- gợi ý \--- Bạn chỉ cần thêm hai khối: một trống `phát cho (0,25) nhịp`{: class = "block3sound"} và `mục (độ dài của chuỗi) của chuỗi`{: class = "block3variables"}. \--- / gợi ý \--- \--- gợi ý \---

Dưới đây là các khối bạn cần:

![diễn viên ba lê](images/ballerina.png)

```blocks3
chơi trống (\ (1 \) Snare Drum v) trong (0,25) nhịp

(mục (độ dài của [chuỗi v]) của [chuỗi v])
```

\--- /hint \---

\--- gợi ý \--- Đây là cách mã hoàn thành của bạn sẽ trông như thế nào:

![diễn viên ba lê](images/ballerina.png)

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

\--- / gợi ý \---

\--- /task \---