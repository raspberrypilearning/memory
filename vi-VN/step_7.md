## Thử thách: cải thiện trò chơi của bạn

### Tạo nhiều khối hơn

Bạn có thấy mã nào khác giống nhau cho cả bốn nút không?

```blocks3
khi tôi nhận được [red v]
nếu <(mục (1 v) của [chuỗi v]) =[1]> thì
    trống chơi (\ (1 \) Snare Drum v) cho (0,25) nhịp
    xóa (1 v) của [chuỗi v]
khác
    Trò chơi kết thúc :: tùy chỉnh
kết thúc

khi tôi nhận được [màu xanh v]
nếu <(mục (1 v) của [trình tự v]) =[1]> sau đó
    chơi trống (\ (2 \ ) Bass Drum v) cho (0,25) nhịp
    xóa (1 v) của [chuỗi v]
khác
    Trò chơi kết thúc :: tùy chỉnh
kết thúc
```

Bạn có thể tạo một khối tùy chỉnh khác mà tất cả các nút có thể sử dụng không?

### Trang phục khác

Bạn có thể thấy rằng trò chơi của bạn bắt đầu với nhân vật của bạn hiển thị một trong bốn màu và nhân vật đó luôn hiển thị màu cuối cùng trong chuỗi trong khi người chơi đang lặp lại chuỗi màu?

Bạn có thể thêm một trang phục trắng đơn giản khác cho nhân vật của mình và thêm mã để nhân vật hiển thị trang phục này khi bắt đầu trò chơi và trong khi người chơi đang lặp lại trình tự không?

![ảnh chụp màn hình](images/colour-white.png)

### Cấp độ khó

Bạn có thể cho phép người chơi của mình lựa chọn giữa chơi trò chơi ở 'chế độ dễ' (chỉ sử dụng màu đỏ và màu xanh) và 'chế độ bình thường' (sử dụng cả bốn màu) không?

Nếu bạn muốn, bạn thậm chí có thể thêm chế độ 'cứng', sử dụng trống thứ năm!