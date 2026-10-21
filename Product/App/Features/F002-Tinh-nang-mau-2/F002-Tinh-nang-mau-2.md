# F002 — {{Tên tính năng}}

<!--
  TEMPLATE — Feature Description
  Đích: Product/App/Features/F002-Tinh-nang-mau-2/F002-Tinh-nang-mau-2.md

  Nguyên tắc viết:
  · Viết theo hướng NGƯỜI DÙNG: họ muốn gì, thấy gì, làm gì, được gì.
    Không mô tả cấu trúc code, tên class, schema DB.
  · Mỗi khẳng định thiết kế đi kèm LÝ DO. "Làm thế này" mà không có
    "vì thế kia" thì lần sau không ai dám sửa.
  · Mô tả BẢN ĐANG CHẠY. Phần đã thiết kế nhưng chưa dựng gom vào §9.
  · Chi tiết từng thành phần trên mockup KHÔNG nằm ở đây — nằm ở
    F002-Tinh-nang-mau-2-Mockup.md.
  · Xoá hết chú thích \<!-- \--\> và các mục không dùng trước khi commit.
-->

| | |
|---|---|
| **Mã tính năng** | F002 |
| **Màn hình** | {{Màn N — Tên màn, hoặc "Sheet/Popover/Hộp thoại mở từ …"}} |
| **Loại** | {{Cửa sổ chính · vùng nội dung · sheet · popover · hộp thoại · thành phần dùng chung}} |
| **Lối vào** | {{Người dùng tới đây từ đâu — liệt kê mọi đường, link sang F khác}} |
| **Hành động chính** | {{Việc quan trọng nhất người dùng làm ở đây}} |
| **Phiên bản đặc tả** | — |
| **Trạng thái** | Nháp |

> {{Một câu tóm tắt cho người đọc lướt: màn này là gì và vì sao nó tồn tại.}}

## 1. Mục tiêu

{{
Câu mô tả tính năng viết theo hướng user story.
Sau đó giải thích tính năng này có những chức năng gì, mục tiêu, ...
}}

## 2. Mockup

[Xem mockup — bản sáng và bản tối](F002-Tinh-nang-mau-2.html#mockup-1)

Mô tả chi tiết từng thành phần: [F002-Tinh-nang-mau-2-Mockup.md](F002-Tinh-nang-mau-2-Mockup.md)

### Danh mục mockup

<!-- Mã theo quy ước F000 §6: {Mã tính năng}-{nhóm A,B,C…}{số biến thể}.
     Bản sáng và bản tối dùng CHUNG một mã.
     Mỗi dòng: mã · mô tả ngắn · lý do thiết kế nếu có. -->

- **`F002-A1`** · {{Mô tả ngắn}} — {{Lý do thiết kế / điều cần chú ý}}
- **`F002-A2`** · {{Mô tả ngắn}} — {{…}}

## 3. Người dùng làm được gì ở đây

<!-- Danh sách việc, viết bằng động từ của người dùng, không phải của hệ thống.
     Mỗi việc: làm thế nào, và kết quả họ thấy. -->

- **{{Việc 1}}** — {{Thao tác}} → {{Kết quả người dùng thấy}}
- **{{Việc 2}}** — {{…}}

## 4. Luồng chính

<!-- Kịch bản thành công, đánh số theo bước. Mỗi bước một câu.
     Nếu màn có nhiều luồng ngang nhau thì tách 4.1, 4.2… -->

1. {{Người dùng …}}
2. {{Hệ thống …}}
3. {{…}}

**Kết thúc ở:** {{Màn/trạng thái nào}}

## 5. Hành vi từng CTA

<!-- Bảng này là hợp đồng giữa thiết kế và lập trình.
     Liệt kê MỌI phần tử bấm được, gom theo vùng trên màn. -->

| Phần tử | Hành vi khi bấm | Đích |
|---|---|---|
| **{{Vùng — vd: Thanh công cụ}}** | | |
| {{Nút A}} | {{Chuyện gì xảy ra, gồm cả trường hợp đặc biệt}} | {{Màn N / tại chỗ / đóng}} |
| {{Nút B}} | {{…}} | {{…}} |

## 6. Trạng thái

<!-- Mỗi trạng thái: khi nào gặp, người dùng thấy gì, lối ra là gì.
     Trạng thái rỗng và trạng thái lỗi là bắt buộc phải có. -->

| Trạng thái | Khi nào | Người dùng thấy | Lối ra |
|---|---|---|---|
| Thường | {{…}} | {{…}} | — |
| Rỗng | {{Chưa có dữ liệu nào}} | {{Câu chữ + nút gì}} | {{…}} |
| Đang tải | {{…}} | {{…}} | — |
| Lỗi | {{…}} | {{Câu báo lỗi nói rõ chuyện gì và làm gì tiếp}} | {{…}} |

## 7. Quy tắc & ràng buộc

<!-- Luật nghiệp vụ nhìn thấy được từ phía người dùng: giới hạn, kiểm tra
     hợp lệ, thứ tự ưu tiên, cái gì nhớ và nhớ theo phạm vi nào. -->

- **{{Quy tắc}}** — {{Vì sao}}
- **Ghi nhớ:** {{Thứ gì được nhớ lại, nhớ theo tài khoản / theo thiết bị / theo phiên chạy}}

## 8. Bàn phím & trợ năng

- **Phím tắt:** {{Danh sách, ghi rõ cái nào mới là nhãn chưa gắn thật}}
- **Tab order:** {{Thứ tự focus}}
- **Đọc màn hình:** {{Nhãn cho phần tử chỉ có icon}}

## 9. Đã thiết kế, chưa dựng

<!-- Mockup vẽ đủ nhưng bản chạy chưa có. Ghi kèm nguyên lý thiết kế
     để sau này dựng không phải nghĩ lại từ đầu. -->

- **{{Hạng mục}}** — {{Thiết kế ra sao, vì sao chưa dựng}}

## 10. Còn để ngỏ — cần quyết

- **{{Câu hỏi}}** — {{Các phương án và cái giá của từng phương án}}

## 11. Liên quan

| | |
|---|---|
| Màn trước | [F001](../F001-Tinh-nang-mau-1/F001-Tinh-nang-mau-1.md) |
| Màn sau | {{—}} |
| Nền tảng chung | [F000](../F000-Nen-tang-va-quy-uoc-chung/F000-Nen-tang-va-quy-uoc-chung.md) |

---

**Xem tiếp:** [Danh mục tính năng](../../Features.md)

## Lịch sử phiên bản

<!-- Chỉ MAJOR/MINOR, tối đa 10 dòng. Mở bảng khi chốt v1.0.0. -->

| Phiên bản | Ngày | Thay đổi | Đợt phát hành |
|---|---|---|---|
| — | — | — | — |
