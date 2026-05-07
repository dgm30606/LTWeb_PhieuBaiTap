Phần A
A1
| Position | Vẫn chiếm chỗ trong flow? | Tham chiếu vị trí | Cuộn theo trang? | Use case |
|----------|---------------------------|-------------------|------------------|----------|
| `static` | có | Mặc định (Không dùng top/left/right/bottom) | có | Mặc định của mọi phần tử |
| `relative` | có | Vị trí gốc của chính nó | có | Dịch chuyển nhẹ, làm mốc tọa độ cho absolute |
| `absolute` | không | Phần tử cha gần nhất có thuộc tính position (khác static) | có | Badge thông báo, dropdown menu, tooltip |
| `fixed` | không | Viewport | không | Nút chat, modal overlay, thanh điều hướng cố định |
| `sticky` | có | Viewport | có | Sticky header, mục lục |

A2
TH1
+-------------------------------------------------------------+
| [   Item 1   ] [   Item 2   ] [   Item 3   ] [   Item 4   ] |
+-------------------------------------------------------------+

TH2
+-----------------------------------+
|  [     Item 1     ] [     Item 2     ]  |
|  [     Item 3     ] [     Item 4     ]  |
|  [     Item 5     ] [     Item 6     ]  |
+-----------------------------------+
TH3
+-------------------------------------------------------------+
| [Item 1]                   [Item 2]                  [Item 3] |
+-------------------------------------------------------------+
TH4
+-------------------------------------------------------------+
| [ 200px ]   [          1fr (Phần còn lại)          ]   [ 200px ] |
+-------------------------------------------------------------+
TH5
+-------------------------------------------------------------+
| [   Item 1   ]   [   Item 2   ]   [   Item 3   ]            |
| [   Item 4   ]   [   Item 5   ]   [   Item 6   ]            |
| [   Item 7   ]   [   Trống    ]   [   Trống    ]            |
+-------------------------------------------------------------+