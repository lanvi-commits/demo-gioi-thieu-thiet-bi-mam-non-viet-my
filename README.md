# Demo hiệu ứng: trang Giới thiệu Thiết bị mầm non Việt Mỹ

Bản chụp nguyên trang https://website-demo-02.thcmedia.vn/gioi-thieu/ (ngày 21/10/2026). **Không đổi bố cục, nội dung hay cỡ chữ của section nào.** Demo chỉ phủ thêm một lớp hiệu ứng.

**Xem demo:** https://lanvi-commits.github.io/demo-gioi-thieu-thiet-bi-mam-non-viet-my/

Công tắc ở góc dưới trái dùng để bật/tắt lớp hiệu ứng và so trực tiếp với live. Link có `?fx=0` mở thẳng chế độ Tắt (giống site hiện tại).

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

## Ghi chú cho DEV

- **CSS:** khối `<style id="vmx-fx">`. Bỏ tiền tố `html.vmx-fx` là chép được sang theme. Phần "CÔNG TẮC DEMO" ở cuối khối không cần chép.
- **Slide trôi:** dùng extension chính chủ `@splidejs/splide-extension-auto-scroll@0.5.3` (bản cho Splide 4.1.4 mà site đang chạy). Cách cài nằm trong phần chú thích đầu khối `<script id="vmx-fx-pre">`.
- **Bẫy cần xử lý:** `components/splide-autoplay.js` ép `autoplay: true` cho mọi slider. Nếu không miễn trừ 2 slider này, kiểu nhảy ô sẽ chạy chồng lên kiểu trôi.

## Khác live ngoài hiệu ứng (chỉ để demo chạy an toàn trên github.io)

- Form báo giá trong popup **không gửi**. Gốc API của CF7 trỏ thẳng về website-demo-02, để nguyên thì bấm gửi sẽ thành yêu cầu báo giá thật.
- Gỡ `external-links.js` (trên github.io nó gắn nofollow cho mọi link), gỡ script theo dõi nguồn khách và AJAX giỏ hàng.
- Ảnh nền hero được nhúng thẳng vào file, để script nút "xem thêm" của site đọc được màu nền (máy chủ THC không gửi CORS).

CSS của site được nhúng sẵn. JS và ảnh vẫn tải từ website-demo-02. `index.html` được dựng bằng `build.py` (lưu ở máy, không có trong repo này), đừng sửa tay.
