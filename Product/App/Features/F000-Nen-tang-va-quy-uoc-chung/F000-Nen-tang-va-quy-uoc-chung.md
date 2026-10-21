# F000 — Nền tảng & quy ước dùng chung

| | |
|---|---|
| **Mã tính năng** | F000 |
| **Loại** | Nền tảng (áp cho mọi tính năng khác) |
| **Màn hình liên quan** | Toàn bộ |
| **Nội dung** | Tổng quan · nguyên tắc · thuật ngữ · quy ước tương tác · design token · mã mockup |
| **Phiên bản đặc tả** | — |
| **Trạng thái** | Nháp |

Tài liệu này gom những quy tắc mà **mọi tính năng phải tuân theo**. Các tệp F001 trở đi chỉ mô tả phần riêng của từng tính năng và luôn ngầm định các quy tắc ở đây.

---

## 1. Sản phẩm

{{Agenx là gì · cho ai · chạy trên nền tảng nào · dữ liệu nằm ở đâu.}}

{{Ngôn ngữ giao diện bám theo đâu — vd HIG của Apple, Material, hay hệ riêng.}}

## 2. Nguyên tắc bất biến

<!-- Thứ mọi quyết định sau phải chịu. Mỗi nguyên tắc kèm lý do. -->

1. **{{Nguyên tắc}}** — {{Vì sao}}
2. **{{Nguyên tắc}}** — {{Vì sao}}

## 3. Thuật ngữ

<!-- Một khái niệm một từ, dùng thống nhất ở mọi tài liệu và trên giao diện. -->

| Thuật ngữ | Nghĩa | Không dùng |
|---|---|---|
| {{Thuật ngữ}} | {{Định nghĩa}} | {{Từ đồng nghĩa bị cấm}} |

## 4. Quy ước tương tác

- **{{vd: Hành động phá huỷ}}** — {{luôn hỏi xác nhận? có hoàn tác không?}}
- **{{vd: Ngày & múi giờ}}** — {{ngày đổi lúc mấy giờ, theo múi giờ nào}}
- **{{vd: Lưu}}** — {{tự lưu hay bấm Lưu}}

## 5. Design tokens — sáng & tối

<!-- Giá trị ở đây là nguồn; assets/mockup.css chép theo. -->

| Token | Dùng cho | Sáng | Tối |
|---|---|---|---|
| `--s-page` | Nền trang | {{#FFFFFF}} | {{#000000}} |
| `--s-surface` | Nền thẻ, panel | {{…}} | {{…}} |
| `--t-primary` | Chữ chính | {{…}} | {{…}} |
| `--t-secondary` | Chữ phụ | {{…}} | {{…}} |
| `--b-line` | Đường kẻ | {{…}} | {{…}} |
| `--accent` | Màu nhấn | {{…}} | {{…}} |

## 6. Mã mockup

Mỗi mockup trong tệp `.html` mang **một mã, kèm một mô tả ngắn** ngay dưới hình:

```
{Mã tính năng}-{nhóm A,B,C…}{số biến thể}  [mô tả ngắn]
        F001  -        A        2          Trạng thái rỗng
```

- **Chữ cái là nhóm mockup**, đánh theo thứ tự xuất hiện trong tệp HTML; mỗi `<section class="mk-sec">` là một nhóm. Chữ cái chạy liên tục qua các mục trong cùng một tệp.
- **Số là biến thể trong nhóm**, đếm từ `1`.
- **Mã nhóm bỏ số — `F001-A` — là tên gọi của chính màn đó.** Chỉ thêm số khi trỏ vào một trạng thái cụ thể.
- **Một nhóm chỉ chứa đúng một màn.** Sheet và hộp thoại mở ra từ màn đó vẫn thuộc nhóm của nó; màn khác phải có nhóm riêng.
- **Bản sáng và bản tối dùng chung một mã.**
- **Mã không đánh lại** khi chèn thêm mockup: mockup mới nhận số tiếp theo trong nhóm.

Trong HTML, mã dùng lớp `.mk-id`, mô tả ngắn dùng `.mk-lbl`, cả hai nằm trong `.ui-cap`:

```html
<div class="ui-cap"><span class="mk-id">F001-A1</span><b class="mk-lbl">Trạng thái thường</b></div>
```

## 7. Phạm vi không hỗ trợ ở bản này

- {{vd: Đồng bộ nhiều thiết bị}} — {{vì sao chưa}}

## 8. Hợp đồng với sản phẩm khác

{{Không có · hoặc liệt kê sản phẩm khác và trỏ hai chiều.}}

---

**Xem tiếp:** [UI kit](Component-Inventory.md) · [Danh mục tính năng](../../Features.md)
