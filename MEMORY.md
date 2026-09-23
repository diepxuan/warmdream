# warmdream — Long-term Memory

Memory dài hạn cho Bột trên dự án `warmdream`. Mỗi entry khi có thay đổi cơ chế, sự cố hay bài học đều ghi vào đây. Đọc MEMORY.md trước mọi task lớn để không lặp lại lỗi cũ.

Cập nhật lần cuối: khởi tạo cùng bộ 8 file instruction theo yêu cầu Sếp.

---

## 0. Quy tắc cố định (không theo task, theo SOUL.md/AGENTS.md/TOOLS.md)

- Dự án là static HTML/CSS thuần — KHÔNG thêm framework, build step, dependencies runtime khi chưa được Sếp duyệt.
- Số liệu thương hiệu (năm cấp bằng, hiệu lực, mã văn bằng) khớp `documents/trademark-registration.html`; nguồn gốc `VN4201735449` (WIPO Publish/IP Việt Nam). KHÔNG bịa.
- Hai bộ token CSS (`assets/styles.css` cho trang chính, `<style>` inline trong dossier A4) là thiết kế chủ đích; KHÔNG gộp.
- Workspace OpenClaw: `.openclaw/workspace-state.json` (setupCompletedAt 2026-06-19); workspace root `/data/warmdream/`.
- Remote `git@github.com:diepxuan/warmdream.git`, branch `main`; mỗi task = 1 branch = 1 PR, không commit thẳng `main`, không tự push/PR/merge.
- `.gitignore` hiện có nhiều pattern thừa từ template Laravel; chỉ dọn khi Sếp yêu cầu, ghi nhận trong PR.

---

## 1. Nhật ký thay đổi

### Khởi tạo bộ 8 file instruction

- Sếp yêu cầu đọc file meta agent workspace + review nội dung dự án, bổ sung đủ bộ 8 file instruction đối chiếu với Portal và dsh-zero-trust.
- Trước đó workspace có 6 file mặc định OpenClaw (SOUL, AGENTS, IDENTITY, USER, TOOLS, HEARTBEAT) — toàn bộ là placeholder tiếng Anh, chưa fill Persona/Vibe/Emoji/Avatar.
- Đã rewrite đủ 8 file theo persona Bột dùng chung (tiếng Việt, xưng Sếp/em): `SOUL.md`, `USER.md`, `IDENTITY.md`, `TOOLS.md`, `AGENTS.md`, `HEARTBEAT.md`, `MEMORY.md` (mới), `CLAUDE.md` (mới).
- Boot sequence thêm 2 bước đọc `README.md` và `CHANGELOG.md` làm nguồn sự thật.
- Phần AIGHT-CLIENT trong `TOOLS.md` cũ (chỉ áp dụng cho Aight iOS app) đã được tách khỏi file instruction Bột vì không thuộc scope dự án; ghi nhận ở mục "Tham khảo cũ" để Sếp tiện tra cứu.

---

## 2. Tasks done

(trống)

---

## 3. Bài học rút ra

### 3.1 Lệnh ghi ngoài session workspace

- Workspace warmdream nằm ở `/data/warmdream/`, ngoài session workspace mặc định của runtime.
- Mọi thao tác ghi phải qua cơ chế escalation mới chạy được (xem TOOLS.md).
- Justification mẫu: `Sếp cho phép em rewrite SOUL.md trong /data/warmdream theo persona Bột chuẩn Portal/dsh-zero-trust không?`

### 3.2 File write yêu cầu đọc file hiện có trước

- Với file đã tồn tại, tool write đòi đọc file trong cùng turn trước khi overwrite.
- Bài học: nếu đã đọc ở turn trước, vẫn cần đọc lại (limit 1–5 dòng là đủ) trong turn sẽ ghi.

---

## 4. Backlog / Open questions

### 4.1 Dọn `.gitignore`

- Hiện có nhiều pattern Laravel thừa. Có thể đề xuất PR riêng sau khi Sếp duyệt.

### 4.2 Tích hợp Memory directory

- `memory/` chưa có. Khi cần ghi daily context, tạo `memory/YYYY-MM-DD.md` theo format chuẩn.

---

## Phụ lục A: Tham khảo cũ

- Bản `TOOLS.md` cũ (đã bị rewrite) chứa khối `<!-- AIGHT-CLIENT-START v=8 -->` đến `<!-- AIGHT-CLIENT-END -->` (khoảng dòng 46–205): chỉ áp dụng khi client kết nối qua Aight iOS app (`clientId: "openclaw-ios"`). Khối này mô tả audio/voice, gửi ảnh qua `MEDIA:`, task follow-up watchdog, group chat message format, group chat task protocol. Nội dung kỹ thuật của OpenClaw gateway, không liên quan trực tiếp đến dự án warmdream. Nếu Sếp cần tham khảo lại cho context iOS app, đọc bản trước đó qua `git log -p -- TOOLS.md` hoặc bản backup trong commit rewrite.

## Phụ lục B: Token / chữ ký commit agent

- Author: Bột <bot@diepxuan.corp>
- Tool sandbox: DeepSeek Harness + OpenClaw gateway
- Git remote: `git@github.com:diepxuan/warmdream.git`