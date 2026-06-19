# WarmDream

WarmDream là trang giới thiệu sản phẩm dạng landing page hiện đại, tối ưu cho GitHub Pages hoặc static hosting.

## Mục đích

Trang này dùng để giới thiệu sản phẩm, trình bày giá trị cốt lõi, tính năng nổi bật và kêu gọi khách hàng liên hệ hoặc dùng thử.

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
│   └── styles.css                          # Giao diện và responsive layout
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

- Tên sản phẩm: `WarmDream`
- Mô tả hero
- Tính năng tại section `#features`
- Lợi ích tại section `#benefits`
- Email liên hệ tại section `#contact`

## Quyết định thiết kế

- Dùng HTML/CSS thuần để triển khai nhanh, dễ host trên GitHub Pages.
- Không dùng framework để giảm độ phức tạp và tránh build step.
- Thiết kế responsive theo hướng mobile-first fallback.
- Màu sắc ấm, gradient hiện đại, phù hợp tên WarmDream.

## Trade-offs

- Không có CMS, chỉnh nội dung bằng code.
- Không có form backend; CTA hiện dùng `mailto:`.
- Không có tối ưu ảnh vì phiên bản hiện tại chưa dùng asset hình ảnh thật.

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
