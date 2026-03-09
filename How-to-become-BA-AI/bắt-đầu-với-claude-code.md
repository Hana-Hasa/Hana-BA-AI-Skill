# 🤖 Claude Code — Hướng dẫn cài đặt cho VS Code, Cursor & Antigravity

> ✍️ **Tác giả:** Hana Ngọc Huyền
> 🗓️ **Ngày viết:** Tháng 3/2026
> 🎯 **Dành cho:** BA muốn dùng Claude Code trực tiếp trong editor để tăng tốc công việc
> 📚 **Series:** Becoming an AI-Augmented BA — Article 3

---

## 🌈 Lời mở đầu — Why should you care?

Hồi trước muốn dùng AI thì phải mở browser, copy code/text qua lại giữa ChatGPT và editor. Viết PRD thì tab này, review code thì tab kia, context bị mất liên tục. Mệt lắm bạn ơi 😮‍💨

Nhưng giờ khác rồi! Với **Claude Code**, bạn có thể:

- 🧠 **Chat với AI ngay trong editor** — không cần mở browser
- 📂 **AI đọc được cả project** — hiểu context file, folder, code của bạn
- ✏️ **AI sửa file trực tiếp** — viết PRD, review doc, tạo template... ngay trong workspace
- 🔧 **Chạy terminal commands** — AI có thể chạy lệnh, test, commit giúp bạn

Nghe tiện không? Đọc hết bài này là bạn setup xong trong 15 phút 🚀

---

## 📦 Tổng quan — 3 cách cài đặt

```
Cách 1: VS Code        →  Extension chính chủ Anthropic  (phổ biến nhất)
Cách 2: Cursor          →  Tích hợp qua Extension hoặc Terminal
Cách 3: Antigravity     →  Tích hợp qua Terminal
```

Cả 3 cách đều dùng chung **Claude Code CLI** — chỉ khác ở editor bạn chọn.

> 💡 **Claude Code là gì?**
> Nếu Claude (trên web) giống như bạn chat qua điện thoại, thì **Claude Code** giống như mời Claude ngồi cạnh bàn làm việc — AI thấy được toàn bộ project, đọc file, sửa file, chạy lệnh... ngay tại chỗ.

---

---

# 🛠️ CHUẨN BỊ — Cài đặt Claude Code CLI

> ⚠️ **Bắt buộc phải làm bước này trước**, dù bạn dùng VS Code, Cursor hay Antigravity.

Claude Code chạy trên **Node.js** — đây là môi trường giúp máy tính hiểu và chạy Claude Code.

---

## Step 1 — Cài Node.js

Node.js giống như "pin" để Claude Code chạy được. Không có Node.js thì Claude Code không khởi động.

1. Vào [nodejs.org](https://nodejs.org/)
2. Tải bản **LTS** (Long Term Support) — bản ổn định nhất
3. Cài đặt theo hướng dẫn (cứ Next → Next → Finish)

Kiểm tra cài thành công:

**Windows (PowerShell):**

```powershell
node --version
```

**Mac/Linux (Terminal):**

```bash
node --version
```

```
✅ Success: v20.x.x hoặc v22.x.x → Thành công!
❌ Error: "command not found" → Node.js chưa cài. Thử tải lại từ nodejs.org
```

> ⚠️ **Yêu cầu:** Node.js phiên bản **18 trở lên**. Nếu version thấp hơn, hãy tải bản LTS mới nhất.

---

## Step 2 — Cài Claude Code CLI

CLI (Command Line Interface) là công cụ dòng lệnh — bạn chỉ cần copy-paste 1 dòng lệnh là xong.

Mở Terminal / PowerShell và chạy:

```bash
npm install -g @anthropic-ai/claude-code
```

Kiểm tra:

```bash
claude --version
```

```
✅ Success: hiện số version → Claude Code đã sẵn sàng!
❌ Error: "command not found" → Thử đóng terminal, mở lại rồi chạy lại lệnh kiểm tra
```

> 🖼️ *[Screenshot: Terminal sau khi cài Claude Code thành công, hiện version]*

---

## Step 3 — Đăng nhập tài khoản Anthropic

Claude Code cần tài khoản Anthropic để hoạt động. Bạn cần có **API key** hoặc đăng nhập qua browser.

```bash
claude auth login
```

Terminal sẽ mở browser để bạn đăng nhập. Sau khi đăng nhập xong, quay lại terminal.

```
✅ Success: "Authentication successful" → Sẵn sàng dùng!
❌ Error: Kiểm tra kết nối internet, hoặc hỏi team lead để được cấp tài khoản
```

> 💡 **Chưa có tài khoản Anthropic?** Liên hệ team lead hoặc đăng ký tại [console.anthropic.com](https://console.anthropic.com/). Cần có credit/plan để sử dụng Claude Code.

---

## ✅ Chuẩn bị — Tóm tắt

| Bước | Việc cần làm                                   |
| ------ | ------------------------------------------------- |
| 1      | Cài Node.js v18+ từ nodejs.org                  |
| 2      | `npm install -g @anthropic-ai/claude-code`      |
| 3      | `claude auth login` → đăng nhập qua browser |

---

---

# 🛤️ CÁCH 1 — Cài Claude Code trong VS Code

## Cơ chế hoạt động

```
VS Code  ──(Extension)──►  Claude Code CLI  ──►  Anthropic API  ──►  AI trả lời
```

Extension chính chủ của Anthropic tích hợp Claude Code vào VS Code — bạn chat với AI ngay trong editor.

---

## Step 1 — Cài Extension Claude Code

1. Mở **VS Code**
2. Click vào **Extensions** (icon hình ô vuông bên trái, hoặc `Ctrl+Shift+X`)
3. Tìm **"Claude Code"** (publisher: Anthropic)
4. Click **Install**

```
✅ Success: Extension xuất hiện ở sidebar trái, icon hình Claude
❌ Error: Nếu không tìm thấy, kiểm tra VS Code version — cần v1.90+
```

> 🖼️ *[Screenshot: VS Code Extensions → tìm "Claude Code" → nút Install]*

---

## Step 2 — Mở Claude Code Panel

Sau khi cài xong:

1. Click vào **icon Claude** ở sidebar trái
2. Hoặc nhấn `Ctrl+Shift+P` → gõ **"Claude Code: Open"**
3. Panel chat AI hiện ra bên phải

```
✅ Success: Panel chat hiện ra, sẵn sàng nhập câu hỏi
❌ Error: "Claude Code not found" → Kiểm tra đã cài CLI ở bước Chuẩn bị chưa
```

> 🖼️ *[Screenshot: VS Code với Claude Code panel mở bên phải, ô chat sẵn sàng]*

---

## Step 3 — Thử nghiệm ngay!

Mở một project/folder bất kỳ trong VS Code, rồi gõ vào Claude Code chat:

```
"Liệt kê tất cả file trong project này"
"Đọc file README và tóm tắt giúp mình"
"Tạo file template PRD cho feature login"
```

AI sẽ đọc project của bạn và trả lời ngay 🎉

---

## ✅ Cách 1 — Tóm tắt

| Bước | Việc cần làm                                                            |
| ------ | -------------------------------------------------------------------------- |
| 1      | Extensions → tìm "Claude Code" → Install                                |
| 2      | Click icon Claude ở sidebar hoặc `Ctrl+Shift+P` → "Claude Code: Open" |
| 3      | Gõ câu hỏi → AI trả lời ngay trong editor                            |

---

---

# 🛤️ CÁCH 2 — Cài Claude Code trong Cursor

> 💡 **Cursor đã có AI built-in rồi, sao cần Claude Code?**
> Cursor mặc định dùng GPT/Claude qua Cursor's API. Nhưng **Claude Code** cho bạn trải nghiệm Claude "chính chủ" với đầy đủ tính năng: agentic coding, đọc toàn bộ codebase, chạy terminal, và dùng API key riêng của team bạn.

---

## Cách 2A — Dùng Extension (giống VS Code)

Cursor tương thích với VS Code extensions, nên bạn cài y hệt:

1. Mở **Cursor**
2. `Ctrl+Shift+X` → tìm **"Claude Code"** → **Install**
3. Click icon Claude ở sidebar → bắt đầu chat

> ⚠️ **Lưu ý:** Một số version Cursor có thể không tương thích 100% với extension VS Code. Nếu gặp lỗi, dùng Cách 2B bên dưới.

---

## Cách 2B — Dùng Terminal tích hợp

Nếu extension không hoạt động, bạn chạy Claude Code trực tiếp trong terminal của Cursor:

1. Mở **Cursor**
2. Mở Terminal: ``Ctrl+` `` (backtick) hoặc menu **Terminal → New Terminal**
3. Gõ:

```bash
claude
```

4. Claude Code khởi động ngay trong terminal, đọc được toàn bộ project

```
✅ Success: Claude Code hiện giao diện chat trong terminal, sẵn sàng nhận lệnh
❌ Error: "command not found" → Quay lại bước Chuẩn bị, kiểm tra đã cài CLI chưa
```

> 🖼️ *[Screenshot: Cursor terminal với Claude Code đang chạy, hiện prompt chờ nhập]*

---

## ✅ Cách 2 — Tóm tắt

| Cách           | Việc cần làm                                                    |
| --------------- | ------------------------------------------------------------------ |
| 2A — Extension | `Ctrl+Shift+X` → "Claude Code" → Install → Click icon sidebar |
| 2B — Terminal  | ``Ctrl+` `` → gõ `claude` → chat trực tiếp                   |

---

---

# 🛤️ CÁCH 3 — Cài Claude Code trong Antigravity

> 💡 **Antigravity** là editor AI-native mới. Claude Code chạy trong Antigravity qua terminal tích hợp.

---

## Step 1 — Mở Terminal trong Antigravity

1. Mở **Antigravity**
2. Mở project/folder bạn muốn làm việc
3. Mở Terminal: dùng shortcut hoặc menu **View → Terminal**

---

## Step 2 — Chạy Claude Code

Trong terminal, gõ:

```bash
claude
```

Claude Code sẽ khởi động và nhận diện project hiện tại.

```
✅ Success: Claude Code hiện giao diện chat, đọc được project
❌ Error: "command not found" → Kiểm tra lại bước Chuẩn bị (Node.js + CLI)
```

---

## Step 3 — Thử nghiệm

```
"Đọc tất cả file .md trong project và tóm tắt"
"Review file PRD này giúp mình"
"Tạo user story cho feature đăng nhập"
```

---

## ✅ Cách 3 — Tóm tắt

| Bước | Việc cần làm                  |
| ------ | -------------------------------- |
| 1      | Mở Antigravity → mở project   |
| 2      | Terminal → gõ `claude`       |
| 3      | Chat với AI ngay trong terminal |

---

---

# 🎯 So sánh nhanh 3 cách

|                             | **VS Code**               | **Cursor**                       | **Antigravity**   |
| --------------------------- | ------------------------------- | -------------------------------------- | ----------------------- |
| **Cách cài**        | Extension chính chủ           | Extension hoặc Terminal               | Terminal                |
| **Giao diện**        | Panel chat riêng               | Panel chat hoặc Terminal              | Terminal                |
| **Tương thích**    | ✅ Tốt nhất                   | ✅ Tốt (Extension có thể lỗi nhẹ) | ✅ Tốt                 |
| **AI khác sẵn có** | GitHub Copilot                  | Cursor AI built-in                     | Antigravity AI built-in |
| **Phù hợp nếu**    | Đang dùng VS Code hàng ngày | Đang dùng Cursor, muốn thêm Claude | Đang dùng Antigravity |

> 🎯 **Rule of thumb:**
>
> - Đang dùng editor nào → cài Claude Code vào editor đó
> - Chưa dùng editor nào → bắt đầu với **VS Code** (phổ biến nhất, tài liệu nhiều nhất)
> - Muốn nhanh nhất → dùng **Terminal** (chỉ cần gõ `claude`)

---

# 💡 Tips & Tricks cho BA

### 1. Mở project trước khi chat

Claude Code đọc được toàn bộ project đang mở. Nếu bạn mở đúng folder chứa PRD, specs, docs → AI hiểu context tốt hơn rất nhiều.

```
Mở folder project → Claude Code → "Tóm tắt toàn bộ PRD trong folder này"
AI đọc tất cả file → tóm tắt → bạn tiết kiệm 1 tiếng đọc docs 📚
```

### 2. Dùng Claude Code để review document

```
"Review file PRD.md — kiểm tra thiếu acceptance criteria ở story nào"
"So sánh 2 file spec v1 và v2 — liệt kê thay đổi"
"Kiểm tra user story này đã đúng format Given-When-Then chưa"
```

### 3. Tạo template nhanh

```
"Tạo template PRD theo format của team mình"
"Viết user story cho feature upload file, include edge cases"
"Tạo test case checklist cho flow thanh toán"
```

### 4. Khi bị lỗi kết nối

Checklist fix nhanh:

- [ ] Node.js đã cài chưa? (`node --version`)
- [ ] Claude Code CLI đã cài chưa? (`claude --version`)
- [ ] Đã đăng nhập chưa? (`claude auth login`)
- [ ] Internet có ổn không?
- [ ] Thử đóng editor, mở lại

---

# 🚀 Thực chiến — Case study thực tế

## Case 1: Review PRD trước sprint planning

> "Đọc file PRD-vServer.md và kiểm tra xem có story nào thiếu acceptance criteria không"

**AI đã làm:**

- Đọc toàn bộ PRD (15 trang)
- Liệt kê 4 user story thiếu acceptance criteria
- Gợi ý acceptance criteria cho từng story

⏱️ **Tiết kiệm:** ~45 phút so với đọc và review tay

---

## Case 2: Tạo meeting notes template

> "Tạo template meeting notes cho sprint retrospective, include các section: What went well, What to improve, Action items"

**AI đã làm:**

- Tạo file `retro-template.md` ngay trong project
- Format đẹp, có bảng, có checkbox cho action items
- Thêm section "Follow-up from last retro"

⏱️ **Tiết kiệm:** ~15 phút so với tạo template từ đầu

---

# 📚 Tài nguyên thêm

| Link                                                            | Mô tả                          |
| --------------------------------------------------------------- | -------------------------------- |
| [Node.js Downloads](https://nodejs.org/)                           | Cài Node.js LTS                 |
| [Claude Code Docs](https://docs.anthropic.com/en/docs/claude-code) | Tài liệu chính chủ Anthropic |
| [VS Code](https://code.visualstudio.com/)                          | Tải VS Code                     |
| [Cursor](https://cursor.sh/)                                       | Tải Cursor                      |
| [Anthropic Console](https://console.anthropic.com/)                | Quản lý API key & billing      |

---

# 🎁 Checklist tổng để bookmark

```
CHUẨN BỊ (BẮT BUỘC)
□ Cài Node.js v18+ (node --version)
□ npm install -g @anthropic-ai/claude-code
□ claude auth login → đăng nhập thành công

VS CODE
□ Extensions → "Claude Code" → Install
□ Click icon Claude sidebar → Panel chat mở
□ Thử hỏi AI 1 câu → nhận được trả lời ✅

CURSOR
□ Cách A: Extensions → "Claude Code" → Install
□ Hoặc Cách B: Terminal → gõ "claude"
□ Thử hỏi AI 1 câu → nhận được trả lời ✅

ANTIGRAVITY
□ Terminal → gõ "claude"
□ Thử hỏi AI 1 câu → nhận được trả lời ✅
```

---

> 💬 **Bình luận / feedback?**
> Thả vào Slack `#ai-ba-lab` hoặc tag mình trong Confluence nhé!
> Happy AI-augmented BA life! ✌️🤖
