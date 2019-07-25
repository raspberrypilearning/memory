## Lặp lại trình tự

Bây giờ bạn sẽ thêm bốn nút mà trình phát phải nhấn để lặp lại chuỗi màu.

\--- task \--- Thêm bốn họa tiết mới vào dự án của bạn để thể hiện bốn nút.

+ Chỉnh sửa trang phục của các họa tiết mới để có một sprite trong mỗi bốn màu
+ Đặt các họa tiết theo thứ tự trên sân khấu như trang phục: đỏ, xanh dương, xanh lá cây, vàng

![ảnh chụp màn hình](images/colour-drums.png) \--- /task \---

\--- Nhiệm vụ \--- Thêm mã để sprite đỏ do đó, khi ma được nhấp, nó `chương trình phát sóng`{: class = "block3events"} a 'đỏ' thông điệp tới sprite nhân vật:

![trống đỏ](images/red_drum.png)

```blocks3
    khi sprite này nhấp
    phát (đỏ v)
```

\--- /bài tập \---

A `phát`{: class = "block3events"} giống như một tin nhắn được thông báo qua loa, ví dụ bạn có thể nghe thấy trong trường học hoặc siêu thị. Tất cả các sprite có thể nghe thấy `phát`{: class = "block3events"}, nhưng chỉ có sprite có nhiệm vụ trả lời sẽ làm gì đó.

\--- task \---

Thêm mã tương tự vào các họa tiết màu xanh lam, xanh lục và vàng để làm cho chúng `quảng bá`{: class = "block3events"} về màu sắc của riêng chúng.

\--- /task \---

Bạn có nhớ rằng `phát`{: class = "block3events"} giống như một tin nhắn loa không? Bạn sẽ thêm mã để biến nó thành công việc của nhân vật để đáp ứng với các thông báo `phát`{: class = "block3events"}.

\--- task \---

Khi sprite ký tự của bạn nhận được thông báo `red`{: class = "block3events"}, mã sẽ kiểm tra xem số `1` có ở đầu danh sách `chuỗi`{: class = "block3variables"} không (có nghĩa là rằng `màu đỏ`{: class = "block3events"} là màu tiếp theo trong chuỗi).

Nếu `1` ở đầu danh sách, mã sẽ xóa số đó khỏi danh sách, vì người chơi đã nhớ đúng màu. Nếu không, trò chơi kết thúc và mã cần `dừng tất cả`{: class = "block3control"} để kết thúc trò chơi.

![diễn viên ba lê](images/ballerina.png)

```blocks3
khi tôi nhận được [đỏ v]
nếu <(mục (1 v) của [trình tự v]) =[1]> thì
xóa (1 v) của [trình tự v]
khác
nói [Trò chơi kết thúc!] cho (1) giây
dừng [tất cả v]
kết thúc
```

\--- /task \---

\--- task \--- Thêm vào mã bạn vừa viết để nhịp trống cũng phát khi nhân vật sprite nhận đúng `phát`{: class = "block3events"}.

\--- gợi ý \--- \--- gợi ý \--- Bạn có thể sử dụng các số tương ứng với mỗi màu để chơi đúng nhịp trống không?

+ 1 = đỏ
+ 2 = màu xanh
+ 3 = xanh
+ 4 = màu vàng \--- / gợi ý \--- \--- gợi ý \--- Trên `xóa 1 chuỗi`{: class = "block3variables"}, thêm `phát trống`{: class = " block3sound "} block để phát âm thanh đầu tiên trong danh sách `chuỗi`{: class =" block3variables "}.

\--- / gợi ý \--- \--- gợi ý \--- Đây là mã bạn sẽ cần thêm:

```blocks3
khi tôi nhận được [red v]
nếu <(mục (1 v) của [chuỗi v]) =[1]> thì

+ chơi trống (\ (1 \) Snare Drum v) cho (0,25) nhịp
xóa (1 v ) của [chuỗi v]
khác
nói [Trò chơi kết thúc!] trong (1) giây
dừng [tất cả v]
kết thúc

```

\--- / gợi ý \--- \--- / gợi ý \--- \--- / nhiệm vụ \---

\--- task \--- Sao chép mã bạn đã sử dụng để làm cho sprite nhân vật của bạn phản hồi lại thông báo `red`{: class = "block3events"}. Thay đổi mã trùng lặp để nó gửi thông báo `blue`{: class = "block3events"}. \--- /task \---

Khi sprite trả lời thông báo `blue`{: class = "block3events"}, bit mã nào sẽ giữ nguyên và bit nào sẽ thay đổi? Hãy nhớ rằng mỗi màu có một số tương ứng.

\--- task \--- Thay đổi mã của ký tự sprite để ký tự phản hồi chính xác với thông báo `blue`{: class = "block3events"}.

\--- gợi ý \--- \--- gợi ý \---

Giữ các khối này, nhưng bạn cần thay đổi chúng theo một cách nào đó:

![diễn viên ba lê](images/ballerina.png)

```blocks3
<(mục (1 v) của [chuỗi v]) = [1]>

khi tôi nhận được [red v]

trống chơi (\ (1 \) Snare Drum v) cho (0,25) nhịp
```

\--- / gợi ý \--- \--- gợi ý \--- Đây là cách mã của bạn sẽ tìm kiếm phát sóng `màu xanh`{: class = "block3events"}.

![diễn viên ba lê](images/ballerina.png)

```blocks3
khi tôi nhận được [blue v]
nếu <(mục (1 v) của [chuỗi v]) =[2]> thì
    trống chơi (\ (2 \) Bass Drum v) cho (0,25) nhịp
    xóa (1 v) trong [chuỗi v]
khác
    nói [Trò chơi kết thúc!] trong (1) giây
    dừng [tất cả v]
kết thúc
```

\--- / gợi ý \--- \--- / gợi ý \--- \--- / nhiệm vụ \---

\--- task \--- Sao chép lại mã hai lần (đối với các nút màu lục và màu vàng) và thay đổi các phần cần thiết để nhân vật phản ứng chính xác với `chương trình phát sóng mới`{: class = "block3events"}. \--- /task \---

Nhớ kiểm tra mã! Bạn có thể ghi nhớ một chuỗi năm màu? Là trình tự khác nhau mỗi lần?

Khi người chơi lặp lại chính xác toàn bộ chuỗi màu, danh sách `chuỗi`{: class = "block3variables"} emtpy và người chơi sẽ thắng. Nếu bạn muốn, bạn cũng có thể hiển thị một số đèn nhấp nháy dưới dạng phần thưởng khi danh sách `chuỗi`{: class = "block3variables"} trống.

\--- task \--- Thêm mã này vào cuối ký tự `của bạn khi cờ nhấp vào`{: class = "block3events"} script:

![diễn viên ba lê](images/ballerina.png)

```blocks3
    đợi cho đến < (độ dài của [chuỗi v]) = [0]>
    phát (thắng v) và chờ
```

\--- /task \---

\--- task \--- Chuyển sang Giai đoạn và nhập `máy trống` âm thanh hoặc âm thanh khác mà bạn thích.

[[[generic-scratch3-sound-from-library]]]

\--- /task \---

\--- task \--- Thêm mã này để phát âm thanh và làm cho phông nền đổi màu khi người chơi thắng.

![diễn viên ba lê](images/stage.png)

```blocks3
    khi tôi nhận được [won v]
    âm thanh bắt đầu (trống máy v)
    lặp lại (50)
        thay đổi hiệu ứng [màu v] bằng (25)
        chờ (0,1) giây
    kết thúc
    hiệu ứng đồ họa rõ ràng
```

\--- /task \---