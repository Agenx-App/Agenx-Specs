# {{Sản phẩm}} v{{X.Y.Z}} — Đợt phát hành

<!--
  TEMPLATE — Release
  Đích: Product/{{Sản phẩm}}/Releases/Release_v{{X.Y.Z}}.md

  Nguyên tắc viết:
  · Đây là tài liệu nói chuyện với NGƯỜI NGOÀI ĐỘI — tài liệu, marketing,
    QA, pháp lý. Không chép lại nội dung spec, chỉ trỏ tới spec.
  · Chốt tệp này TRƯỚC khi dựng, không viết lùi sau khi phát hành.
  · Khi đợt được xác nhận phát hành: chép tài liệu đặc tả của từng tính năng
    trong đợt vào `Features/{Mã}-{Ten}/history/v{X.Y.Z}/` (chỉ đọc), rồi đánh git tag.
  · Xoá hết chú thích <!-- --> và các mục không dùng trước khi commit.
-->

| | |
|---|---|
| **Phiên bản** | v{{X.Y.Z}} |
| **Sản phẩm** | {{App · Website · …}} |
| **Ngày phát hành** | {{YYYY-MM-DD}} — *dự kiến / thực tế* |
| **Tình trạng** | {{Đang soạn · Đã chốt phạm vi · Đang dựng · Đã phát hành}} |
| **Git tag** | `spec/{{app}}/v{{X.Y.Z}}` |
| **Đợt trước** | [Release_v{{X.Y.Z-1}}.md](Release_v{{X.Y.Z-1}}.md) |

> {{Một câu: đợt này mang gì tới cho người dùng.}}

## 1. Tính năng trong đợt

| Mã | Tính năng | Loại | Spec | Trạng thái |
|---|---|---|---|---|
| {{F001}} | [{{Tên tính năng}}](../Features/{{F001-Ten-tinh-nang}}/{{F001-Ten-tinh-nang}}.md) | **Mới** | v{{1.0.0}} | {{Đã chốt}} |
| {{F002}} | [{{Tên tính năng}}](../Features/{{F002-Ten-tinh-nang}}/{{F002-Ten-tinh-nang}}.md) | **Sửa** | v{{2.1.0}} | {{Đang dựng}} |
| {{F003}} | [{{Tên tính năng}}](../Features/{{F003-Ten-tinh-nang}}/{{F003-Ten-tinh-nang}}.md) | **Gỡ** | v{{1.3.0}} | {{Đã gỡ}} |

<!--
  Mới  = lần đầu tới tay người dùng. Một tính năng chỉ "Mới" đúng một lần.
  Sửa  = spec tăng MAJOR hoặc MINOR. Chỉ tăng PATCH thì KHÔNG liệt kê —
         với người dùng không có gì đổi.
  Gỡ   = bỏ khỏi bản chạy. Tệp spec giữ lại ở trạng thái "Đã thay thế",
         mã tính năng vẫn giữ chỗ, không cấp lại cho tính năng khác.
-->

### Người dùng thấy gì đổi

<!-- Mỗi tính năng một dòng, viết bằng lời của người dùng — đây là phần
     tài liệu và marketing lấy đi dùng, không phải phần dành cho người dựng. -->

- **{{Tên tính năng}}** — {{Người dùng giờ làm được gì mà trước không làm được}}

## 2. Phạm vi ngoài

<!-- Thứ CỐ Ý chưa làm trong đợt này. Mỗi thứ một dòng lý do.
     Phần hay bị bỏ qua nhất, và là phần chặn câu hỏi "sao cái này chưa có?"
     lặp lại mỗi tuần. -->

| Không làm | Vì sao | Dự kiến |
|---|---|---|
| {{Hạng mục}} | {{Lý do}} | {{Đợt nào, hoặc "chưa xếp"}} |

## 3. Ảnh hưởng chéo

<!-- Bốn câu hỏi bắt buộc trả lời trước khi chốt đợt. -->

| Hỏi | Trả lời | Việc phải làm |
|---|---|---|
| Đổi quyền / nghĩa vụ hai bên? | {{Có · Không}} | {{Phát hành EULA mới · —}} |
| Đổi hiện trạng sản phẩm? | {{Có · Không}} | {{Sửa tài liệu thông tin sản phẩm · —}} |
| Component mới hoặc đổi? | {{Có · Không}} | {{Sửa Component-Inventory.md · —}} |
| Đổi quy ước dùng chung? | {{Có · Không}} | {{Sửa {{X000}} · —}} |

## 4. Điều kiện vào đợt

<!-- Một tính năng chỉ được nằm trong bảng §1 khi đủ cả ba. Đánh dấu từng
     tính năng; còn ô trống thì tính năng đó chưa vào được đợt. -->

| Mã | Spec `Đã chốt`, không còn mục *Còn để ngỏ* chặn việc dựng | Mockup đủ mọi trạng thái, kể cả rỗng và lỗi | `-Mockup.md` mô tả hết các mã |
|---|---|---|---|
| {{F001}} | ✓ | ✓ | ✓ |
| {{F002}} | ✓ | {{—}} | ✓ |

## 5. Xác nhận phát hành

<!-- Làm theo đúng thứ tự này khi đợt được chốt là đã phát hành. -->

| # | Việc | Xong |
|---|---|---|
| 1 | Đổi **Tình trạng** ở đầu tệp thành *Đã phát hành*, điền ngày thực tế | {{☐}} |
| 2 | Đổi trạng thái từng spec trong §1 thành *Đã phát hành* | {{☐}} |
| 3 | Chép đủ ba tệp của từng tính năng vào `Features/{{Mã}}-{{Ten}}/history/v{{X.Y.Z}}/` — `{{X.Y.Z}}` là phiên bản đặc tả của chính tính năng đó, **chỉ đọc, không sửa nữa** | {{☐}} |
| 4 | Đánh git tag `spec/{{app}}/v{{X.Y.Z}}` | {{☐}} |
| 5 | Thêm một dòng vào `Releases.md` của sản phẩm | {{☐}} |
| 6 | Làm các việc phát sinh ở §3 (EULA · Phụ lục · UI kit · {{X000}}) | {{☐}} |

---

**Xem tiếp:** [Bảng tổng các đợt](../Releases.md) · [Mục lục tính năng](../Features.md)
