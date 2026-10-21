# Demo hiệu ứng: trang Giới thiệu Thiết bị mầm non Việt Mỹ

Bản chụp nguyên trang https://website-demo-02.thcmedia.vn/gioi-thieu/ (ngày 21/10/2026). **Không đổi nội dung hay thứ tự section nào.** Demo phủ thêm 6 hiệu ứng, thu gọn khoảng cách giữa các section, chỉnh cỡ chữ theo tab "Size chữ", làm gọn hero, thêm hiệu ứng cho 3 khối Tầm nhìn & Sứ mệnh, Hành trình phát triển, Giá trị cốt lõi, và cho Quy trình tư vấn hiện/ẩn theo chiều cuộn.

**Xem demo:** https://lanvi-commits.github.io/demo-gioi-thieu-thiet-bi-mam-non-viet-my/

Công tắc ở góc dưới trái dùng để bật/tắt bản đề xuất (hiệu ứng, khoảng cách, cỡ chữ, hero, hiệu ứng 3 khối) và so trực tiếp với live. Link có `?fx=0` mở thẳng chế độ Tắt (giống site hiện tại).

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

## Hiệu ứng 3 khối Tầm nhìn & Sứ mệnh · Hành trình phát triển · Giá trị cốt lõi

Ở site hiện tại, cả 3 khối đều đứng yên: không có hover, không có hiệu ứng khi cuộn tới.

| Khối | Khi cuộn tới (chạy 1 lần) | Khi rê chuột (máy tính) |
|---|---|---|
| Tầm nhìn & Sứ mệnh | 2 thẻ hiện dần và trượt lên 16px, thẻ sau trễ 0,1 giây | Icon nhún lên 4px |
| Hành trình phát triển, máy tính (≥ 992px) | Thanh đỏ tự vẽ từ trái sang trong 1 giây. Mốc nào được thanh chạm tới thì bật ra, chữ dưới mốc trượt lên theo. Mốc cuối ("Hiện tại") toả 2 vòng sóng rồi dừng | Icon nhún lên 4px |
| Hành trình phát triển, tablet (768–991px) | Site ẩn thanh đỏ ở khổ này, nên từng mốc hiện dần khi cuộn tới | – |
| Hành trình phát triển, mobile (≤ 767px) | Mốc xếp dọc, icon nằm bên trái. **Thanh đỏ dọc dài ra khi cuộn xuống, ngắn lại khi cuộn lên**: thanh chạm tới mốc nào thì mốc đó vừa lên tới 60% chiều cao màn hình. Từng mốc hiện dần khi cuộn tới | – |
| Giá trị cốt lõi | 5 thẻ hiện dần và trượt lên 16px, các thẻ cùng hàng lệch nhau 0,08 giây | **Cả thẻ nhún lên 4px** kèm bóng nhẹ, viền chuyển đỏ nhạt (bóng và viền lấy đúng hover thẻ Đối tác), icon nhún thêm 4px |

- Tiêu đề H2 của 3 khối giữ nguyên, không có hiệu ứng, giống các section khác.
- Tầm nhìn và Hành trình không nhấc cả thẻ khi rê chuột, vì các thẻ này không bấm được, nhấc lên kèm bóng dễ khiến khách tưởng là link. Riêng Giá trị cốt lõi nhấc cả thẻ theo yêu cầu.
- Thẻ Giá trị cốt lõi dùng thuộc tính `translate` cho hiệu ứng hiện dần và `transform` cho nhún khi hover. Hai thuộc tính độc lập nên thẻ nhún ngay khi rê chuột. Nếu dùng chung `transform`, thẻ phải chờ hết nhịp trễ của hiệu ứng hiện dần (tới 0,32 giây) và nhún chậm 0,6 giây.
- Máy bật "giảm chuyển động": thẻ chỉ hiện dần (0,3 giây), không trượt, không vẽ thanh, không có sóng, icon không nhún. Thanh dọc trên mobile hiện đủ ngay, không chạy theo cuộn.
- **Đổi bố cục Hành trình trên mobile (≤ 767px):** site hiện xếp mốc thành cột, chữ căn giữa ngay dưới icon, nên một thanh dọc chạy giữa sẽ đè lên chữ. Vì vậy demo đổi sang kiểu trục trái, giống khối Quy trình cùng trang: icon nằm trái, chữ căn trái bên phải, thanh chạy qua tâm các icon. Tablet (768–991px) giữ bố cục lưới 2 cột như site.
- Nội dung chỉ bị ẩn khi JS đã chạy. Nếu JS lỗi, cả 3 khối vẫn hiện bình thường như site hiện tại. Thẻ được ẩn bằng `opacity`, nên Google và trình đọc màn hình vẫn đọc đủ chữ.

**Cho DEV:**
- CSS nằm ở mục 10–12 trong khối `<style id="vmx-fx">`. JS nằm trong khối `<script id="vmx-fx-cuon">`: chép nguyên file, nạp ở footer, không cần thư viện. JS chỉ gắn class `is-in` khi phần tử lọt vào màn hình; toàn bộ chuyển động nằm trong CSS.
- Thời điểm từng mốc Hành trình bật ra được **đo theo vị trí thật** của mốc trên thanh, không ghi cứng 3 nhịp. Nhờ vậy khi nhập lại số mốc (sheet đang ghi "Hành trình… nhập liệu chưa đúng"), hiệu ứng vẫn khớp.
- **Bẫy 1:** thanh đỏ (`.timeline::before`) phải khai trạng thái hiện là `clip-path: inset(0 0 0 0)`. Nếu để mặc định `none`, trình duyệt không chuyển mượt được từ `inset()` sang `none` và thanh hiện ra một lần, không vẽ dần.
- **Bẫy 2:** theme có 2 `@keyframes` cùng tên `fadeInUp` (`style-animations.css` trượt 40px; `style-header.css` kèm `translateX(-50%)`). Bản khai sau thắng, nên đừng dùng lại tên này cho hiệu ứng hiện dần.

**Lỗi có sẵn trên site (demo chưa sửa):** từ 991px trở xuống, 2 thẻ Tầm nhìn/Sứ mệnh chỉ cao 50px và **toàn bộ chữ trong thẻ bị cắt mất**, chỉ còn thấy icon (đo cả trên site thật ở 820px và 390px). Nguyên nhân: ở khổ này theme đổi `.cards` sang cột, nhưng `.card` vẫn giữ `flex: 1 1 0` cùng `overflow: hidden`. Kích thước tối thiểu của thẻ vì thế về 0, và thẻ co lại chỉ còn phần đệm. Cách sửa: thêm `.about_vision_mission .card { flex: 0 0 auto }` trong `@media (max-width: 991.98px)`.

## Quy trình tư vấn: hiện khi cuộn xuống, ẩn khi cuộn lên

Áp cho cả desktop và mobile. Ở site hiện tại, khối này đứng yên.

- Cuộn xuống: từng bước (số thứ tự, đoạn nối và thẻ) hiện dần và trượt lên 16px khi lọt vào màn hình. Các bước cùng lọt vào một lúc lệch nhau 0,08 giây.
- Cuộn lên: bước nào trôi xuống dưới mép kích hoạt (10% cuối màn hình) thì ẩn dần, đi ngược đúng đường lúc hiện. Bước trôi ra phía trên màn hình thì giữ nguyên, không ẩn.
- Thời gian hiện 0,6 giây, ẩn 0,4 giây. Máy bật "giảm chuyển động" thì chỉ hiện và mờ dần, không trượt.
- Accordion mở/đóng giữ như site, không đụng tới.

**Cho DEV:** CSS ở mục 13 trong khối `<style id="vmx-fx">`. JS dùng chung file `vmx-fx-cuon` với 3 khối trên; nhóm Quy trình được khai `both: true`, nghĩa là không bỏ theo dõi sau lần hiện đầu. Thanh dọc Hành trình mobile nằm ở mục 11b (CSS) và cuối file JS (biến `--vmx-rail-p` đi từ 0 tới 1).

**Bẫy đo vị trí (thanh dọc mobile):** các mốc đang ẩn có `transform`, nên Chrome lấy chính `.item` làm `offsetParent` của icon. Nếu tính bằng `list.offsetTop + marker.offsetTop` thì mọi icon đo ra 0 và thanh dài 0px. Cách đúng là cộng dồn `offsetTop` ngược lên tới `.timeline`. Không dùng `getBoundingClientRect` vì kết quả lệch theo đoạn trượt 16px.

## Khoảng cách giữa các section (sheet dòng 114)

Khoảng chuẩn **56px** khi màn hình ≥ 992px, **44px** ở 768–991px, **36px** khi ≤ 767px (biến `--vmx-gap`). Trang ngắn đi 405px ở desktop và 493px ở tablet/mobile.

Bảng dưới là khoảng nhìn thấy, đo từ mép nội dung (chữ, ảnh, ô màu) của section trên tới section dưới, ở khổ 1440px:

| Chỗ nối | Live | Demo | Cách làm |
|---|---|---|---|
| Hero → Về Việt Mỹ | 171 | 100 | Mây đáy hero (85px) giữ nguyên; bỏ phần trắng thừa quanh mây (xem mục Hero) |
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

## Hero gọn hơn

- **Bỏ mũi tên "→"** ở cuối đoạn mô tả. Mũi tên này là nút duy nhất để mở phần chữ đang bị cắt còn 4 dòng, nên bản demo **hiện đủ đoạn mô tả** ở mọi khổ.
- **Thu khoảng trong hero** (đơn vị px, theo thứ tự ≥ 992 / 768–991 / ≤ 767):

| Khoảng | Site hiện tại | Demo |
|---|---|---|
| Mép trên hero → nội dung | 88 / 80 / 64 | 32 / 32 / 24 |
| Nhãn "Kể từ năm 2013" ↔ H1 ↔ mô tả | 24 / 24 / 16 | 16 / 16 / 12 |
| Mô tả → nút | 24 / 24 / 16 | giữ nguyên |
| Chữ ↔ ảnh (khi xếp dọc) | – / 32 / 32 | – / 24 / 24 |
| Đáy ảnh/nút → đỉnh mây | 55 / 55 / 35 | 16 / 16 / 12 |

Chiều cao hero: 709 → 614 (1440) · 602 → 553 (1200) · 1031 → 982 (820) · 829 → 943 (390). Ở mobile hero cao hơn trước vì đoạn mô tả giờ hiện đủ (+200px), phần khoảng cách thu lại được 86px.

**Cho DEV:**
- Làm thật thì xoá `<button class="more">` cùng class `is-collapsed` và `data-about-hero-desc` trong template, rồi gỡ `about-hero-story.js`. File này chỉ phục vụ nút mũi tên, gồm cả phần đọc màu nền bằng canvas.
- 32px trong số 88px ở mép trên là **lỗi cascade**. Theme khai `.about_hero_story { padding: 0 }`, nhưng rule chung `section:not(:first-child) { padding-top: 2rem }` trong `style-base.css` có độ ưu tiên cao hơn (0,1,1 so với 0,1,0) nên vẫn chèn thêm 32px.

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
