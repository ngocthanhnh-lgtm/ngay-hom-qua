# ngày hôm qua

*những mảnh vụn nhớ được*

---

## Cấu trúc

Mọi file nằm **cùng một cấp**, không có thư mục con.

```
index.html                  ← trang chủ: masthead + mục lục
_MAU-BAI.html               ← khung rỗng, copy ra khi viết bài mới
cai-cay-no-ngoi.html        ← bài 01

base.css                    ← KHUNG XƯƠNG: layout, cỡ chữ, khoảng cách
theme-oly.css               ← da Ô LY      (tông NẮNG)
theme-bangden.css           ← da BẢNG ĐEN  (tông ĐÈN VÀNG)
theme-sach.css              ← da SÁCH      (tông XÁM)
theme-kraft.css             ← da KRAFT
theme-baotuong.css          ← da BÁO TƯỜNG

cai-cay-no-ngoi.png         ← ảnh to, dùng trong bài
thumb-cai-cay-no-ngoi.jpg   ← ảnh nhỏ (~500px), dùng ở mục lục
```

**Quy ước tên ảnh:** ảnh của bài `<ten-bai>.html` phải đặt là
`<ten-bai>.png` và `thumb-<ten-bai>.jpg`. Cứ theo vậy là không lạc file.

---

## Nguyên tắc sửa

| Muốn đổi | Sửa file |
|---|---|
| màu · font · hoa văn | `theme-*.css` |
| layout · cỡ chữ · khoảng cách | `base.css` (một lần, cả blog theo) |

⚠ **Đừng bao giờ viết CSS thẳng vào file HTML.** Đó là cách blog phình
ra rồi không sửa nổi. HTML chỉ chứa nội dung.

---

## Thêm một bài mới

1. Copy `_MAU-BAI.html` → đổi tên thành `<ten-bai>.html`
2. Sửa trong file đó:
   - `<title>`
   - dòng `<link ... theme-*.css>` — chọn da theo tông ánh sáng
   - `<h1>` tên bài
   - nội dung trong `<article>`
3. Thêm 2 file ảnh: `<ten-bai>.png` và `thumb-<ten-bai>.jpg`
4. Mở `index.html`, copy khối `<a class="entry">`, đổi 3 chỗ:
   `href` · `src` ảnh thumb · tên bài.
   Xếp theo **dòng thời gian ký ức** (cũ trên, mới dưới) — không phải
   theo ngày đăng.
5. Khi đã có vài bài, xoá khối `<div class="entry blank">` ở cuối mục lục.

---

## Chọn da theo tông ánh sáng

| Tông | Dùng khi | Da |
|---|---|---|
| **NẮNG** | ban ngày, chơi bời — phần lớn truyện | `theme-oly` |
| **ĐÈN VÀNG** | chuyện buổi tối: cúp điện, trốn nhà đi chơi | `theme-bangden` |
| **XÁM** | buồn, chia ly, có người dọn đi, nhịp 2026 | `theme-sach` |

`theme-kraft` và `theme-baotuong` để dành, chưa gán tông.

**Đổi da cả blog cùng lúc:**
```bash
sed -i 's/theme-oly.css/theme-kraft.css/' *.html
```

---

## Class dùng trong bài

| Class | Dùng cho |
|---|---|
| `<p>` | đoạn văn thường |
| `<p class="dialog">` | câu thoại (thụt vào) |
| `<p class="em">` | câu vọng lại trong đầu (in nghiêng) |
| `<figure class="illu">` | hình minh hoạ |
| `<div class="sep">· · ·</div>` | dấu ngắt đoạn giữa bài |

---

## Luật đặt tên bài

- **Không** chứa tên nhân vật. Không "Ngày gặp anh Môn".
- Phải là một **hình ảnh** hoặc một **vật** — để người đọc tự mường tượng.
- Mục lục **không** có đoạn mồi, **không** meta, **không** ngày tháng.
  Chỉ ảnh nhỏ + tên bài.

Đây là một trang hồi ký, không phải trang tin. Mục lục hồi ký thì khô
khốc — chính cái khô đó buộc người ta phải mở ra.
