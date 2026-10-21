# F001 — {{Tên tính năng}} · Mô tả mockup

<!--
  TEMPLATE — Mockup Description
  Đích: Product/App/Features/F001-Tinh-nang-mau-1/F001-Tinh-nang-mau-1-Mockup.md

  Nguyên tắc viết:
  · Tệp này mô tả TỪNG THÀNH PHẦN NHÌN THẤY trên mockup — đọc tệp này
    là dựng lại được màn mà không cần mở trình duyệt.
  · Một mục cho một mã mockup, theo đúng thứ tự xuất hiện trong .html.
  · Mỗi thành phần: tên · vị trí · nội dung · kiểu dáng · trạng thái.
    LÝ DO thiết kế không nằm ở đây — nằm ở tệp feature description.
  · Chỉ ghi con số khi con số là chủ ý thiết kế (cỡ chữ, chiều cao hàng,
    bề rộng cột). Đừng chép mọi giá trị CSS.
  · Bản sáng và bản tối dùng chung một mã: chỉ ghi chỗ hai bản KHÁC nhau.
  · Xoá hết chú thích <!-- --> và các mục không dùng trước khi commit.
-->

| | |
|---|---|
| **Mã tính năng** | F001 |
| **Tệp mockup** | [F001-Tinh-nang-mau-1.html](F001-Tinh-nang-mau-1.html) |
| **Đặc tả** | [F001-Tinh-nang-mau-1.md](F001-Tinh-nang-mau-1.md) |
| **Số mockup** | {{N}} mã, {{M}} nhóm |
| **Khung dựng** | {{vd: cửa sổ 1100 × 700 · bản sáng trên, bản tối dưới}} |

## 0. Quy ước chung của tệp mockup

<!-- Những gì đúng cho MỌI mockup trong tệp. Viết một lần ở đây để các
     mục dưới không phải lặp lại. -->

- **Bố cục khung:** {{vd: sidebar 178px cố định bên trái · toolbar 44px · vùng nội dung co giãn}}
- **Lưới & khoảng cách:** {{vd: padding vùng nội dung 20px · khoảng cách giữa các khối 16px}}
- **Chữ:** {{vd: nội dung 13px · tiêu đề mục 11px in hoa, letter-spacing .06em}}
- **Màu:** lấy từ design token ở [F000](../F000-Nen-tang-va-quy-uoc-chung/F000-Nen-tang-va-quy-uoc-chung.md). {{Ghi ngoại lệ nếu có}}
- **Dữ liệu mẫu:** {{vd: tên người dùng, dữ liệu mẫu — dùng nhất quán ở mọi mockup}}
- **Chưa mô phỏng được:** {{vd: hiệu ứng chuyển cảnh, animation}}

---

## `F001-A1` · {{Mô tả ngắn}}

<!-- Lặp lại khối này cho mỗi mã mockup. -->

**Tình huống:** {{Người dùng vừa làm gì để màn ở đúng trạng thái này}}
**Neo:** [#mockup-1](F001-Tinh-nang-mau-1.html#mockup-1)

### Bố cục

{{Một đoạn ngắn tả tổng thể: có mấy vùng, xếp theo chiều nào, vùng nào chiếm bao nhiêu.}}

```
┌─────────┬──────────────────────────────┐
│ {{vùng}}│ {{vùng}}                     │
├─────────┼──────────────────────────────┤
│         │ {{vùng}}                     │
└─────────┴──────────────────────────────┘
```

### Thành phần

| # | Thành phần | Vị trí | Nội dung hiển thị | Kiểu dáng | Tương tác |
|---|---|---|---|---|---|
| 1 | {{Tên — vd: Thanh tiêu đề}} | {{Đỉnh vùng nội dung, full-bleed}} | {{Chữ thật trên mockup}} | {{Cỡ chữ · đậm nhạt · nền · đường kẻ}} | {{Bấm được không, hover ra sao}} |
| 2 | {{…}} | {{…}} | {{…}} | {{…}} | {{…}} |

<!-- Đánh số khớp với thứ tự đọc trên màn: trên → dưới, trái → phải.
     Nếu một thành phần có cấu trúc con (hàng trong bảng, mục trong menu)
     thì tách thành bảng con ngay dưới. -->

#### {{Thành phần phức tạp — vd: Hàng trong danh sách}}

| Phần | Nội dung | Kiểu dáng |
|---|---|---|
| {{Cột 1}} | {{…}} | {{14px, đậm hơn phần còn lại}} |
| {{Cột 2}} | {{…}} | {{12.5px}} |

### Trạng thái vẽ trong mockup này

- **{{Hover / chọn / tắt / rỗng}}** — {{Phần tử nào đang ở trạng thái đó và trông ra sao}}

### Khác biệt bản tối

- {{Chỗ nào không chỉ là đảo màu theo token — vd: đường kẻ dùng token khác, ảnh đổi phiên bản}}
- {{Không có khác biệt → ghi "Chỉ đảo màu theo token, không khác gì về bố cục."}}

### Ghi chú dựng

- {{Điều người dựng dễ làm sai: chiều cao cố định, thứ tự z, chỗ tràn chữ, chỗ cắt bằng ellipsis}}

---

## `F001-A2` · {{Mô tả ngắn}}

{{Lặp lại cấu trúc trên.}}

---

## Phụ lục — bản đồ mã mockup

| Mã | Nhóm | Mô tả ngắn | Neo |
|---|---|---|---|
| `F001-A1` | {{A — tên nhóm}} | {{…}} | [#mockup-1](F001-Tinh-nang-mau-1.html#mockup-1) |
| `F001-A2` | {{A}} | {{…}} | [#mockup-2](F001-Tinh-nang-mau-1.html#mockup-2) |

<!-- Mã đã phát ra là mã vĩnh viễn: chèn mockup mới thì lấy số tiếp theo
     trong nhóm, không đánh lại từ đầu (F000 §6). -->

---

**Xem tiếp:** [Đặc tả F001](F001-Tinh-nang-mau-1.md) · [Danh mục tính năng](../../Features.md)
