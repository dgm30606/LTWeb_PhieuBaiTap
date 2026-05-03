A1
1. Quá trình khi gõ https://shopee.vn và nhấn Enter
Khi bạn nhấn Enter, trình duyệt và hệ thống mạng sẽ thực hiện hàng loạt thao tác trong chớp mắt. Dưới đây là thứ tự các bước cơ bản nhất:

DNS Lookup (Phân giải tên miền): Trình duyệt không hiểu "shopee.vn", nó chỉ hiểu địa chỉ IP. Đầu tiên, trình duyệt kiểm tra cache (bộ nhớ tạm). Nếu không có, nó sẽ hỏi DNS Server (Hệ thống phân giải tên miền) để dịch URL shopee.vn thành địa chỉ IP của máy chủ (ví dụ: 143.198.x.x).

TCP Handshake (Bắt tay 3 bước TCP): Khi đã có địa chỉ IP, trình duyệt sẽ thiết lập một kết nối tin cậy (TCP connection) với máy chủ Shopee qua quy trình "bắt tay 3 bước" (SYN, SYN-ACK, ACK) để đảm bảo hai bên đã sẵn sàng truyền dữ liệu.

TLS/SSL Handshake (Thiết lập kết nối bảo mật): Vì URL bắt đầu bằng https, trình duyệt và máy chủ sẽ thực hiện thêm một bước "bắt tay" nữa để mã hóa dữ liệu. Hai bên trao đổi chứng chỉ bảo mật và tạo ra các khóa mã hóa để đảm bảo thông tin (như tài khoản, mật khẩu) không bị đánh cắp.

HTTP Request (Gửi yêu cầu HTTP): Sau khi đường truyền an toàn được thiết lập, trình duyệt gửi một yêu cầu GET tới máy chủ để xin tải nội dung của trang chủ (file HTML).

HTTP Response (Nhận phản hồi từ Server): Máy chủ Shopee tiếp nhận yêu cầu, xử lý và gửi trả lại một luồng dữ liệu (HTTP Response). Phản hồi này chứa mã trạng thái (ví dụ: 200 OK) kèm theo nội dung file HTML của trang web.

Rendering (Kết xuất giao diện): Trình duyệt bắt đầu đọc luồng HTML này. Khi gặp các thẻ liên kết đến tài nguyên khác (như file CSS định dạng layout, file JavaScript, hoặc hình ảnh sản phẩm), nó sẽ tiếp tục gửi các request mới để tải chúng về. Cuối cùng, trình duyệt xây dựng DOM Tree (cấu trúc HTML), CSSOM Tree (cấu trúc CSS) và hiển thị (render) trang web hoàn chỉnh lên màn hình cho bạn.

2. Tab Network trong Chrome DevTools
Tab Network là nơi ghi lại tất cả các giao tiếp mạng giữa trình duyệt và máy chủ. Nó cho bạn biết chính xác file nào đang được tải, dung lượng bao nhiêu, mất bao lâu và có bị lỗi (như 404 Not Found) hay không. Đây là nơi bạn sẽ thường xuyên lui tới khi cần kiểm tra xem tại sao một đoạn code CSS Grid của mình không ăn CSS, hay một file ảnh không hiển thị.

Về yêu cầu chụp ảnh màn hình:
Mình là một trí tuệ nhân tạo nên không có giao diện màn hình vật lý hay trình duyệt thực tế để chụp ảnh và vẽ đánh dấu trực tiếp lên đó cho bạn. Tuy nhiên, mình có thể hướng dẫn bạn chính xác vị trí để tìm 3 thông tin này ngay trên máy tính của bạn:

Cách thực hành:
Bạn hãy mở Chrome, vào một trang web bất kỳ (ví dụ Shopee), nhấn F12 (hoặc Ctrl + Shift + I), chọn tab Network và tải lại trang (F5). Bạn sẽ thấy một danh sách dài các request hiện ra.

Status Code của request đầu tiên:

Hãy cuộn lên đầu danh sách (ở khung bên trái/giữa màn hình). Dòng đầu tiên thường chính là tên miền của trang web (ví dụ: shopee.vn).

Nhìn sang cột có tên là Status. Bạn sẽ thấy một con số, thường là 200 (Thành công), 301/302 (Chuyển hướng), hoặc đôi khi là lỗi như 404, 500.

Tổng thời gian load trang (Total load time):

Hãy nhìn xuống khu vực thanh trạng thái (status bar) dưới cùng của tab Network.

Bạn sẽ thấy một dòng tổng hợp dạng như: 100 requests | 5 MB transferred | 15 MB resources | Finish: 2.5 s | Load: 1.2 s. Con số ở phần Load chính là tổng thời gian để trang web tải xong nội dung cơ bản.

Một request trả về file CSS:

Ở thanh công cụ ngay dưới tab Network, bạn sẽ thấy một hàng các bộ lọc (Filter) như: All, Fetch/XHR, JS, CSS, Img, Media...

Hãy nhấp vào chữ CSS. Danh sách bên dưới sẽ lập tức lọc ra và chỉ hiển thị các file stylesheet.

Nhìn vào cột Name, bạn sẽ thấy các file có đuôi .css. Nhìn sang cột Type, nó sẽ hiển thị là stylesheet.

A2
1. Không sử dụng các thẻ cấu trúc vùng (Landmark Tags) như <header>, <main>, <footer>

Lỗi: Dùng <div class="header">, <div class="main">, và <div class="footer">. Thẻ <div> không mang ý nghĩa gì ngoài việc gom nhóm. Google sẽ không biết đâu là nội dung chính (main content), đâu là phần đầu hay phần chân trang.

Cách sửa: Thay bằng các thẻ <header>, <main>, và <footer>.

2. Thiếu thẻ tiêu đề (Heading Tags: H1, H2, H3...)

Lỗi: Tên thương hiệu ("ShopTLU") và tên sản phẩm ("iPhone 16 Pro") đang được đặt trong thẻ <div>. Các công cụ tìm kiếm phụ thuộc rất nhiều vào các thẻ <h1> đến <h6> để lập chỉ mục (index) và hiểu hệ thống phân cấp nội dung của trang web. Một trang web SEO tốt bắt buộc phải có thẻ <h1> đại diện cho chủ đề chính.

Cách sửa: Dùng <h1> cho Logo/Tiêu đề trang và <h2> cho tên sản phẩm.

3. Không sử dụng thẻ điều hướng <nav> và cấu trúc danh sách cho Menu

Lỗi: Menu đang dùng <div class="menu"> và các thẻ <div> con để chứa liên kết. Googlebot không thể nhận diện đây là cụm điều hướng chính của trang web.

Cách sửa: Sử dụng thẻ <nav> kết hợp với danh sách không thứ tự <ul> và các mục <li> để chuẩn hóa cụm menu điều hướng.

4. Dùng <div> cho một đối tượng nội dung độc lập (Sản phẩm)

Lỗi: <div class="product"> đang chứa thông tin của một sản phẩm.

Cách sửa: Nên sử dụng thẻ <article> vì một sản phẩm là một thành phần nội dung có tính độc lập cao, có thể phân phối và tái sử dụng. Các thành phần bên trong như giá tiền có thể dùng thẻ <p>.

A3
[ Hộp 1 ]
Text A Text B
[ Hộp 2 ]
Text C Text D (in đậm)
[ Hộp 3 ]

A4
1. Sự khác nhau giữa <thead>, <tbody> và <tfoot>
Ba thẻ này được sử dụng để gom nhóm các hàng (<tr>) trong một bảng (<table>). Việc này không chỉ giúp source code gọn gàng mà còn mang ý nghĩa ngữ nghĩa (semantics) rất quan trọng để trình duyệt và các công cụ hỗ trợ đọc hiểu dữ liệu.

<thead> (Table Head - Phần đầu bảng):

Dùng để bọc các hàng chứa tiêu đề cột (thường chứa các thẻ <th>).

Nó cho trình duyệt biết đây là hàng định danh cho các cột bên dưới.

Đặc biệt: Khi in một bảng dữ liệu dài phải vắt sang nhiều trang giấy, trình duyệt sẽ tự động lặp lại phần <thead> ở đầu mỗi trang để người đọc không bị mất bối cảnh.

<tbody> (Table Body - Phần thân bảng):

Dùng để chứa nội dung dữ liệu cốt lõi.

Bạn có thể dùng nhiều thẻ <tbody> trong cùng một bảng nếu muốn chia dữ liệu thành các khối độc lập (giúp dễ dàng áp dụng CSS hoặc thao tác bằng JavaScript sau này).

<tfoot> (Table Foot - Phần chân bảng):

Dùng để chứa các hàng tổng kết, tính tổng, hoặc chú thích nằm ở cuối bảng (ví dụ: dòng "Tổng tiền" trong bảng hóa đơn).

Đặc biệt: Trình duyệt có thể ưu tiên render <tfoot> trước ngay cả khi <tbody> chứa lượng dữ liệu khổng lồ chưa kịp tải xong, giúp khung bảng hiển thị hoàn thiện nhanh hơn.

2. Tại sao KHÔNG NÊN dùng <table> để tạo layout trang web?
Vào những năm 2000, việc dùng thẻ <table> để chia cột, tạo bố cục trang web là "tiêu chuẩn". Tuy nhiên, ngày nay điều này tuyệt đối không được sử dụng vì những lý do cốt lõi sau:
 - Sai lệch về ngữ nghĩa và phá hỏng Trợ năng
 - Rất khó để làm Responsive Design
 - Hiệu suất hiển thị rất kém

B3
    Lỗi 1: <!DOCTYPE> thiếu html sửa -> <!DOCTYPE html>
    Lỗi 2: Thiếu thẻ đóng <title> -> thêm </title>
    Lỗi 3: Sai chính tả charset sửa utf8 -> UTS-8
    Lỗi 4: Thẻ đóng h1 sai cú pháp -> </h1>
    Lỗi 5: Sai vị trí thẻ h1 phải di chuyển nào trong thẻ header
    Lỗi 6: Thẻ a đóng sai cú pháp -> </a>
    Lỗi 7: Thẻ img thiếu thuộc tính alt dùng để hiển thị thay thế khi lỗi ảnh
    Lỗi 8: Lỗi lồng 2 thẻ p và b
    Lỗi 9: Thẻ td dùng để chứa dữ liệu thường ở Tên và Giá sửa td -> th
    Lỗi 10: Chỉ được dùng 1 thẻ main đổi thẻ main thứ 2 thành aside để biểu diễn nội dung phụ
    Lỗi 11: Thiếu thẻ p đóng

C1
    