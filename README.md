# Agenx — Specs

Repo tài liệu của **Agenx**, {{một câu: Agenx là gì, chạy trên nền tảng nào}}.
Đây là nơi giữ đặc tả, nhận diện và quy ước — **không chứa mã nguồn**; mã nằm ở
repo `{{Agenx-App}}`.

| Thư mục | Nội dung | Bắt đầu từ |
|---|---|---|
| [`Product/`](Product) | Hành vi sản phẩm: tính năng, mockup, đợt phát hành | [Product/README.md](Product/README.md) |
| [`Brand/`](Brand) | Icon ứng dụng (SVG nguồn + PNG sáng/tối 16–1024), logo | [Brand/README.md](Brand/README.md) |
| [`Technical/`](Technical) | Kiến trúc và quyết định kỹ thuật | *chưa có nội dung* |
| [`Project-Rules.md`](Project-Rules.md) | Quy ước chung của repo | *chưa có nội dung* |

## Cách tài liệu được quản lý

Tài liệu sống theo **một mô hình phiên bản**: bản ở thư mục gốc là bản đang soạn,
sửa tự do; bản đã phát hành được chép vào `history/` và không sửa nữa. Số phiên bản
đặt tại thời điểm phát hành, không tăng theo từng lần sửa.

| | Đơn vị đánh số | Bản đã chốt nằm ở |
|---|---|---|
| Đặc tả tính năng | Mỗi tính năng một số phiên bản | `Product/{Sản phẩm}/Features/{Mã}-{Ten}/history/v{X.Y.Z}/` |
| Đợt phát hành sản phẩm | Theo phiên bản sản phẩm | `Product/{Sản phẩm}/Releases/` |

Tất cả tài liệu viết bằng **tiếng Việt**; bản tiếng Anh, nếu có, là bản dịch tham
khảo.

## Tình trạng

Mới khởi tạo khung. `Product/App` có nền tảng `F000` (còn trống) và hai tính năng
mẫu `F001`, `F002` để điền. Chưa có đợt phát hành nào, `Technical/` còn trống.
