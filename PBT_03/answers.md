A1 
Inline CSS (trong thẻ):
Ví dụ: <h1 style="color: red;">Tiêu đề</h1>
Ưu/Nhược: Ưu điểm là áp dụng nhanh, độ ưu tiên rất cao. Nhược điểm là lặp code, khó bảo trì, trộn lẫn HTML và CSS.
Khi nào dùng: Tránh dùng, chỉ dùng để debug nhanh.
Internal CSS (trong thẻ <style>):
Ví dụ: <style> h1 { color: red; } </style>
Ưu/Nhược: Code nằm gọn trong 1 file HTML, nhưng không thể tái sử dụng cho trang khác.
Khi nào dùng: Chấp nhận được khi làm các trang prototype (bản mẫu).
External CSS (file .css riêng):
Ví dụ: <link rel="stylesheet" href="styles.css">
Ưu/Nhược: Tái sử dụng được trên nhiều trang, tách biệt hoàn toàn HTML/CSS, dễ bảo trì. Nhược điểm nhỏ là mất thêm 1 request tải file.
Khi nào dùng: Dùng trong 100% các dự án thực tế production.
Câu hỏi thêm: Nếu áp dụng cả 3, Inline CSS sẽ "thắng" vì nó có điểm độ ưu tiên cao nhất (1000 điểm) so với các cách chọn bằng selector thông thường.

A2
h1 → Chọn: ShopTLU
.price → Chọn: 25.990.000đ và 45.990.000đ
#app header → Chọn: Toàn bộ thẻ <header> (bao gồm ShopTLU và 3 menu nav)
nav a:first-child → Chọn: Home
.product.featured h2 → Chọn: MacBook Pro
article > p → Chọn: 25.990.000đ, Mô tả sản phẩm..., 45.990.000đ, Mô tả sản phẩm... (Vì cả class price và mô tả đều là con trực tiếp của article).
a[href="/"] → Chọn: Home
.top-bar.dark h1 → Chọn: ShopTLU

A3
Trường hợp 1 (content-box):
Chiều rộng hiển thị = 400 + (20 * 2) + (5 * 2) = 450px.
Không gian chiếm = 450 + (10 * 2) = 470px.
Trường hợp 2 (border-box):
Chiều rộng hiển thị = 400px.
Kích thước content thực tế = 400 - (20 * 2) - (5 * 2) = 350px.
Không gian chiếm = 400 + (10 * 2) = 420px.
Trường hợp 3 (Margin collapse):
Khoảng cách = 40px.
Giải thích: Khi hai thẻ block nằm kề dọc, margin bị "collapse" (nuốt) — CSS sẽ không cộng dồn mà lấy giá trị lớn hơn giữa 25px và 40px.

A4
Tính điểm: Rule A (p): 0,0,1; Rule B (.price): 0,1,0; Rule C (#main-price): 1,0,0; Rule D (p.price): 0,1,1.
Màu hiển thị: Màu đỏ vì Rule C có ID selector (điểm 100) cao nhất.
Thêm Inline Style: Chữ sẽ có Màu cam. Inline style luôn mạnh hơn ID (điểm 1000).
Thêm !important vào Rule A: Chữ sẽ có Màu đen. !important có sức mạnh vô cực, ghi đè tất cả các luật bình thường kể cả inline style.

C1