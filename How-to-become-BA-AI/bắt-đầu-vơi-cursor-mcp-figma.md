# 🎨 BA x AI x Figma — Cẩm nang "đu trend" MCP Figma với Cursor

> ✍️ **Tác giả:** Senior BA team VNG  
> 🗓️ **Ngày viết:** Tháng 3/2026  
> 🎯 **Dành cho:** BA non-tech muốn dùng AI đọc & chỉnh Figma mà không cần code

---

## 🌈 Lời mở đầu — Why should you care?

Hồi trước BA ngồi xem Figma thì chỉ biết nhìn rồi mô tả lại bằng tay. Review màn hình thì copy text từng cái, check spec thì zoom zoom zoom từng layer. Mệt lắm bạn ơi 😮‍💨

Nhưng giờ khác rồi! Với **Cursor + MCP Figma**, bạn có thể:

- 🔍 **Đọc màn Figma** → nhờ AI review design, kiểm tra UX ngay trong Cursor
- ✏️ **Edit Figma** trực tiếp từ Cursor → vẽ wireframe nhanh chóng, clone frame, đổi text, đánh số, thêm data mẫu... mà không cần đụng tay vào Figma

Nghe "bá đạo" không? Đọc hết bài này là bạn làm được luôn 🚀

---

## 📦 Tổng quan — Có 2 hành trình

```
Hành trình 1: Đọc Figma   →  Figma Desktop MCP    (read-only)
Hành trình 2: Edit Figma  →  Plugin TalkToFigma   (read + write)
```

Hai cái này hoạt động **độc lập**, bạn có thể dùng 1 hoặc cả 2 đều được.

> 💡 **Câu hỏi hay gặp: "Ủa sao MCP Figma chỉ đọc được thôi, không edit được á?"**
>
> Đúng vậy! Lý do là:
> - **Figma Desktop MCP** do **Figma chính chủ** làm → họ chỉ cung cấp **read-only API** (lấy design, metadata, screenshot) vì lý do bảo mật, tránh AI tự ý "phá" design.
> - **Plugin TalkToFigma** do **cộng đồng** làm → plugin chạy **bên trong Figma** nên có đủ quyền để edit canvas (thêm node, đổi text, clone frame...). Plugin đóng vai "tay nối dài" nhận lệnh từ Cursor rồi thực thi trực tiếp trong Figma.
>
> **Nói ngắn gọn:**
> ```
> Muốn ĐỌC/REVIEW  →  Figma Desktop MCP  (đơn giản, ít setup)
> Muốn EDIT/THAY   →  Plugin TalkToFigma  (cần thêm Bun + socket + plugin)
> ```

Hai cái này hoạt động **độc lập**, bạn không cần cài cả hai nếu chỉ cần 1 trong 2.

---

---

# 🛤️ HÀNH TRÌNH 1 — Đọc màn Figma với Figma Desktop MCP

## Cơ chế hoạt động

```
Figma Desktop App  ──(MCP server port 3845)──►  Cursor  ──►  AI đọc design
```

Figma Desktop tự bật 1 server nhỏ trên máy bạn (port 3845). Cursor kết nối vào. AI có thể hỏi "màn này có gì?" và Figma trả lời ngay — **hoàn toàn chạy local, không lên internet**.

> ⚠️ **Lưu ý quan trọng:** Hành trình này **chỉ đọc được thôi**, không edit Figma được. Đây là giới hạn Figma đặt ra chủ ý — họ không muốn AI tự ý thay đổi design của bạn. Nếu cần edit, xem Hành trình 2 bên dưới nhé.

---

## Step 1 — Cài Figma Desktop

> ⚠️ Bắt buộc phải dùng **Figma Desktop App**, không phải browser.

1. Vào [figma.com/downloads](https://www.figma.com/downloads/)
2. Tải về và cài Figma Desktop cho Windows/Mac
3. Đăng nhập bằng tài khoản Figma của bạn

```
💡 Yêu cầu tài khoản: Dev Mode hoặc Full Seat (Professional / Org / Enterprise plan)
   Nếu bạn chưa có, liên hệ team design để được cấp quyền nhé!
```

---

## Step 2 — Bật Local MCP Server trong Figma

1. Mở **Figma Desktop**
2. Click vào **logo Figma** (góc trên trái) → chọn **Preferences**
3. Tìm mục **"Enable local MCP server"** → Bật ON

```
✅ Khi bật xong, Figma sẽ hiện thông báo xác nhận ở phía dưới màn hình
   Server mặc định chạy ở: http://127.0.0.1:3845/mcp
```

> 🖼️ *[Ảnh: Figma Preferences → Enable local MCP server được toggle ON]*

---

## Step 3 — Cấu hình Cursor kết nối Figma

Mở file cấu hình MCP của Cursor tại:

```
📁 Windows: C:\Users\<tên bạn>\.cursor\mcp.json
📁 Mac:     ~/.cursor/mcp.json
```

Thêm đoạn config sau vào file:

```json
{
  "mcpServers": {
    "Figma Desktop": {
      "url": "http://127.0.0.1:3845/mcp"
    }
  }
}
```

> 💡 Nếu file chưa có, tạo mới file `mcp.json` với nội dung trên là được.

---

## Step 4 — Restart Cursor

- **Đóng Cursor hoàn toàn** (không chỉ reload window)
- Mở lại Cursor
- Vào **Cursor Settings → MCP** → kiểm tra xem **Figma Desktop** có xuất hiện và status là ✅ không

> 🖼️ *[Ảnh: Cursor Settings → MCP tab → Figma Desktop hiện màu xanh "Connected"]*

---

## Step 5 — Thử nghiệm ngay!

1. Mở file Figma bất kỳ trong **Figma Desktop**
2. Click vào 1 màn hình (frame) bạn muốn xem
3. Quay lại Cursor, mở chat với AI và thử hỏi:

```
"Review màn hình Figma mình đang chọn"
"Màn hình này có những element gì?"
"Kiểm tra UX của màn này giúp mình"
```

AI sẽ đọc design, screenshot và trả lời ngay cho bạn 🎉

---

## ✅ Hành trình 1 — Tóm tắt

| Bước | Việc cần làm |
|------|-------------|
| 1 | Cài Figma Desktop |
| 2 | Preferences → Enable local MCP server |
| 3 | Thêm config vào `~/.cursor/mcp.json` |
| 4 | Restart Cursor, kiểm tra Connected |
| 5 | Mở Figma → chọn frame → hỏi AI trong Cursor |

**Dùng được để làm gì?**
- ✅ Review design, kiểm tra UX
- ✅ Đọc thông tin element, màu sắc, font, layout
- ✅ Screenshot frame → AI mô tả chi tiết
- ✅ Hỏi AI "màn này thiếu state gì?", "copy có ổn không?"...
- ❌ **Không edit được Figma** — đây là read-only by design (Figma chính chủ quyết định vậy)

> 💬 **Nếu bạn cần edit Figma từ Cursor → tiếp tục Hành trình 2 bên dưới nhé!**

---

---

# 🛤️ HÀNH TRÌNH 2 — Edit Figma từ Cursor với TalkToFigma

> 💡 **Tại sao không dùng MCP Figma để edit luôn?**  
> Vì Figma Desktop MCP **chỉ đọc** (do Figma chính chủ giới hạn). Để edit được, cần một plugin chạy bên trong Figma để "nhận lệnh" và thực thi. Đó là vai trò của **TalkToFigma** — một plugin cộng đồng, không phải của Figma chính chủ.

## Cơ chế hoạt động

```
Cursor (MCP TalkToFigma)
        │  "Clone frame X đi!"
        ▼ WebSocket
Socket Server (bunx cursor-talk-to-figma-socket)  ← cầu nối trung gian
        │
        ▼ Channel code (vd: abc12345)
Plugin TalkToFigma chạy bên trong Figma  ← nhận lệnh
        │  "OK, clone xong rồi!"
        ▼
Figma Canvas ← thay đổi hiện ra ngay lập tức ✨
```

**Tại sao cần đến 3 tầng như vậy?**
- Cursor ở ngoài, Figma ở trong — hai app không nói chuyện trực tiếp được
- **Socket server** đóng vai trung gian nhận/truyền tin
- **Plugin** chạy trong Figma mới có quyền sửa canvas
- **Channel code** là "mã phòng" giúp đúng Cursor kết nối đúng Figma

Ba thứ phải chạy cùng lúc:
1. **Socket server** — `bunx cursor-talk-to-figma-socket` chạy ở terminal
2. **Plugin TalkToFigma** — chạy trong Figma và bấm Connect
3. **Cursor** — chat với AI và gửi yêu cầu

---

## Step 1 — Cài Bun (runtime để chạy socket server)

Bun là môi trường chạy JavaScript, cần cài trước.

**Windows (PowerShell):**
```powershell
powershell -c "irm bun.sh/install.ps1 | iex"
```

**Mac/Linux (Terminal):**
```bash
curl -fsSL https://bun.sh/install | bash
```

Sau khi cài xong, kiểm tra:
```bash
bun --version
# Kết quả: 1.x.x là thành công ✅
```

> 🖼️ *[Ảnh: Terminal sau khi cài Bun thành công, hiện version]*

---

## Step 2 — Cài plugin TalkToFigma trong Figma

1. Mở **Figma** (Desktop hoặc Browser đều được)
2. Vào [figma.com/community/plugin/1485687494525374295](https://www.figma.com/community/plugin/1485687494525374295/cursor-talk-to-figma-mcp-plugin)
3. Click **"Install"** (nếu dùng browser) hoặc **"Open in Figma"** → cài trực tiếp
4. Sau khi cài, plugin xuất hiện trong **Plugins** của Figma

> 🖼️ *[Ảnh: Trang Figma Community của plugin TalkToFigma, nút Install màu tím]*

---

## Step 3 — Thêm TalkToFigma vào Cursor MCP config

Mở lại file `~/.cursor/mcp.json`, thêm **TalkToFigma** bên cạnh Figma Desktop:

```json
{
  "mcpServers": {
    "Figma Desktop": {
      "url": "http://127.0.0.1:3845/mcp"
    },
    "TalkToFigma": {
      "command": "bunx",
      "args": [
        "cursor-talk-to-figma-mcp@latest"
      ]
    }
  }
}
```

> 💡 Lưu file lại. **Restart Cursor** để áp dụng config mới.

---

## Step 4 — Chạy Socket Server

Mở **Terminal** (trong Cursor hoặc PowerShell/Terminal) và chạy:

```bash
bunx cursor-talk-to-figma-socket
```

Terminal sẽ hiện thông báo server đang chạy. **Giữ terminal này mở** trong suốt quá trình làm việc.

```
✅ Thành công: Server is running on port 3055 (hoặc 3000)
❌ Lỗi: Kiểm tra lại Bun đã cài chưa, hoặc thử lại bằng quyền admin
```

> 🖼️ *[Ảnh: Terminal hiện "Socket server running on port 3055"]*

---

## Step 5 — Bật Plugin trong Figma và Connect

1. Mở **Figma Desktop**
2. Mở file bạn muốn chỉnh sửa
3. Vào **Plugins** → tìm **"Cursor Talk to Figma"** → click chạy
4. Plugin hiện popup nhỏ → click **"Connect"**
5. Đợi plugin hiện **channel code** (dạng `abc12345`) và báo **Connected** ✅

```
📌 Ghi lại channel code này! Bạn sẽ cần dùng nó trong Cursor.
   Ví dụ: miqlnozt, 51wyo84y...
```

> 🖼️ *[Ảnh: Plugin TalkToFigma popup trong Figma, hiện channel code và nút Connect]*

---

## Step 6 — Kết nối từ Cursor

Trong **Cursor chat**, gõ yêu cầu và cung cấp channel code:

```
"Đã kết nối Figma rồi nè, channel: abc12345
 Em clone frame Database - List - All thành frame mới giúp anh"
```

AI sẽ tự động:
1. Join channel `abc12345`
2. Thực hiện thao tác trên Figma của bạn
3. Báo kết quả

> 🖼️ *[Ảnh: Cursor chat nhận được "Successfully joined channel: abc12345" và thực hiện lệnh]*

---

## Những việc TalkToFigma có thể làm

| Thao tác | Ví dụ |
|----------|-------|
| 📋 Clone frame | "Clone màn Database thành màn vServer" |
| ✏️ Đổi text hàng loạt | "Đổi chữ 'Database' thành 'vServer' trong frame" |
| 🔢 Điền data mẫu | "Đánh số thứ tự 1–5 vào cột ID" |
| 🔍 Scan toàn bộ text | "Liệt kê tất cả text node trong frame này" |
| 🎨 Đổi màu nền | "Đổi màu background frame thành #FAFAFA" |
| 📐 Resize node | "Chỉnh width của button thành 200px" |
| 🗑️ Xóa node | "Xóa component X trong frame" |

---

## ⚠️ Giới hạn cần biết (để không bị bất ngờ)

```
❌ Không thêm node mới vào bên trong INSTANCE của component
   → Muốn chỉnh cấu trúc: phải Detach Instance trước trong Figma, rồi mới nhờ AI edit

❌ Không sửa component gốc trong Design System từ xa được
   → Phải vào file Design System, sửa component nguồn trực tiếp

✅ Edit được text node, rename, clone, resize, set color nằm ngoài instance
```

---

## ✅ Hành trình 2 — Tóm tắt

| Bước | Việc cần làm |
|------|-------------|
| 1 | Cài Bun (`bun --version` để kiểm tra) |
| 2 | Cài plugin TalkToFigma từ Figma Community |
| 3 | Thêm TalkToFigma vào `mcp.json`, restart Cursor |
| 4 | Chạy `bunx cursor-talk-to-figma-socket` ở terminal |
| 5 | Mở Figma → chạy plugin → Connect → lấy channel code |
| 6 | Paste channel code vào Cursor chat → nhờ AI làm |

---

---

# 🎯 So sánh nhanh 2 hành trình

| | **Figma Desktop MCP** | **TalkToFigma Plugin** |
|---|---|---|
| **Ai làm ra** | Figma chính chủ | Cộng đồng (open source) |
| **Mục đích chính** | 📖 Đọc, review design | ✏️ Edit, clone, thay text |
| **Có edit Figma được không?** | ❌ Read-only (cố tình) | ✅ Edit được |
| **Plugin Figma** | Không cần | Cần cài plugin |
| **Socket server** | Không cần | Cần chạy `bunx` |
| **Độ phức tạp setup** | ⭐ Đơn giản | ⭐⭐ Cần thêm vài bước |
| **Figma Desktop bắt buộc?** | ✅ Bắt buộc | ❌ Desktop hoặc Browser đều được |
| **Edit bên trong instance/component** | ❌ | ❌ (phải Detach trước) |

> 💡 **Rule of thumb:**
> - Chỉ cần **nhìn và hỏi AI** về design → dùng **Figma Desktop MCP** (nhanh, đơn giản)
> - Cần **thay đổi nội dung Figma** từ Cursor → dùng **TalkToFigma Plugin**
> - Có thể dùng **cả hai cùng lúc** — không xung đột nhau

---

# 💡 Tips & Tricks cho BA

### 1. Workflow review design chuẩn chỉnh

```
Figma Desktop MCP → Cursor đọc màn
        ↓
AI review UX, liệt kê issues
        ↓
Copy output → paste vào Confluence/Notion/docs
```

### 2. Tạo data mẫu nhanh cho prototype

```
Clone frame bằng TalkToFigma
        ↓
Nhờ AI điền text mẫu, đánh số thứ tự
        ↓
Tiết kiệm 30 phút ngồi gõ tay ✌️
```

### 3. Khi bị lỗi timeout / can't connect

Checklist fix nhanh:

- [ ] Socket server (`bunx cursor-talk-to-figma-socket`) vẫn đang chạy không?
- [ ] Plugin trong Figma đã bấm **Connect** chưa?
- [ ] Channel code copy đúng chưa? (không có khoảng trắng thừa)
- [ ] Thử tắt plugin → bật lại → Connect lại

### 4. Detach instance khi cần edit cấu trúc

Trong Figma:
1. Click phải vào component bảng/frame
2. Chọn **"Detach instance"**
3. Quay Cursor và nhờ AI tiếp tục

---

# 🚀 Thực chiến — Case study thực tế

## Case 1: Review màn upload document

> "Review màn hình Figma mình đang chọn đi em"

**AI đã làm:**
- Screenshot màn "Upload - Showing supported types"
- Mô tả đầy đủ layout, element, UX flow
- Gợi ý 6 điểm cần cải thiện (copy, state, responsive, accessibility...)

⏱️ **Tiết kiệm:** ~30–45 phút so với ngồi đọc tay từng layer

---

## Case 2: Clone màn Database sang vServer

> "Clone màn Database - List - All thành frame mới rồi đánh số ID từ 1–5 vào bảng"

**AI đã làm:**
- Join channel `51wyo84y`
- Clone frame `1:1765` → tạo frame mới `5:3418`
- Scan toàn bộ text node trong bảng
- Điền số 1, 2, 3, 4, 5 vào đúng cột ID

⏱️ **Tiết kiệm:** ~20 phút so với duplicate + edit tay

---

# 📚 Tài nguyên thêm

| Link | Mô tả |
|------|-------|
| [Figma Downloads](https://www.figma.com/downloads/) | Cài Figma Desktop |
| [TalkToFigma Plugin](https://www.figma.com/community/plugin/1485687494525374295) | Plugin Figma Community |
| [cursor-talk-to-figma-mcp GitHub](https://github.com/sonnylazuardi/cursor-talk-to-figma-mcp) | Source code, docs đầy đủ |
| [Bun.sh](https://bun.sh) | Cài Bun runtime |
| [Cursor MCP Docs](https://cursor.directory/mcp) | Hướng dẫn MCP trong Cursor |

---

# 🎁 Checklist tổng để bookmark

```
HÀNH TRÌNH 1 — Đọc Figma (Figma Desktop MCP)
□ Cài Figma Desktop
□ Figma Preferences → Enable local MCP server
□ Thêm "Figma Desktop": {"url": "http://127.0.0.1:3845/mcp"} vào ~/.cursor/mcp.json
□ Restart Cursor → Kiểm tra Settings → MCP
□ Mở frame Figma → hỏi AI trong Cursor ✅

HÀNH TRÌNH 2 — Edit Figma (TalkToFigma)
□ Cài Bun (bun --version)
□ Cài plugin TalkToFigma từ Figma Community
□ Thêm TalkToFigma vào mcp.json → Restart Cursor
□ Terminal: bunx cursor-talk-to-figma-socket (giữ mở)
□ Figma → Plugins → TalkToFigma → Connect
□ Copy channel code → paste vào Cursor chat ✅
```

---

> 💬 **Bình luận / feedback?**  
> Thả vào Slack `#ai-ba-lab` hoặc tag mình trong Confluence nhé!  
> Happy vibe-coding! ✌️🎨
