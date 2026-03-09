# 🤖 Claude Code Agent Teams — Hướng dẫn cài đặt và sử dụng

> ✍️ **Tác giả:** Senior BA team VNG
> 🗓️ **Ngày viết:** Tháng 3/2026
> 🎯 **Dành cho:** BA đã cài Claude Code, muốn dùng nhiều AI agent cùng lúc để tăng tốc công việc
> 📚 **Series:** Becoming an AI-Augmented BA — Article 4
> ⚠️ **Yêu cầu:** Đã cài đặt Claude Code theo [hướng dẫn trước](bắt-đầu-với-claude-code.md)

---

## 🌈 Lời mở đầu — Agent Teams là gì?

Bình thường khi dùng Claude Code, bạn chat với **1 AI duy nhất**. AI đọc file, trả lời, sửa file — mọi thứ diễn ra tuần tự, từng bước một.

Nhưng hãy tưởng tượng thế này: thay vì 1 người làm tất cả, bạn có **cả một team AI** làm việc cùng lúc 🤯

**Agent Teams** cho phép bạn:

- 👥 **Chạy nhiều Claude Code cùng lúc** — mỗi agent làm một việc riêng
- 🧑‍💼 **Có 1 "Team Lead" điều phối** — phân việc, tổng hợp kết quả
- 💬 **Các agent chat với nhau** — trao đổi, chia sẻ kết quả trực tiếp
- ⚡ **Song song hóa công việc** — việc 1 tiếng giờ chỉ còn 15 phút

> 💡 **Ví dụ thực tế cho BA:**
> Bạn cần review 5 file PRD cùng lúc? Thay vì AI đọc từng file một (chậm), Agent Teams sẽ spawn 5 agent — mỗi agent đọc 1 file — rồi tổng hợp kết quả. Nhanh gấp 5 lần! 🚀

---

---

# 🛠️ CÀI ĐẶT — Bật Agent Teams

> ⚠️ **Yêu cầu trước:** Bạn phải đã cài Claude Code CLI và đăng nhập thành công. Nếu chưa, quay lại [bài hướng dẫn cài đặt Claude Code](bắt-đầu-với-claude-code.md).

Agent Teams là tính năng **experimental** — cần bật thủ công qua cấu hình.

---

## Cách 1 — Cấu hình qua file settings (KHUYẾN NGHỊ)

Đây là cách **một lần là xong**, không cần nhớ gõ lệnh mỗi khi mở Claude Code.

### Step 1 — Tìm file settings

File settings nằm ở:

```
Windows:  C:\Users\<tên-user>\.claude\settings.json
Mac:      ~/.claude/settings.json
Linux:    ~/.claude/settings.json
```

> 💡 **Mẹo:** Nếu bạn không thấy folder `.claude`, hãy mở terminal và chạy `claude` một lần rồi thoát ra — Claude Code sẽ tự tạo folder này.

### Step 2 — Mở và chỉnh sửa file

Mở file `settings.json` bằng editor bất kỳ (VS Code, Cursor, Notepad...) và thêm phần `env`:

**Nếu file đang trống hoặc chỉ có `{}`:**

```json
{
  "env": {
    "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1"
  }
}
```

**Nếu file đã có nội dung sẵn (ví dụ):**

```json
{
  "effortLevel": "low",
  "env": {
    "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1"
  }
}
```

> ⚠️ **Lưu ý format JSON:**
> - Mỗi dòng cần dấu phẩy `,` ở cuối (trừ dòng cuối cùng trong block)
> - Dùng dấu ngoặc kép `"` cho cả key và value
> - Nếu không chắc, copy đoạn mẫu phía trên và chỉnh lại

### Step 3 — Khởi động lại Claude Code

Đóng Claude Code hoàn toàn (gõ `/exit` hoặc `Ctrl+C`), rồi mở lại.

```
✅ Success: Claude Code khởi động bình thường → Agent Teams đã sẵn sàng
❌ Error: "Unexpected token" → Kiểm tra lại format JSON (thiếu dấu phẩy, ngoặc?)
```

---

## Cách 2 — Cấu hình qua biến môi trường (dùng tạm)

Nếu bạn chỉ muốn **thử nhanh** mà không sửa file:

**Windows (PowerShell):**
```powershell
$env:CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS = "1"
claude
```

**Mac/Linux (Terminal):**
```bash
export CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1
claude
```

> ⚠️ **Lưu ý:** Cách này chỉ có hiệu lực trong phiên terminal hiện tại. Đóng terminal là mất. Khuyến nghị dùng **Cách 1** để cấu hình vĩnh viễn.

---

## ✅ Cài đặt — Tóm tắt

| Cách | Việc cần làm | Hiệu lực |
|------|-------------|-----------|
| Cách 1 (file) | Thêm `env` vào `settings.json` → restart Claude Code | Vĩnh viễn ✅ |
| Cách 2 (biến MT) | Export biến môi trường → chạy `claude` | Chỉ phiên hiện tại |

---

---

# 🚀 SỬ DỤNG — Chạy Agent Teams đầu tiên

Sau khi bật tính năng, bạn chỉ cần **mô tả task bằng ngôn ngữ tự nhiên** — Claude sẽ tự tạo team và phân việc.

---

## Step 1 — Mở Claude Code và giao task

Mở Claude Code trong terminal hoặc editor, rồi gõ task mà bạn muốn nhiều agent cùng làm:

```
"Review 3 file PRD trong folder docs/ — mỗi file kiểm tra acceptance criteria,
edge cases, và dependencies. Sau đó tổng hợp kết quả."
```

Claude sẽ tự động:
1. 🧑‍💼 Tạo **Team Lead** (chính Claude đang chat với bạn)
2. 👥 Spawn **teammates** (mỗi agent nhận 1 file PRD)
3. 📋 Phân chia task rõ ràng
4. 📊 Tổng hợp kết quả khi tất cả hoàn thành

---

## Step 2 — Theo dõi tiến trình

Khi team đang chạy:

- **`Shift+Down`** — Chuyển qua lại giữa các teammates để xem tiến trình
- **Gõ tin nhắn** — Gửi chỉ dẫn thêm cho teammate đang chọn
- **Đợi kết quả** — Team Lead sẽ tổng hợp và báo cáo khi xong

```
✅ Success: Thấy nhiều agent đang chạy, mỗi agent có task riêng
❌ Không thấy gì khác lạ? → Kiểm tra lại đã bật env variable chưa (xem phần Cài đặt)
```

---

## Step 3 — Một số lệnh hữu ích khi dùng Teams

| Hành động | Cách làm |
|-----------|----------|
| Xem danh sách teammates | Hỏi Claude: "Liệt kê teammates hiện tại" |
| Giao thêm việc | Hỏi Claude: "Tạo thêm 1 teammate để review file X" |
| Nhắn riêng 1 teammate | Dùng `Shift+Down` chọn teammate → gõ tin nhắn |
| Dừng 1 teammate | Hỏi Claude: "Shut down teammate đang review file Y" |
| Dọn dẹp team | Hỏi Claude: "Clean up team" |

---

---

# 💡 USE CASES CHO BA — Khi nào nên dùng Agent Teams?

## ✅ NÊN dùng khi:

### 1. Review nhiều tài liệu cùng lúc

```
"Review tất cả PRD trong folder docs/.
Mỗi file kiểm tra: có đủ acceptance criteria không, edge cases đã cover chưa,
dependencies có rõ ràng không. Tổng hợp kết quả thành 1 bảng."
```

### 2. Research nhiều hướng song song

```
"Mình cần tìm hiểu 3 giải pháp payment gateway cho VN: Momo, VNPay, ZaloPay.
Mỗi teammate research 1 giải pháp: API docs, pricing, limitations.
Sau đó so sánh và đề xuất."
```

### 3. Tạo nhiều document cùng lúc

```
"Tạo user stories cho 4 module: Login, Profile, Payment, Notification.
Mỗi teammate viết user stories cho 1 module theo format Given-When-Then."
```

### 4. Debug/phân tích cross-layer

```
"Phân tích bug login fail: 1 teammate check frontend code,
1 teammate check API endpoint, 1 teammate check database schema.
Tổng hợp nguyên nhân root cause."
```

## ❌ KHÔNG nên dùng khi:

| Tình huống | Lý do |
|-----------|-------|
| Task đơn giản, chỉ 1 file | Overkill — chat thường nhanh hơn |
| Task phải làm tuần tự | Agent Teams tỏa sáng khi làm **song song** |
| Cần tiết kiệm token/credit | Nhiều agent = nhiều token hơn đáng kể |

---

---

# ⚙️ CẤU HÌNH NÂNG CAO — Display modes

Agent Teams có 2 chế độ hiển thị:

## In-process (mặc định trên Windows)

Tất cả teammates chạy chung trong 1 cửa sổ terminal. Dùng `Shift+Down` để chuyển view.

```
✅ Ưu điểm: Không cần cài thêm gì
❌ Nhược điểm: Hơi khó theo dõi nhiều agent cùng lúc
```

## Split Panes (cần tmux hoặc iTerm2 — Mac/Linux)

Mỗi teammate có cửa sổ riêng, nhìn trực quan hơn.

```
✅ Ưu điểm: Dễ theo dõi, mỗi agent 1 panel
❌ Nhược điểm: Cần cài tmux (Mac/Linux), Windows chưa hỗ trợ tốt
```

> 💡 **Đối với BA dùng Windows:** Chế độ **in-process** là đủ dùng. Không cần cài tmux.

---

---

# ⚠️ LƯU Ý & HẠN CHẾ

| Hạn chế | Giải thích |
|---------|-----------|
| **Tốn token nhiều hơn** | Mỗi teammate dùng context window riêng → chi phí tăng theo số agent |
| **Không resume được** | Nếu đóng terminal, team in-process sẽ mất. Phải tạo team mới |
| **1 team / 1 session** | Không thể chạy 2 team trong cùng 1 phiên Claude Code |
| **Không nested** | Teammate không thể tạo team con bên trong |
| **File conflict** | Nếu 2 teammate sửa cùng 1 file → có thể bị xung đột. Phân task rõ ràng để tránh |

---

# 🎯 BEST PRACTICES

### 1. Chọn số lượng teammates phù hợp

```
2-3 teammates  → Task vừa (review 2-3 docs, research 2-3 topics)
4-5 teammates  → Task lớn (review cả project, research toàn diện)
6+  teammates  → Hiếm khi cần, token cost cao
```

### 2. Giao context đầy đủ

```
❌ "Review mấy file PRD"
✅ "Review 3 file PRD trong folder docs/prd/. Mỗi file kiểm tra:
    (1) acceptance criteria đầy đủ? (2) edge cases? (3) dependencies rõ ràng?
    Output format: bảng markdown với cột File, Issues Found, Suggestions"
```

### 3. Tránh file conflict

```
❌ 2 teammates cùng sửa file README.md
✅ Mỗi teammate sửa file riêng, hoặc chỉ 1 teammate được sửa file chung
```

### 4. Đợi teammates hoàn thành

Đừng vội tổng hợp khi teammates chưa xong. Hỏi Team Lead: "Tất cả teammates đã xong chưa?" trước khi yêu cầu tổng hợp.

---

---

# 🎁 Checklist tổng để bookmark

```
CÀI ĐẶT
□ Đã cài Claude Code CLI (claude --version)
□ Đã đăng nhập (claude auth login)
□ Mở file ~/.claude/settings.json
□ Thêm "env": { "CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS": "1" }
□ Khởi động lại Claude Code

THỬ NGHIỆM
□ Gõ task cần nhiều agent (vd: "Review 3 file PRD cùng lúc")
□ Thấy Claude tạo teammates → ✅ Agent Teams hoạt động!
□ Dùng Shift+Down để chuyển giữa teammates
□ Đợi kết quả tổng hợp từ Team Lead

LƯU Ý
□ Số teammates khuyến nghị: 3-5
□ Giao context đầy đủ, rõ ràng
□ Tránh 2 teammates sửa cùng 1 file
□ Token cost tăng theo số teammates
```

---

> 💬 **Bình luận / feedback?**
> Thả vào Slack `#ai-ba-lab` hoặc tag mình trong Confluence nhé!
> Happy AI-augmented BA life! ✌️🤖
