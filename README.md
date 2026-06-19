# WarmDream

WarmDream là website giới thiệu thương hiệu chăn ga gối đệm WarmDream của Công ty TNHH Điệp Xuân, tối ưu cho GitHub Pages hoặc static hosting.

## Mục đích

Trang này dùng để giới thiệu thương hiệu WarmDream, trình bày các dòng sản phẩm chăn ga gối đệm, liên kết hồ sơ nhãn hiệu và dẫn khách hàng tới các trang sản phẩm/liên hệ.

## Cách sử dụng

Mở trực tiếp file:

```bash
open index.html
```

Hoặc chạy static server đơn giản:

```bash
python3 -m http.server 8080
```

Sau đó truy cập:

```text
http://localhost:8080
```

## Cấu trúc file

```text
.
├── index.html                              # Nội dung landing page
├── assets/
│   ├── styles.css                          # Giao diện và responsive layout
│   ├── warm-dream-logo.png                 # Logo chữ Warm Dream dùng cho hồ sơ in
│   ├── warm-dream-brand.png                # Biểu tượng thương hiệu dự phòng
│   ├── warm-dream-brand.svg                # Brand icon MetallicBrown dùng trong header hồ sơ in
│   └── warm-dream-favicon.svg              # Icon/favicons MetallicBrown dùng cho favicon
│   └── products/                           # Ảnh sản phẩm WarmDream dùng trên landing page
├── documents/
│   └── trademark-registration.html         # Hồ sơ nhãn hiệu Warm Dream S dạng in A4
├── LICENSE
├── CHANGELOG.md
└── README.md
```

## Hồ sơ nhãn hiệu

File `documents/trademark-registration.html` là bản tổng hợp thông tin văn bằng bảo hộ nhãn hiệu Warm Dream S, tối ưu để in A4 hoặc lưu PDF.

Cách in:

1. Mở file bằng trình duyệt.
2. Chọn `Print` hoặc `Ctrl+P`.
3. Destination: máy in hoặc `Save as PDF`.
4. Paper size: A4.
5. Margins: Default hoặc None nếu muốn trình duyệt dùng margin từ file.

Nguồn dữ liệu: WIPO Publish/IP Việt Nam, mã bản ghi `VN4201735449`.

## Dependencies

Không có dependency runtime. Trang dùng HTML và CSS thuần.

## Triển khai GitHub Pages

Với repo `diepxuan/warmdream`, URL GitHub Pages mặc định sẽ là:

```text
https://diepxuan.github.io/warmdream/
```

Cách bật:

1. Vào `Settings` của repo.
2. Chọn `Pages`.
3. Source: `Deploy from a branch`.
4. Branch: `main`.
5. Folder: `/ root`.
6. Save và chờ GitHub build.

## Tùy chỉnh nội dung

Các phần cần chỉnh trong `index.html`:

- Nội dung hero thương hiệu WarmDream
- Danh mục sản phẩm tại section `#products`
- Định vị thương hiệu tại section `#brand`
- Hồ sơ nhãn hiệu tại section `#trademark`
- Link liên hệ/trang Điệp Xuân tại section `#contact`

## Quyết định thiết kế

- Dùng HTML/CSS thuần để triển khai nhanh, dễ host trên GitHub Pages.
- Không dùng framework để giảm độ phức tạp và tránh build step.
- Thiết kế responsive theo hướng mobile-first fallback.
- Màu sắc lấy theo hướng nâu/xanh của nhận diện WarmDream, phù hợp sản phẩm phòng ngủ.

## Trade-offs

- Không có CMS, chỉnh nội dung bằng code.
- Không có form backend; CTA hiện dùng `mailto:`.
- Một số danh mục dùng placeholder vì chưa có đủ ảnh sản phẩm sạch trong kho dữ liệu.

## Troubleshooting

### Trang không hiện trên GitHub Pages

Kiểm tra:

- Repo đã bật Pages chưa.
- Branch Pages có đúng `main` không.
- Folder có đúng `/ root` không.
- File `index.html` nằm ở root repo chưa.

### CSS không load

Kiểm tra file `assets/styles.css` có tồn tại và đường dẫn trong `index.html` là:

```html
<link rel="stylesheet" href="assets/styles.css">
```
