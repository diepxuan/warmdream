# WarmDream

WarmDream là thương hiệu chăn ga gối đệm thuộc Công ty TNHH Điệp Xuân. Repo này chứa website giới thiệu thương hiệu WarmDream, tối ưu cho GitHub Pages hoặc static hosting.

WarmDream không phải là một doanh nghiệp độc lập. Thông tin doanh nghiệp, lịch sử hoạt động và đầu mối liên hệ được kế thừa từ hệ thống Điệp Xuân.

## Về Điệp Xuân

Công ty TNHH Điệp Xuân có tiền thân là cửa hàng Điệp Xuân, hoạt động trong lĩnh vực chăn ga gối đệm và nội thất phòng ngủ tại Quảng Bình từ năm 1991. Doanh nghiệp mở rộng sang sản xuất, phân phối và hệ thống showroom; WarmDream là một thương hiệu sản phẩm do Điệp Xuân phát triển.

Thông tin tham khảo chính thức:

- [Hồ sơ tổ chức Điệp Xuân](https://github.com/diepxuan/.github/blob/main/profile/README.md)
- [Website Điệp Xuân](https://www.diepxuan.com/)

## Mục đích

Trang này dùng để giới thiệu WarmDream trong hệ sinh thái Điệp Xuân, trình bày các dòng sản phẩm chăn ga gối đệm, liên kết hồ sơ nhãn hiệu và dẫn khách hàng về đầu mối sản phẩm/liên hệ của Điệp Xuân.

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
- Bước hiện tại tập trung vào landing brand nên chưa hiển thị danh mục/chi tiết sản phẩm; phần này sẽ bổ sung ở bước tiếp theo khi có ảnh và dữ liệu sạch.

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
