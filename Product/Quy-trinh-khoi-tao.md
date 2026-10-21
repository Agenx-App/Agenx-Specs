# Agenx — Quy trình khởi tạo & chốt

| | |
|---|---|
| **Phạm vi** | Mở một **sản phẩm** mới · mở một **tính năng** mới bên trong sản phẩm — từ lúc chưa có gì tới lúc đặc tả `Đã chốt` |
| **Không bao gồm** | Đợt phát hành — [README §4](README.md#4-release) · Tăng phiên bản đặc tả — [README §3](README.md#3-phiên-bản-đặc-tả) |
| **Nối vào đâu** | Tính năng `Đã chốt` là **đầu vào** của bước *Chốt phạm vi* trong quy trình release |

> Chốt không phải là “viết xong”. Chốt là lời hứa: **từ giờ tới lúc phát hành, thứ này không đổi nữa** — đổi thì phải tăng phiên bản đặc tả và xem lại phạm vi đợt.

## 0. Hai vòng đời

```
SẢN PHẨM      Mới mở ──→ Đã chốt nền tảng ──→ Đang chạy
                 │              │
                 │              └─ từ đây mới được mở tính năng ngoài X000
                 └─ chỉ có khung thư mục, chưa ai dựng theo

TÍNH NĂNG     Nháp ──→ Đã chốt ──→ Đang dựng ──→ Đã phát hành ──→ Đã thay thế
                │          │            │              │
             tự do sửa   §2.5      release §3      release §5
```

Hai trạng thái đầu của mỗi vòng đời là phần tài liệu này mô tả; ba trạng thái sau thuộc quy trình release.

**Ranh giới quyết định ở đâu:** trạng thái ghi trong chính tài liệu, không ghi ở nơi khác — sản phẩm ghi ở `{Sản phẩm}/Features.md`, tính năng ghi ở bảng đầu tệp đặc tả. Không có bảng theo dõi riêng, vì bảng thứ hai luôn lệch với bảng thứ nhất.

---

# Phần A — Khởi tạo một sản phẩm mới

## A1. Khi nào là sản phẩm mới, khi nào chỉ là tính năng

Một **sản phẩm** là thứ có **dải mã, mục lục, lịch sử phát hành độc lập**. Mở sản phẩm mới là mở thêm một dòng đánh số và một dòng release chạy song song — giá phải trả lâu dài, không lấy lại được.

| Dấu hiệu | Sản phẩm mới | Tính năng trong sản phẩm cũ |
|---|---|---|
| Phát hành theo nhịp riêng, số phiên bản riêng | ✓ | — |
| Người dùng cài / truy cập nó như một thứ tách rời | ✓ | — |
| Có thể chết đi mà sản phẩm kia vẫn sống | ✓ | — |
| Chỉ là thêm màn, thêm luồng cho thứ đang có | — | ✓ |
| Dùng chung bản cài, chung bản phát hành | — | ✓ |

Ví dụ: một trang web công khai phát hành theo nhịp riêng là **sản phẩm riêng**; một menu trên thanh hệ thống nằm cùng bản cài của App thì chỉ là **tính năng** của App.

**Nghi ngờ thì để trong sản phẩm cũ.** Tách ra sau vẫn được (đổi tên thư mục, cấp lại mã); gộp lại thì mất mã vĩnh viễn.

## A2. Cấp tiền tố

Tiền tố là **một chữ cái latin in hoa**, chưa ai dùng, đứng trước ba chữ số ([README §2](README.md#2-định-danh-tính-năng)).

| Tiền tố | Sản phẩm | Tình trạng |
|---|---|---|
| `F` | App — {{nền tảng}} | Mới mở — `F000` chưa viết |

**Tiền tố đã phát ra là vĩnh viễn**, kể cả khi sản phẩm bị bỏ — cùng luật với mã tính năng. Chọn chữ gợi nhớ được tên sản phẩm; hết chữ gợi nhớ thì lấy chữ còn trống bất kỳ, đừng ghép hai chữ.

## A3. Các bước

| # | Bước | Việc | Xong thì có |
|---|---|---|---|
| 1 | **Đặt tên & tiền tố** | Chốt tên sản phẩm, chọn chữ cái chưa dùng, thêm một dòng vào bảng ở §A2 | Định danh |
| 2 | **Dựng khung** | `Product/{Sản phẩm}/` với `Features/`, `Releases/`, `Features.md`, `Releases.md`; có giao diện thì thêm `assets/` | Khung rỗng |
| 3 | **Viết `Features.md`** | Bảng đầu tệp: sản phẩm là gì · dạng gì · tiền tố · phạm vi. Ghi rõ **sản phẩm này có giao diện hay không** (§A4) | Mục lục |
| 4 | **Viết `Releases.md`** | Chép khung từ sản phẩm sẵn có; nói rõ **một đợt phát hành ở đây nghĩa là gì** — bản cài mới, hay lần đổi hợp đồng dữ liệu | Bảng tổng rỗng |
| 5 | **Viết `{X}000`** | Tài liệu nền tảng — xem §A4. Đây là bước nặng nhất và là bước không được bỏ | Nền tảng chung |
| 6 | **Nối vào bộ tài liệu** | Thêm sản phẩm vào bảng ở [Product/README.md](README.md) và [README gốc](../README.md); nếu ăn khớp với sản phẩm khác thì trỏ hai chiều | Không còn tài liệu mồ côi |
| 7 | **Chốt nền tảng** | Kiểm §A5, đổi trạng thái `{X}000` sang `Đã chốt` | **Được mở tính năng** |

Bước 1–4 làm trong một buổi. Bước 5 mới là chỗ sản phẩm thực sự hình thành.

## A4. `{X}000` — tài liệu nền tảng

Mỗi sản phẩm có đúng một tài liệu mang số `000`, **không phải một chức năng** mà là thứ mọi tài liệu còn lại được phép viện dẫn thay vì lặp lại.

| Mục | Sản phẩm có giao diện | Sản phẩm không giao diện |
|---|---|---|
| Nguyên tắc bất biến — thứ mọi quyết định sau phải chịu | Bắt buộc | Bắt buộc |
| Các bên liên quan & họ thấy sản phẩm qua đâu | Nên có | Bắt buộc |
| Thuật ngữ dùng thống nhất | Bắt buộc | Bắt buộc |
| Quy ước tương tác, luật ngày/múi giờ, luật không hoàn tác | Bắt buộc | Khi có |
| Design token sáng & tối | Bắt buộc | — |
| Quy ước mã mockup | Bắt buộc | — |
| Hợp đồng với sản phẩm khác | Khi có | Khi có |

Mẫu khung: [F000](App/Features/F000-Nen-tang-va-quy-uoc-chung/F000-Nen-tang-va-quy-uoc-chung.md) — bản cho sản phẩm có giao diện.

**Sản phẩm không có giao diện thì bỏ `.html` và `-Mockup.md`** ở mọi tính năng, và **nói rõ điều đó ngay trong `Features.md`** — người mở thư mục lần đầu phải biết tệp thiếu là do chủ ý, không phải do chưa làm.

**Sản phẩm có giao diện cũng có thể bỏ mockup** nếu `{X}000` ghi rõ quyết định đó — giao diện dựng thẳng rồi đối chiếu với đặc tả. Khi đó bỏ dòng *Quy ước mã mockup* ở bảng trên, và cũng nói rõ trong `Features.md`.

## A5. Điều kiện chốt nền tảng

| Điều kiện | Vì sao |
|---|---|
| Tiền tố đã ghi vào bảng §A2 | Tránh hai sản phẩm cùng chữ cái |
| `Features.md` nói rõ sản phẩm là gì, dạng gì, **có giao diện hay không** | Quyết định tệp nào bắt buộc ở mọi tính năng sau |
| `Releases.md` định nghĩa “một đợt phát hành ở đây” | Không định nghĩa thì đợt đầu tiên sẽ tranh cãi lại từ đầu |
| `{X}000` có **nguyên tắc bất biến** và **thuật ngữ** | Thiếu thì mỗi tính năng tự đặt luật riêng, sáu tháng sau không gộp được |
| Sản phẩm xuất hiện ở cả hai README | Không có lối vào thì tài liệu coi như không tồn tại |
| Ăn khớp với sản phẩm khác đã trỏ hai chiều | Hợp đồng một chiều là hợp đồng sẽ lệch |

Đủ sáu dòng → `{X}000` chuyển `Đã chốt`, sản phẩm chuyển **Đã chốt nền tảng**. Từ đây mới mở tính năng `{X}001` trở đi.

**Chưa đủ thì vẫn mở được thư mục và ghi nháp** — chỉ là không tính năng nào được phép chốt. `App/` đang ở trạng thái này: khung, `F000` và hai tính năng mẫu đều có, nhưng `F000` chưa chốt.

---

# Phần B — Khởi tạo một tính năng mới

## B1. Khi nào là tính năng mới

Một tính năng phục vụ **một nhu cầu cụ thể của người dùng**, có thể gồm nhiều màn hình và nhiều chức năng con ([README §2](README.md#2-định-danh-tính-năng)).

| Tình huống | Xử lý |
|---|---|
| Nhu cầu mới, người dùng gọi tên được nó | **Tính năng mới** |
| Thêm màn cho một nhu cầu đã có tài liệu | Thêm màn vào tính năng cũ — `{Mã}-B`, `{Mã}-C` |
| Thêm một trạng thái của màn đã có | Thêm biến thể — `{Mã}-A2` |
| Tài liệu cũ phình quá, khó đọc | **Không tách** vì lý do độ dài; tách vì nhu cầu khác nhau |

Phép thử: viết được một câu *“người dùng muốn ___ nên họ ___”* mà không nhắc tính năng cũ → tính năng mới. Phải nhắc → nó là một phần của tính năng cũ.

## B2. Cấp mã

```
{tiền tố}{3 chữ số}-{ten-khong-dau}        F001-Ten-tinh-nang
```

- **Lấy số trống tiếp theo** trong sản phẩm đó, không lấp lại số đã bỏ. Số đã bỏ là số chết vĩnh viễn.
- Tên thư mục **không dấu**, gạch nối, viết hoa chữ đầu mỗi từ. Đổi tên tính năng thì đổi tên thư mục, **giữ nguyên số**.
- Cấp mã xong thì **thêm dòng vào `Features.md` ngay**, kể cả khi đặc tả còn rỗng — đó là cách giữ chỗ để người kế tiếp không cấp trùng.

## B3. Các bước

| # | Bước | Việc | Trạng thái |
|---|---|---|---|
| 1 | **Giữ chỗ** | Cấp mã, tạo thư mục, thêm dòng vào `Features.md` | Nháp |
| 2 | **Chép mẫu** | [Feature-Description](.Template/Feature-Description.template.md) và — nếu sản phẩm dùng mockup — [Mockup-Description](.Template/Mockup-Description.template.md), đổi tên đủ mã | Nháp |
| 3 | **Viết mục tiêu & luồng chính** | §1, §3, §4 của mẫu. Viết bằng động từ của người dùng, không phải của hệ thống | Nháp |
| 4 | **Dựng mockup** | `.html` — bản sáng trên, bản tối dưới, không JavaScript. Đủ mọi trạng thái: thường · rỗng · đang tải · lỗi | Nháp |
| 5 | **Viết `-Mockup.md`** | Một mục cho mỗi mã mockup, theo đúng thứ tự trong `.html` | Nháp |
| 6 | **Điền bảng CTA & trạng thái** | §5, §6 — đây là hợp đồng giữa thiết kế và lập trình | Nháp |
| 7 | **Dọn *Còn để ngỏ*** | Mỗi câu hỏi: trả lời, hoặc chuyển xuống §9 *Đã thiết kế chưa dựng*, hoặc khẳng định nó **không chặn việc dựng** | Nháp |
| 8 | **Chốt** | Kiểm §B4, điền phiên bản và trạng thái vào bảng đầu tệp | **Đã chốt** |

Sản phẩm không dùng mockup (không giao diện, hoặc `{X}000` đã bỏ mockup): bỏ bước 4 và 5.

Bước 4 và 6 đi kèm nhau: vẽ một trạng thái mà bảng §6 không có dòng tương ứng là dấu hiệu một trong hai chỗ đang thiếu.

## B4. Điều kiện chốt tính năng

Ba dòng đầu trùng đúng **điều kiện vào đợt** ở [mẫu Release §4](.Template/Release.template.md) — cố ý trùng, để lúc chốt phạm vi đợt không phải kiểm lại từ đầu.

| # | Điều kiện | Kiểm bằng cách |
|---|---|---|
| 1 | Đặc tả không còn mục *Còn để ngỏ* **chặn việc dựng** | Đọc §10: mỗi mục còn lại phải trả lời được “không biết cái này thì vẫn dựng xong chứ?” |
| 2 | Mockup đủ mọi trạng thái, **kể cả rỗng và lỗi** | Đối chiếu §6 với danh mục mockup §2 |
| 3 | `-Mockup.md` mô tả hết các mã trong `.html` | Đếm mã ở hai tệp |
| 4 | Bảng CTA liệt kê **mọi phần tử bấm được**, mỗi dòng có đích | Quét mockup, không bỏ icon-only |
| 5 | Mọi khẳng định thiết kế có **lý do** kèm theo | “Làm thế này” mà không có “vì thế kia” thì lần sau không ai dám sửa |
| 6 | Liên kết §11 trỏ đúng, hai chiều với màn trước / màn sau | Mở thử từng liên kết |
| 7 | Không viện dẫn thứ chưa có trong `{X}000` | Cần quy ước mới → sửa `{X}000` trước, không đặt luật riêng trong tệp tính năng |
| 8 | Bảng đầu tệp điền đủ **Phiên bản đặc tả** và **Trạng thái** | `v1.0.0 — YYYY-MM-DD` · `Đã chốt` |
| 9 | Chú thích `<!-- -->` của mẫu đã xoá hết | grep `{{` và `<!--` trong thư mục tính năng |

Sản phẩm không dùng mockup (không giao diện, hoặc `{X}000` đã bỏ mockup): bỏ dòng 2 và 3, các dòng còn lại giữ nguyên. Dòng 4 khi đó quét trên giao diện thật thay vì mockup.

**Còn ô trống thì tính năng chưa chốt được**, và chưa chốt thì không vào đợt phát hành — không vừa dựng vừa chốt.

## B5. Chốt xong thì đổi gì

| Nơi | Sửa gì |
|---|---|
| Bảng đầu tệp đặc tả | **Phiên bản đặc tả** `v1.0.0 — {ngày}` · **Trạng thái** `Đã chốt` |
| Cuối tệp đặc tả | Mở bảng lịch sử: `v1.0.0 · {ngày} · Bản đầu · —` |
| `Features.md` | Dòng của tính năng: mô tả thật thay cho chỗ giữ chỗ |
| `{X}000` | Nếu tính năng sinh ra quy ước dùng chung mới |
| `Component-Inventory.md` | Nếu có component mới hoặc component cũ đổi (sản phẩm có giao diện) |
| Tính năng liên quan | Thêm liên kết ngược ở §11 của chúng |

Sau đó tính năng **nằm chờ** tới khi một đợt phát hành nhận nó vào phạm vi.

## B6. Chốt rồi mà cần sửa

Chốt không phải khoá. Sửa được, nhưng có giá — giá đó là số phiên bản, theo [README §3](README.md#3-phiên-bản-đặc-tả):

| Sửa gì | Mức | Hệ quả |
|---|---|---|
| Chính tả, viết lại cho rõ, sửa liên kết | **PATCH** | Không ai phải đọc lại. Không liệt kê trong đợt |
| Thêm trạng thái, thêm mockup, thêm phím tắt | **MINOR** | Người dựng đọc phần thêm |
| CTA đổi đích, bỏ trạng thái, đổi luồng | **MAJOR** | Người dựng đọc lại từ đầu. Không phải chép gì: bản đang chạy đã đông cứng ở `history/v{X.Y.Z}/` từ đợt phát hành trước |

**Tính năng đã vào đợt mà spec tăng MAJOR thì phải xem lại phạm vi đợt** — thứ đội đang dựng không còn là thứ đã chốt.

---

## C. Bảng kiểm rút gọn

**Sản phẩm mới**

```
☐ Chữ cái tiền tố chưa ai dùng, ghi vào bảng §A2
☐ Product/{Sản phẩm}/ + Features/ Releases/ Features.md Releases.md (+ assets/ nếu có giao diện)
☐ Features.md nói rõ: là gì · dạng gì · tiền tố · CÓ GIAO DIỆN HAY KHÔNG
☐ Releases.md định nghĩa "một đợt phát hành ở đây là gì"
☐ {X}000 có nguyên tắc bất biến + thuật ngữ (+ design token nếu có giao diện)
☐ Có mặt ở Product/README.md và README gốc
☐ {X}000 → Đã chốt          ⇒ SẢN PHẨM ĐÃ CHỐT NỀN TẢNG
```

**Tính năng mới**

```
☐ Số trống tiếp theo, không lấp số đã bỏ
☐ Thư mục + dòng giữ chỗ trong Features.md
☐ Chép 2 mẫu từ .Template/, đổi tên đủ mã
☐ Mockup .html — sáng trên, tối dưới, đủ trạng thái rỗng và lỗi
☐ -Mockup.md mô tả hết mã trong .html
☐ Bảng CTA đủ mọi phần tử bấm được, mỗi dòng có đích
☐ Mọi khẳng định thiết kế có lý do
☐ §10 không còn mục chặn việc dựng
☐ Xoá hết {{ }} và <!-- --> của mẫu
☐ Bảng đầu tệp: v1.0.0 + Đã chốt     ⇒ TÍNH NĂNG ĐÃ CHỐT
```

---

**Xem tiếp:** [Quy ước chung của Product](README.md) · [Mẫu tài liệu](.Template) · [Quy trình release](README.md#4-release)
