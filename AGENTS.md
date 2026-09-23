# AGENTS.md - Operating Instructions (warmdream)

Operating instructions cho Bột trên dự án `warmdream`. Xem SOUL.md cho bản sắc, IDENTITY.md cho chi tiết identity.

---

## 0. Boot Sequence

Mỗi session PHẢI đọc theo đúng thứ tự trong SOUL.md §4:

1. **SOUL.md** → 2. **USER.md** → 3. **IDENTITY.md** → 4. **TOOLS.md** → 5. `memory/<hôm-nay>.md` → 6. `memory/<hôm-qua>.md` (nếu có) → 7. **MEMORY.md** (chỉ MAIN SESSION) → 8. **README.md** → 9. **CHANGELOG.md**

KHÔNG chỉ đọc AGENTS.md rồi thao tác luôn. Nếu có xung đột, ưu tiên: chỉ dẫn mới nhất của Sếp → SOUL.md → USER.md → IDENTITY.md → AGENTS.md → tài liệu dự án còn lại.

---

## 1. Code Scope

| Ưu tiên | Vị trí | Ghi chú |
|---------|--------|---------|
| Chính | `index.html`, `documents/*.html` | copy + cấu trúc section |
| Chính | `assets/styles.css` | token màu/typography, responsive |
| Hạn chế | `assets/warm-dream-*.{png,svg}` | chỉ thay khi Sếp duyệt bộ asset mới |
| Hạn chế | `LICENSE`, `CNAME` | chỉ Sếp đổi |
| Hạn chế | `documents/trademark-registration.html` | số liệu văn bằng phải đối chiếu nguồn WIPO/IP Việt Nam (`VN4201735449`) |
| Tài liệu | `README.md`, `CHANGELOG.md` | cập nhật khi cấu trúc/cơ chế đổi |

### Quy tắc biên tập nội dung

- Tiếng Việt là ngôn ngữ hiển thị mặc định cho mọi copy người dùng nhìn thấy; thuộc tính `lang="vi"` đã đặt đúng trong `<html>` của cả hai file HTML.
- Số liệu thương hiệu (năm cấp bằng, hiệu lực, mã văn bằng) phải khớp `documents/trademark-registration.html`; trước khi đổi, đọc file thật và xác nhận với Sếp.
- Không thêm framework, build step, hay dependencies runtime; dự án cam kết HTML/CSS thuần theo README.
- Token CSS trong `assets/styles.css` là nguồn sự thật về màu/typography/radius/shadow — KHÔNG hardcode giá trị ngoài token ở view mới.
- Trang chính và trang in A4 có 2 bộ token CSS khác nhau (WarmDream vs dossier) — đó là thiết kế chủ đích, KHÔNG gộp.

---

## 2. Domain Knowledge (WarmDream)

- Website giới thiệu thương hiệu chăn ga gối đệm WarmDream của Công ty TNHH Điệp Xuân.
- Triển khai GitHub Pages; CNAME `warmdream.diepxuan.com`; repo `diepxuan/warmdream`.
- Bốn section người dùng nhìn thấy: hero (`#top`), định vị thương hiệu (`#brand`), nhãn hiệu (`#trademark`), liên hệ (`#contact`).
- `documents/trademark-registration.html` là bản in A4 hồ sơ văn bằng bảo hộ nhãn hiệu Warm Dream S, nguồn WIPO Publish/IP Việt Nam mã `VN4201735449`.
- KHÔNG tự ý thêm form backend, CMS, danh mục sản phẩm; theo README, phần catalogue sẽ bổ sung ở bước tiếp theo khi có ảnh và dữ liệu sạch.

---

## 3. Git Discipline

- Remote: `git@github.com:diepxuan/warmdream.git`, branches track trong `.git/config`: `main`, `feature/product-landing-page`, `build-product-brand-site`. GitHub Pages build từ `main` (root).
- Mỗi task = 1 branch = 1 PR; KHÔNG commit thẳng lên `main`.
- Không tự push / tạo PR / merge; chỉ khi Sếp nói "push đi" / "Em tạo PR đi".
- Merge PR dùng `gh pr merge <N> --squash --delete-branch`, KHÔNG `git merge` local (trừ khi Sếp nói rõ cherry-pick / gộp branch / rebase local).

---

## 4. Task Completion Cycle

Khi nhận task, phải đi hết vòng đời:

1. **Đọc task + source** — `README.md`, `CHANGELOG.md`, file HTML/CSS tương ứng
2. **Audit code** — xác định phần copy/structure/CSS bị ảnh hưởng
3. **Implement** — đúng scope, không tự ý thêm dependency hay build step
4. **Self-review** — preview local, check responsive (mobile + desktop), check in A4 đối với dossier
5. **Verification** — `python3 -m http.server 8080` mở local kiểm chứng; kiểm tra asset path đúng (relative path); kiểm tra link trong nav
6. **Review loop** — fix theo comment
7. **Documentation** — cập nhật `CHANGELOG.md` khi thay đổi release-worthy; cập nhật `README.md` khi cấu trúc/cơ chế đổi; cập nhật `MEMORY.md` khi rút ra bài học
8. **Báo cáo cuối** — bằng chứng cụ thể

### Guard rails

- Nếu thiếu dữ kiện: đọc source trước; nếu vẫn thiếu thì hỏi Sếp
- Khi gặp lỗi: dừng, phân tích nguyên nhân, không vá mù
- KHÔNG tự chạy các lệnh nhóm "Ghi cần xin phép" trong TOOLS.md (`git push`, `gh pr create/merge`, `rm -rf`, network ngoài GitHub)
- Definition of Done: diff sạch, preview local pass, link/asset đúng, `CHANGELOG.md` cập nhật (nếu áp dụng)
- Workspace nằm ở `/data/warmdream/` — ngoài session workspace mặc định của runtime, mọi thao tác ghi phải qua cơ chế escalation, xem TOOLS.md

---

## 5. Sub-Agents

- Gọi là **đệ**
- Mô tả rõ: mục tiêu, input, output, giới hạn quyền
- Đệ không được vượt quyền Bột, KHÔNG được tự push hay thay đổi nội dung thương hiệu