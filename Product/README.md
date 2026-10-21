# Agenx — Đặc tả sản phẩm

Nơi quản lý **hành vi sản phẩm**: tính năng làm được gì, màn trông ra sao, bấm vào thì đi đâu.

| | |
|---|---|
| **Sản phẩm** | [`App/`](App) — {{nền tảng}}, 2 tính năng mẫu |
| **Mục lục** | [App/Features.md](App/Features.md) |
| **Nền tảng chung** | [F000](App/Features/F000-Nen-tang-va-quy-uoc-chung/F000-Nen-tang-va-quy-uoc-chung.md) — nguyên tắc, design token, quy ước mã mockup |
| **UI kit** | [Component-Inventory.md](App/Features/F000-Nen-tang-va-quy-uoc-chung/Component-Inventory.md) — tệp phụ của F000 |
| **Mẫu tài liệu** | [`.Template/`](.Template) — mẫu đặc tả · mô tả mockup · release |
| **Quy trình** | [Quy-trinh-khoi-tao.md](Quy-trinh-khoi-tao.md) — mở và chốt một sản phẩm · một tính năng |

## 1. Cấu trúc

```
Product/
├── .Template/                          mẫu đặc tả · mô tả mockup · release
└── {Sản phẩm}/                         App · …
    ├── Features.md                     mục lục tính năng
    ├── Releases.md                     bảng tổng các đợt phát hành
    ├── assets/                         mockup.css — dùng chung
    │
    ├── Features/
    │   ├── {Mã}-{Ten-tinh-nang}/
    │   │   ├── {Mã}-{Ten-tinh-nang}.md          đặc tả
    │   │   ├── {Mã}-{Ten-tinh-nang}.html        mockup — sáng + tối, không JS
    │   │   ├── {Mã}-{Ten-tinh-nang}-Mockup.md   mô tả từng thành phần trên mockup
    │   │   └── history/                         bản đã phát hành, chỉ đọc  (§3)
    │   │       └── v1.0.0/                      ba tệp trên, giữ nguyên tên, đông cứng lúc phát hành
    │   └── {Mã}-{Ten-tinh-nang}/               tính năng tiếp theo
    │
    └── Releases/
        └── Release_v0.1.0.md           hồ sơ một đợt phát hành  (§4)
```

| Cấp | Nghĩa |
|---|---|
| `{Sản phẩm}/` | Một sản phẩm — dải mã, mục lục, mockup và lịch sử phát hành **độc lập** |
| `Features/` | Mọi tính năng của sản phẩm đó, mỗi tính năng một thư mục |
| `{Mã}-{Ten}/` | Một tính năng — ba tệp chính + `history/` |
| `Releases/` | Mỗi đợt phát hành một tệp |

| Tệp | Trả lời | Cho ai |
|---|---|---|
| `.md` | Để làm gì · làm được gì · bấm đi đâu · **vì sao** | Product · QA · tài liệu |
| `.html` | Trông ra sao | Ai cũng — mở bằng trình duyệt |
| `-Mockup.md` | Có thành phần nào · ở đâu · kích thước · trạng thái | Người dựng giao diện |

Tách `-Mockup.md` khỏi đặc tả vì **hai thứ đổi theo hai nhịp**: lý do thiết kế hiếm khi đổi, kích thước trên hình đổi mỗi lần tinh chỉnh.

Tên tệp lặp lại mã đầy đủ (không rút thành `spec.md`) để mở nhiều tab vẫn phân biệt được. Mockup mang mã riêng `F001-A1` theo [F000 §6](App/Features/F000-Nen-tang-va-quy-uoc-chung/F000-Nen-tang-va-quy-uoc-chung.md#6-mã-mockup); bản sáng và tối dùng chung một mã.

**Mở tính năng mới:** lấy số trống tiếp theo → tạo thư mục → chép 2 mẫu ở [`.Template/`](.Template) → dựng mockup → thêm dòng vào [Features.md](App/Features.md). Chi tiết các bước và điều kiện chốt: [Quy-trinh-khoi-tao.md](Quy-trinh-khoi-tao.md).

## 2. Định danh tính năng

Một tính năng (feature) là một chức năng cụ thể của sản phẩm, phục vụ một nhu cầu của người dùng.

```
{tiền tố sản phẩm}{3 chữ số}-{Ten-khong-dau}
        F              001    -Ten-tinh-nang
```

**Tiền tố sản phẩm**

- App = `F`
- Sản phẩm sau lấy chữ cái chưa dùng.

**Mã tính năng** — `{tiền tố}{3 chữ số}`, vd `F001`

- Định danh cho một tính năng, phục vụ một nhu cầu cụ thể của người dùng.
- Một tính năng có thể gồm nhiều màn hình hoặc chức năng con.
  - Màn hình = `{mã tính năng}-{chữ latin in hoa}` — vd `F001-A`
- Mỗi màn hình hoặc chức năng con có thể có nhiều trạng thái biến thể.
  - Trạng thái = `{mã màn hình}{số thứ tự}` — vd `F001-A1`

Quy tắc khác:

- **Mã đã phát ra là vĩnh viễn.** Bỏ tính năng thì để trống mã, không cấp lại.
- Đổi tên tính năng thì đổi tên thư mục, **giữ nguyên số**.

## 3. Phiên bản đặc tả

**Số phiên bản trong bảng đầu tệp spec**: `| **Phiên bản đặc tả** | v1.0.0 — YYYY-MM-DD |`

**Trạng thái đặc tả**: `Nháp → Đã chốt → Đang dựng → Đã phát hành → Đã thay thế`.

| Mức | Khi nào | Người dựng |
|---|---|---|
| **MAJOR** | Hợp đồng hành vi đổi — CTA đổi đích, bỏ trạng thái, đổi luồng | Phải đọc lại |
| **MINOR** | Thêm mà không phá cái cũ — trạng thái, mockup, phím tắt | Đọc phần thêm |
| **PATCH** | Chính tả, viết lại cho rõ, sửa liên kết | Bỏ qua |

| Nơi lưu | Nội dung |
|---|---|
| `history/v{X.Y.Z}/` | **Mỗi đợt phát hành chép một lần, đủ cả ba tệp** của mọi tính năng trong đợt, giữ nguyên tên — mở `history/` là đọc được nguyên trạng bản đã tới tay người dùng mà không cần `git` |
| Cuối tệp spec | Bảng rút gọn, chỉ MAJOR/MINOR, tối đa 10 dòng: `Phiên bản · Ngày · Thay đổi · Đợt phát hành` |
| Git tag | `spec/app/v0.1.0` theo từng đợt — `git show` ra nguyên bộ tài liệu tại thời điểm dựng |

**Nguyên tắc lưu phiên bản**

- Khi một đợt được xác nhận phát hành, chép đặc tả của **từng tính năng trong đợt** vào `Features/{Mã}-{Ten}/history/v{X.Y.Z}/` — `{X.Y.Z}` là **phiên bản đặc tả** của tính năng đó, không phải phiên bản đợt.
- Tài liệu trong `history/` là chỉ đọc.
- Tài liệu ngoài `history/` là "đang phát triển", sửa được.

## 4. Release

Một **đợt phát hành** là một phiên bản sản phẩm tới tay người dùng. Mỗi đợt một tệp `Releases/Release_v{X.Y.Z}.md`, soạn từ [mẫu Release](.Template/Release.template.md); `Releases.md` của sản phẩm giữ bảng tổng.

| Mức | Khi nào |
|---|---|
| **MAJOR** | Đổi cách dùng sản phẩm ở mức người cũ phải học lại |
| **MINOR** | Có ít nhất một tính năng **Mới**, hoặc một spec tăng MAJOR |
| **PATCH** | Chỉ sửa lỗi, không tính năng nào đổi hành vi |

### Quy trình

| # | Bước | Việc | Trạng thái đợt |
|---|---|---|---|
| 1 | **Mở đợt** | Tạo `Release_v{X.Y.Z}.md` từ mẫu, liệt kê tính năng dự kiến | Đang soạn |
| 2 | **Chốt phạm vi** | Kiểm **điều kiện vào đợt** của từng tính năng — spec `Đã chốt`, mockup đủ trạng thái, `-Mockup.md` mô tả hết mã. Chưa đủ thì **đẩy sang đợt sau**. Điền *Phạm vi ngoài* và *Ảnh hưởng chéo* | Đã chốt phạm vi |
| 3 | **Dựng** | Đội dựng theo spec đã chốt. Spec đổi giữa chừng thì tăng phiên bản; **tăng MAJOR là phải xem lại phạm vi đợt** | Đang dựng |
| 4 | **Phát hành** | Điền ngày thực tế, đổi trạng thái các spec sang `Đã phát hành`, làm nốt việc ở *Ảnh hưởng chéo* | Đã phát hành |
| 5 | **Lưu phiên bản** | Chép đặc tả vào `history/v{X.Y.Z}/`, đánh git tag `spec/{sản phẩm}/v{X.Y.Z}`, thêm một dòng vào `Releases.md` | — |

### Luật

- **Ba loại thay đổi**: *Mới* (lần đầu tới tay người dùng) · *Sửa* (spec tăng MAJOR/MINOR) · *Gỡ* (bỏ khỏi bản chạy, spec chuyển `Đã thay thế`, mã vẫn giữ chỗ).
- **Spec chỉ tăng PATCH thì không liệt kê trong đợt.**
- **Một tính năng chỉ *Mới* đúng một lần**; các đợt sau chỉ xuất hiện dạng *Sửa* hoặc *Gỡ*.
- **Đợt chỉ sửa lỗi kỹ thuật**: không cần hồ sơ đợt, chỉ một dòng trong `Releases.md`.

## 5. Việc còn tồn

- Viết [F000](App/Features/F000-Nen-tang-va-quy-uoc-chung/F000-Nen-tang-va-quy-uoc-chung.md) — nguyên tắc, thuật ngữ, design token — rồi chốt.
- Điền hai tính năng mẫu [F001](App/Features/F001-Tinh-nang-mau-1/F001-Tinh-nang-mau-1.md) và [F002](App/Features/F002-Tinh-nang-mau-2/F002-Tinh-nang-mau-2.md); đổi tên thư mục theo tên thật, giữ nguyên số.
