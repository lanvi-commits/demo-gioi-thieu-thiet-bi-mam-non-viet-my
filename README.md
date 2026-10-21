# Demo hiệu ứng: trang Giới thiệu Thiết bị mầm non Việt Mỹ

Bản chụp nguyên trang https://website-demo-02.thcmedia.vn/gioi-thieu/ (ngày 21/10/2026). **Không đổi nội dung, cỡ chữ hay thứ tự section nào.** Demo phủ thêm 6 hiệu ứng, thu gọn khoảng cách giữa các section và chỉnh cỡ chữ theo tab "Size chữ".

**Xem demo:** https://lanvi-commits.github.io/demo-gioi-thieu-thiet-bi-mam-non-viet-my/

Công tắc ở góc dưới trái dùng để bật/tắt bản đề xuất (hiệu ứng, khoảng cách, cỡ chữ) và so trực tiếp với live. Link có `?fx=0` mở thẳng chế độ Tắt (giống site hiện tại).

## 6 hiệu ứng thêm (theo tab "Review tổng thể website")

| # | Khối | Site hiện tại | Demo | Dòng |
|---|---|---|---|---|
| 1 | Ảnh hero | Không zoom | Zoom 1.06 khi hover, ảnh nằm trong khung | 3 |
| 2 | Ảnh "Tại sao chọn Việt Mỹ" | Không zoom (`.frame` có `pointer-events: none`) | Zoom 1.06 khi hover | 3 |
| 3 | Nút "Nhận Tư vấn & Báo giá" | Tối nền, nhấc 2px | Thêm vệt sáng lướt qua, mũi tên nhích phải, nút co 97% khi nhấn | 115 |
| 4 | Nút "Xem dự án đã thực hiện" | Hover nền #fff8f8, gần như không thấy; không có vòng focus | Hover nền đỏ nhạt #fdecec (chữ đỏ 4,63:1); có vòng focus khi dùng phím Tab | 115 |
| 5 | Slide Dự án | Nhảy từng ô mỗi 3,5 giây | Trôi đều liên tục, dừng khi rê chuột | 43 |
| 6 | Slide Đối tác | Nhảy từng ô mỗi 3,5 giây | Trôi đều liên tục, dừng khi rê chuột hoặc khi popover đang mở | 62 |

Trên điện thoại, hiệu ứng hover tự tắt. Máy bật "giảm chuyển động" thì không zoom và slide đứng yên.

## Khoảng cách giữa các section (sheet dòng 114)

Khoảng chuẩn **56px** khi màn hình ≥ 992px, **44px** ở 768–991px, **36px** khi ≤ 767px (biến `--vmx-gap`). Trang ngắn đi 405px ở desktop và 493px ở tablet/mobile.

Bảng dưới là khoảng nhìn thấy, đo từ mép nội dung (chữ, ảnh, ô màu) của section trên tới section dưới, ở khổ 1440px:

| Chỗ nối | Live | Demo | Cách làm |
|---|---|---|---|
| Hero → Về Việt Mỹ | 171 | 112 | Mây đáy hero (85px) giữ nguyên; bỏ phần trắng thừa quanh mây |
| Về Việt Mỹ → Tầm nhìn | 75 | 59 | Section trên chừa 56px, section dưới bỏ padding trên |
| Tầm nhìn → Hành trình | 127 | 87 | Mây đầu Hành trình (85px) chính là khoảng cách, bỏ padding đáy Tầm nhìn |
| Hành trình → Giá trị cốt lõi | 73 | 57 | Như trên |
| Mua theo nhóm → Đội ngũ | 91 | 55 | Như trên |
| Đội ngũ → Tại sao chọn | 73 | 57 | Như trên |
| Tại sao chọn → Quy trình | 64 | 56 | Như trên (nền kem nối liền qua ảnh `.bg-bottom`) |
| Đối tác → Đánh giá | 232 tới tiêu đề | 140 tới tiêu đề | Bỏ trắng thừa phía trên mây vàng, mây giữ nguyên |
| Đánh giá → Hoạt động thực tế | 108 tới tiêu đề | 56 tới tiêu đề | Cùng nền kem |

Các chỗ nội dung sát dải màu đỏ/cam (Thành tựu, Dự án, Tư vấn viên) vốn đã ≤ 56px nên giữ nguyên, chỉ thu ở tablet/mobile nếu vượt 44/36px.

**Bẫy cho DEV:** ảnh hero cần được cắt khi zoom. Không dùng `overflow: hidden` cho `.media`, mà dùng `overflow: clip`. Lý do: ở khổ ≤ 991px, `.media` là phần tử co giãn; `hidden` làm kích thước tối thiểu của nó về 0, khung co lại 0px và mất ảnh hero (bản demo đầu tiên đã dính lỗi này ở tablet/mobile).

## Cỡ chữ (theo tab "Size chữ" của sheet Brief)

Khối `<style id="vmx-co-chu">`. Thang chữ desktop gồm 12 · 14 · 16 · 18 · 20 · 28 · 36, mobile (≤ 767px) gồm 12 · 14 · 16 · 24 · 28. Chỉ sửa những chữ đang lệch bảng, các chữ đã đúng thì giữ nguyên:

| Phần tử | Site hiện tại (desktop / mobile) | Theo bảng |
|---|---|---|
| H1 hero | 48 / 32 | H1 36 / 28 |
| Mô tả dưới H2 (9 section) | 18 / 14–18 | Chữ phụ 14 / 14 |
| Tên card: Tầm nhìn, Giá trị cốt lõi, Đội ngũ, Tại sao chọn, Quy trình | 24 / 18–20, đậm 600 | Tiêu đề nhỏ 18 / 16, đậm 700 |
| Mô tả trong card, mốc Hành trình, accordion, bước Quy trình | 16 / 14 | Chữ phụ 14 / 14 |
| Con số Thành tựu | 44 / 36, đậm 800 | H2 28 / 24, đậm 700 |
| Nhãn số liệu, chức vụ Đội ngũ | 18 / 16 | Chữ phụ 14 / 14 |
| Năm Hành trình ("2013") | 24 / 24, đậm 600 | H3 20 / 16, đậm 700 |
| Tab "Reviews", nút Zalo/QR mobile, breadcrumb | 13–16 / 12–13 | Chữ phụ 14 / 14 |

Độ đậm của Đoạn văn, Chữ phụ và Chữ nhỏ giữ như site, theo ghi chú trong bảng ("đang ok thì khỏi đổi").

## Ghi chú cho DEV

- **CSS:** khối `<style id="vmx-fx">`. Bỏ tiền tố `html.vmx-fx` là chép được sang theme. Phần "CÔNG TẮC DEMO" ở cuối khối không cần chép.
- **Slide trôi:** dùng extension chính chủ `@splidejs/splide-extension-auto-scroll@0.5.3` (bản cho Splide 4.1.4 mà site đang chạy). Cách cài nằm trong phần chú thích đầu khối `<script id="vmx-fx-pre">`.
- **Bẫy cần xử lý:** `components/splide-autoplay.js` ép `autoplay: true` cho mọi slider. Nếu không miễn trừ 2 slider này, kiểu nhảy ô sẽ chạy chồng lên kiểu trôi.

## Khác live ngoài hiệu ứng (chỉ để demo chạy an toàn trên github.io)

- Form báo giá trong popup **không gửi**. Gốc API của CF7 trỏ thẳng về website-demo-02, để nguyên thì bấm gửi sẽ thành yêu cầu báo giá thật.
- Gỡ `external-links.js` (trên github.io nó gắn nofollow cho mọi link), gỡ script theo dõi nguồn khách và AJAX giỏ hàng.
- Ảnh nền hero được nhúng thẳng vào file, để script nút "xem thêm" của site đọc được màu nền (máy chủ THC không gửi CORS).

CSS của site được nhúng sẵn. JS và ảnh vẫn tải từ website-demo-02. `index.html` được dựng bằng `build.py` (lưu ở máy, không có trong repo này), đừng sửa tay.
