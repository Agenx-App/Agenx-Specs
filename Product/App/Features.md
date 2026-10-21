# Agenx — Danh mục tính năng

| | |
|---|---|
| **Sản phẩm** | Agenx — {{một câu mô tả sản phẩm}} |
| **Nền tảng** | {{vd: macOS · iOS · Web}} |
| **Giao diện** | **Có** — mỗi tính năng gồm đặc tả `.md`, mockup `.html` và mô tả mockup `-Mockup.md` |
| **Tiền tố** | `F` |
| **Phạm vi** | 3 tài liệu: F000 nền tảng + 2 tính năng mẫu |
| **Tình trạng** | Mới mở — `F000` chưa chốt |

Mỗi thư mục trong [`Features/`](Features) là **một tính năng**, chứa đặc tả `.md` và mockup `.html` cùng tên. Mockup không chạy JavaScript, nên mỗi màn được dựng **thành cặp — bản sáng ở trên, bản tối ngay dưới**. Tài nguyên dùng chung cho mọi mockup nằm ở [`assets/`](assets).

---

## Nền tảng

| Mã | Tính năng | Nội dung |
|---|---|---|
| **F000** | [Nền tảng & quy ước dùng chung](Features/F000-Nen-tang-va-quy-uoc-chung/F000-Nen-tang-va-quy-uoc-chung.md) | Nguyên tắc · thuật ngữ · quy ước tương tác · design token sáng & tối · mã mockup |

## {{Nhóm tính năng 1}}

| Mã | Tính năng | Màn | Nội dung |
|---|---|---|---|
| **F001** | [{{Tính năng mẫu 1}}](Features/F001-Tinh-nang-mau-1/F001-Tinh-nang-mau-1.md) | {{1}} | {{Mô tả một dòng}} |
| **F002** | [{{Tính năng mẫu 2}}](Features/F002-Tinh-nang-mau-2/F002-Tinh-nang-mau-2.md) | {{2}} | {{Mô tả một dòng}} |

---

## Bản đồ màn hình → tính năng

| Màn | Tên | Tính năng |
|---|---|---|
| {{1}} | {{Tên màn}} | [F001](Features/F001-Tinh-nang-mau-1/F001-Tinh-nang-mau-1.md) |
| {{2}} | {{Tên màn}} | [F002](Features/F002-Tinh-nang-mau-2/F002-Tinh-nang-mau-2.md) |

---

## Luồng người dùng chính

```
Mở app
 └─→ F001 {{Tính năng mẫu 1}} ──→ F002 {{Tính năng mẫu 2}}
```

---

## Tình trạng đặc tả

| Mã | Phiên bản | Trạng thái |
|---|---|---|
| F000 | — | Nháp |
| F001 | — | Nháp |
| F002 | — | Nháp |
