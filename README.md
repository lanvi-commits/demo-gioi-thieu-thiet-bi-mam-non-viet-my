# Demo hiệu ứng: trang Giới thiệu Thiết bị mầm non Việt Mỹ

Bản chụp nguyên trang https://website-demo-02.thcmedia.vn/gioi-thieu/ (ngày 21/10/2026). **Không đổi nội dung hay thứ tự section nào.** Demo phủ thêm 6 hiệu ứng, thu gọn khoảng cách giữa các section, chỉnh cỡ chữ theo tab "Size chữ", làm gọn hero, thêm hover cho 3 khối Tầm nhìn & Sứ mệnh, Hành trình phát triển, Giá trị cốt lõi, thêm thanh liền với ô sáng dần theo cuộn cho Quy trình tư vấn và Hành trình (mobile), và hiện mô tả khi rê chuột lên thẻ Mua theo nhóm Thiết bị.

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

**Không có hiệu ứng hiện dần khi cuộn tới.** Các bản v5–v9 từng có: thẻ mờ rồi trượt lên, thanh Hành trình desktop tự vẽ, mốc bật ra, mốc cuối toả sóng. Ngày 22/10 user yêu cầu bỏ, nên từ v10 thẻ, thanh và mốc của 3 khối hiện sẵn như site.

| Khối | Khi cuộn | Khi rê chuột (máy tính) |
|---|---|---|
| Tầm nhìn & Sứ mệnh | Đứng yên như site | Icon nhún lên 4px |
| Hành trình phát triển, máy tính và tablet (≥ 768px) | Đứng yên như site | Icon nhún lên 4px |
| Hành trình phát triển, mobile (≤ 767px) | Mốc xếp dọc, icon nằm bên trái. **Thanh đỏ dọc dài ra khi cuộn xuống, ngắn lại khi cuộn lên.** Icon chưa tới thì tắt (nền trắng, icon xám nhạt); thanh chạm tới thì sáng dần thành tròn đỏ như site, icon đang đứng có quầng mờ; thanh rút lên qua thì tắt lại. Thanh chạy hết thì mốc cuối toả 2 vòng sóng. **Chữ mốc co/giãn theo thanh** (v15, giống Quy trình): mốc 2013 luôn hiện chữ; mốc 2015 và 2016 chưa tới thì chỉ còn icon, thanh chạm icon thì chữ giãn ra, cuộn lên thì co lại. Khối cao 314px khi co, 455px khi giãn; CLS đo khi lăn qua là 0,072 | – |
| Giá trị cốt lõi | Đứng yên như site | **Cả thẻ nhún lên 4px** kèm bóng nhẹ, viền chuyển đỏ nhạt (bóng và viền lấy đúng hover thẻ Đối tác), icon nhún thêm 4px |

- Tầm nhìn và Hành trình không nhấc cả thẻ khi rê chuột, vì các thẻ này không bấm được, nhấc lên kèm bóng dễ khiến khách tưởng là link. Riêng Giá trị cốt lõi nhấc cả thẻ theo yêu cầu.
- Máy bật "giảm chuyển động": icon và thẻ không nhún (thẻ Giá trị vẫn có bóng và viền khi rê chuột). Thanh dọc (Hành trình mobile, Quy trình) hiện đủ ngay, mọi ô sáng sẵn, không có sóng.
- **Đổi bố cục Hành trình trên mobile (≤ 767px):** site hiện xếp mốc thành cột, chữ căn giữa ngay dưới icon, nên một thanh dọc chạy giữa sẽ đè lên chữ. Vì vậy demo đổi sang kiểu trục trái, giống khối Quy trình cùng trang: icon nằm trái, chữ căn trái bên phải, thanh chạy qua tâm các icon. Tablet (768–991px) giữ bố cục lưới 2 cột như site.

**Cho DEV:** hover nằm ở mục 10–12, Hành trình mobile ở mục 11b, trong khối `<style id="vmx-fx">`. Thanh dọc dùng chung JS với Quy trình, xem mục dưới.

**Lỗi có sẵn trên site (demo chưa sửa):** từ 991px trở xuống, 2 thẻ Tầm nhìn/Sứ mệnh chỉ cao 50px và **toàn bộ chữ trong thẻ bị cắt mất**, chỉ còn thấy icon (đo cả trên site thật ở 820px và 390px). Nguyên nhân: ở khổ này theme đổi `.cards` sang cột, nhưng `.card` vẫn giữ `flex: 1 1 0` cùng `overflow: hidden`. Kích thước tối thiểu của thẻ vì thế về 0, và thẻ co lại chỉ còn phần đệm. Cách sửa: thêm `.about_vision_mission .card { flex: 0 0 auto }` trong `@media (max-width: 991.98px)`.

## Quy trình tư vấn: thanh liền, ô số và thẻ hiện dần theo cuộn

Áp cho cả desktop và mobile. Ở site hiện tại, khối này đứng yên, giữa các số chỉ có những đoạn nối mờ rời nhau.

- Một **thanh đỏ liền** chạy qua tâm các số 1 → 5, thay cho các đoạn nối rời. Cuộn xuống thì thanh dài ra, cuộn lên thì ngắn lại. Đầu thanh nằm ở vạch 60% chiều cao màn hình.
- **Ô số** chưa được thanh chạm tới thì để viền rỗng như site. Thanh chạm tới thì ô chuyển dần (0,4 giây) sang tô đỏ đầy, số màu trắng. Ô đang đứng (ô cuối cùng thanh đã chạm) có thêm quầng mờ quanh. Thanh rút lên qua ô nào thì ô đó trở lại viền rỗng.
- **Thẻ của từng bước co và giãn theo thanh**, làm trang ngắn lại hoặc dài ra (v12, user 22/10: "ẩn hiện section thì cũng đồng nghĩa với việc thu gọn và giãn trang").
  - **Bước 1 luôn hiện thẻ** (v13, user 22/10: "đối với bước số 1 hãy auto cố định hiển"): cuộn tới khối là thấy ngay nội dung bước đầu. Ô số 1 vẫn sáng theo thanh như các ô khác.
  - Thẻ bước 2–5 chưa tới thì co hẳn về cao 0. Mỗi bước lúc này chỉ còn vòng số và đoạn nối (76px, mobile 68px), xếp sát nhau.
  - Thanh chạm ô số bước nào thì thẻ bước đó giãn ra trong 0,5 giây, đẩy các vòng bên dưới và section sau xuống. Chữ trong thẻ hiện trễ 0,15 giây, sau khi khung thẻ đã bắt đầu mở.
  - Thanh rút lên qua ô số thì thẻ co lại và trang ngắn đi.
  - Thẻ và ô số luôn cùng trạng thái. Ở 1440px, khối dài 535px khi co hết (bước 1 vẫn hiện) và 752px khi giãn hết.
- Các vòng số rỗng và rãnh mờ luôn hiện, làm đường ray báo trước còn bước phía dưới. Tiêu đề H2 và đoạn mô tả của section đứng yên, giống các section khác.
- Dùng phím Tab tới nút của một thẻ đang co thì thẻ đó mở ra, vòng focus không rơi vào chỗ trống.
- **Lưu ý SEO (Core Web Vitals):** khi thẻ giãn ra, mọi thứ bên dưới bị đẩy xuống, và Chrome tính đó là layout shift. Lăn chuột qua khối ở 1440px, bản v12 (bước 1 cũng co) đo 2 lần được **CLS 0,11 và 0,17** (dao động theo tốc độ cuộn), đều vượt ngưỡng "tốt" là 0,1. Bản v13 để bước 1 luôn hiện nên bớt một thẻ giãn, CLS giảm (xem số đo ở BRAND.md). Bản v11 (thẻ chỉ mờ đi, không co) có CLS bằng 0. Nếu đưa lên site thật, chỉ số CLS của URL /gioi-thieu/ có thể bị Google xếp vào mức "cần cải thiện".
- Site đang tô đầy số của **bước đang mở accordion**. Ở demo, màu số do vị trí cuộn quyết định, nên bỏ kiểu tô đó. Thẻ đang mở vẫn giữ viền đỏ như site.
- Máy bật "giảm chuyển động": thanh hiện đủ, mọi ô sáng sẵn, mọi thẻ hiện sẵn, không chuyển dần.
- Thẻ chỉ bị co khi JS đã chạy. Nếu JS lỗi, mọi thẻ vẫn hiện như site. Thẻ được co bằng chiều cao 0 kèm `overflow: clip`, không dùng `display` hay `visibility`, nên Google và trình đọc màn hình vẫn đọc đủ chữ.
- Lịch sử: v7, v8 làm thẻ mờ theo vị trí riêng của từng thẻ. v9 cho thẻ đứng yên theo video mẫu. v11 cho thẻ mờ đi/hiện ra bám đúng thanh. v12 cho thẻ co/giãn chiều cao.

**Cho DEV:** CSS ở mục 13 (Quy trình) và 11b (Hành trình mobile) trong khối `<style id="vmx-fx">`. JS ở phần "THEO VỊ TRÍ CUỘN" cuối khối `<script id="vmx-fx-cuon">`, dùng chung cho 2 thanh. Mỗi khung cuộn, JS đặt `--vmx-rail-p` (0 tới 1) lên `.timeline` để CSS vẽ thanh bằng `scaleY`, và gắn `.vmx-reached` / `.vmx-current` lên `.item` khi có ô đổi trạng thái. Thẻ `.card` dùng chung `.vmx-reached` đó. JS còn gắn `.vmx-rail-on`, và chỉ khi có class này thẻ mới được co.

Trạng thái đích của thẻ (co về 0 hoặc cao tự nhiên) nằm trong CSS. Đoạn co/giãn dần do hàm `fold()` trong JS chạy bằng WAAPI (`element.animate`), theo 3 bước: đo kích thước đang hiện, đổi class, đo kích thước đích. Không dùng `transition: height` vì chuyển dần từ `auto` sang 0 chỉ chạy được trên Chrome 129+, còn Safari sẽ nhảy cái một. Hết hiệu ứng, thẻ trả về `height: auto`, nên accordion vẫn mở/đóng bình thường. Hiệu ứng chỉ bật sau 2 khung hình kể từ lúc tải trang, để khi tải lại giữa khối thẻ đứng đúng trạng thái ngay.

**Giới hạn trên Safari (theo tài liệu, chưa kiểm trên máy Safari thật):** Safari chưa hỗ trợ cơ chế giữ vị trí cuộn khi nội dung phía trên đổi cao (scroll anchoring, `overflow-anchor`). Vì vậy nếu người xem nhảy cóc từ trên xuống quá khối Quy trình (bấm link neo, tải lại trang ở vị trí bên dưới), các thẻ giãn ra phía trên sẽ đẩy nội dung đang xem xuống. Chrome và Firefox tự bù trừ trường hợp này.

Nền đỏ của ô là gradient, không chuyển dần được, nên được vẽ ở lớp `::before` và chỉ đổi `opacity`. Vị trí được đo lại khi bố cục đổi (ảnh tải xong, mở/đóng accordion, xoay màn hình). Các đoạn `.line` của theme được ẩn bằng `visibility: hidden` để giữ nguyên chiều cao bố cục.

**Bẫy đo vị trí (gặp ở v7):** phần tử bọc ngoài nào có `transform` thì Chrome lấy chính nó làm `offsetParent` của icon. Khi đó, tính bằng `list.offsetTop + marker.offsetTop` cho mọi icon ra 0 và thanh dài 0px. Cách đúng là cộng dồn `offsetTop` ngược lên tới `.timeline`. Không dùng `getBoundingClientRect` cho tâm ô, vì kết quả lệch theo mọi transform đang chạy, kể cả icon đang nhún khi hover.

## Mua theo nhóm Thiết bị: rê chuột lên thẻ thì hiện mô tả (v14)

Ở site hiện tại, chỉ thẻ "Đồ chơi vận động mầm non" có mô tả. Mô tả hiện thành bong bóng đen nằm phía trên thẻ, nên ở hàng đầu bị thanh menu che mất nửa trên, chữ còn bị cắt giữa từ ("…những năm th…"). 10 thẻ còn lại không có gì.

Demo làm theo mẫu thẻ luật sư user gửi:
- Rê chuột lên thẻ thì một lớp navy phủ kín thẻ (cùng màu bong bóng cũ, độ phủ 88%), ảnh phía sau nhoè đi. Tên nhóm ẩn, đoạn mô tả hiện ở giữa thẻ, bên dưới là chữ "Xem thêm →". Lớp phủ mờ dần vào trong 0,3 giây, chữ trượt lên 8px.
- Áp cho cả 11 thẻ, bỏ bong bóng cũ.
- Cả thẻ vẫn là 1 link sang trang danh mục. "Xem thêm" chỉ là chữ gợi ý, không phải link thứ hai.
- Chỉ chạy trên máy có chuột. Trên điện thoại và tablet cảm ứng, thẻ giữ như site: chạm vào là sang trang danh mục, không phải chạm 2 lần. Dùng phím Tab tới thẻ thì mô tả cũng hiện.
- Chữ trắng trên lớp navy đạt tương phản trên 12:1 ở cả 11 màu thẻ. Lớp phủ dùng `position: absolute` và chỉ đổi `opacity`, nên không làm trang xê dịch (không ảnh hưởng CLS).
- Trình đọc màn hình: lớp phủ có `aria-hidden`, còn link trỏ `aria-describedby` vào nó. Tên link vẫn là tên nhóm, mô tả được đọc thành phần mô tả, không bị đọc 2 lần.

**Nội dung mô tả là bản mẫu, cần khách duyệt.** Site chỉ có mô tả danh mục cho Đồ chơi vận động, nên câu của thẻ này lấy đúng từ mô tả đó. 10 nhóm còn lại chưa có mô tả, nên câu được ghép từ các danh mục con đang hiện trên trang danh mục của từng nhóm (đọc ngày 22/10), không thêm số liệu hay chứng nhận nào. Hai nhóm Thông tư 02 và Thông tư 32 viết theo đúng tên danh mục của thông tư.

**Cho DEV:** CSS ở mục 14 trong khối `<style id="vmx-fx">`. Trong theme, chèn vào cuối thẻ `<a class="card">` của component `shop_category_groups`:

```html
<span class="vmx-scg-ov" id="…" aria-hidden="true">
  <span class="vmx-scg-ov__desc">{mô tả danh mục}</span>
  <span class="vmx-scg-ov__more">Xem thêm<i class="fa-light fa-arrow-right" aria-hidden="true"></i></span>
</span>
```

Lấy mô tả từ trường Mô tả của danh mục WooCommerce, cắt gọn khoảng 100 ký tự. Bản live hiện đang ghép cả tiêu đề H2 lẫn đoạn đầu của mô tả nên bị lặp tên nhóm. CSS có `line-clamp` 7 dòng (mobile 5) để phòng câu dài. Có thể bỏ `<span class="card-tip">` cũ.

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
