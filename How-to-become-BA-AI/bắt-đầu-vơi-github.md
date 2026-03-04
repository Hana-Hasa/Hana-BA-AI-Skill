# 🐙 Bước đầu trở thành BA AI thực thụ — Làm quen với GitHub

> ✍️ **Tác giả:** Senior BA team VNG  
> 🗓️ **Ngày viết:** Tháng 3/2026  
> 🎯 **Dành cho:** BA muốn bước vào con đường AI-augmented, bắt đầu từ công cụ nền tảng nhất  
> 📚 **Series:** Bước đầu trở thành BA AI thực thụ — Bài 1/N

---

## 🤔 Ủa GitHub là gì, BA thì cần biết để làm gì?

Nghe đến **GitHub** là nhiều bạn BA nghĩ ngay đến "mấy cái đó của dev, mình không cần đâu" 😅

Mình hiểu cảm giác đó — nhưng thật ra GitHub không chỉ là nơi lưu code. Với BA, GitHub là:

- 📁 **Google Drive phiên bản pro** — lưu tài liệu có version history, biết ai sửa gì lúc nào
- 📋 **Jira mini** — quản lý task, todo list, track progress ngay trên repo
- 🤝 **Confluence nhẹ hơn** — viết docs bằng Markdown, review và comment trực tiếp
- 🤖 **"Ổ cứng" cho AI làm việc** — các tool AI như Cursor đọc file từ repo của bạn để hiểu context và hỗ trợ chính xác hơn

Nếu bạn muốn dùng **Cursor AI**, **Claude**, hay bất kỳ AI tool nào để hỗ trợ công việc BA → GitHub là **nền tảng bạn cần có trước tiên**. Không có repo thì AI "mù" bối cảnh dự án của bạn.

---

## 🗺️ Roadmap bài này

```
1. Khái niệm cơ bản (không cần nhớ hết, đọc hiểu là đủ)
2. Cài đặt và tạo tài khoản
3. Tạo repo đầu tiên cho BA
4. Cách dùng GitHub hàng ngày (không cần biết code)
5. Tại sao BA nên dùng GitHub thay vì Google Drive thuần túy
6. Tips & Tricks thực tế
```

---

---

# 🧠 PHẦN 1 — Khái niệm cơ bản (đủ dùng cho BA)

> 💡 Không cần nhớ hết — chỉ cần hiểu đủ để làm việc. Gặp từ lạ thì tra lại bài này.

## Git vs GitHub — hai thứ khác nhau nha!

| | **Git** | **GitHub** |
|---|---|---|
| Là gì? | Phần mềm quản lý version chạy trên máy bạn | Website/dịch vụ lưu trữ repo trên cloud |
| Cài ở đâu? | Máy tính của bạn | Không cần cài, vào web là dùng |
| Dùng như thế nào? | Dòng lệnh (terminal) hoặc qua app | Trình duyệt hoặc app GitHub Desktop |
| Bắt buộc không? | Cần nếu muốn sync tự động | Cần để lưu và share với người khác |

> 🎯 **Với BA non-tech:** Dùng **GitHub Desktop** (app có giao diện đẹp) là đủ, không cần nhớ dòng lệnh.

---

## Từ điển GitHub cho BA

| Từ | Hiểu đơn giản là... |
|----|---------------------|
| **Repository (repo)** | Một "thư mục dự án" trên GitHub — chứa tất cả file, docs, task |
| **Commit** | Hành động "lưu lại" thay đổi, kèm ghi chú "lưu cái gì" |
| **Branch** | Nhánh làm việc riêng — như tạo 1 bản copy để thử nghiệm mà không ảnh hưởng bản gốc |
| **Main/Master** | Nhánh chính — bản "chính thức" của tài liệu |
| **Pull Request (PR)** | Yêu cầu merge thay đổi vào nhánh chính — như "xin duyệt bản cập nhật" |
| **Issue** | Một task, bug, hoặc ghi chú cần theo dõi — giống ticket Jira |
| **Markdown (.md)** | Định dạng viết văn bản đơn giản — bạn đang đọc 1 file Markdown lúc này đấy! |
| **Push** | Đẩy thay đổi từ máy lên GitHub cloud |
| **Pull** | Kéo thay đổi từ GitHub cloud về máy |
| **Clone** | Tải nguyên 1 repo từ GitHub về máy để làm việc |

> 🖼️ **[Ảnh cần có: Sơ đồ minh họa flow: Local (máy bạn) → Commit → Push → GitHub Cloud, và ngược lại Pull]**

---

## Vòng đời làm việc với GitHub (đơn giản nhất)

```
1. Tạo repo trên GitHub
        ↓
2. Clone về máy (hoặc edit thẳng trên web)
        ↓
3. Tạo/sửa file (.md, .txt, .json...)
        ↓
4. Commit: ghi chú "sửa gì" → lưu lại snapshot
        ↓
5. Push lên GitHub cloud
        ↓
6. Người khác Pull về → xem được thay đổi của bạn
```

---

---

# 🛠️ PHẦN 2 — Cài đặt và tạo tài khoản

## Step 1 — Tạo tài khoản GitHub

1. Vào [github.com](https://github.com)
2. Click **"Sign up"** → điền email, username, password
3. Xác nhận email
4. Done! Tài khoản free là đủ dùng cho BA rồi 🎉

> 🖼️ **[Ảnh cần có: Trang đăng ký GitHub với nút Sign Up nổi bật]**

```
💡 Gợi ý đặt username:
   - Dùng tên thật hoặc tên công việc (vd: hana-ba-vng)
   - Tránh username random khó nhớ vì sẽ share link repo cho team
```

---

## Step 2 — Cài GitHub Desktop (khuyên dùng cho BA)

GitHub Desktop là app có giao diện kéo thả, không cần gõ lệnh. **BA non-tech nên dùng cái này.**

1. Vào [desktop.github.com](https://desktop.github.com)
2. Download và cài đặt
3. Đăng nhập bằng tài khoản GitHub vừa tạo

> 🖼️ **[Ảnh cần có: Giao diện GitHub Desktop — sidebar trái là danh sách repo, giữa là list file thay đổi, phải là diff (so sánh trước/sau)]**

```
✅ Sau khi cài xong, GitHub Desktop tự nhận diện Git trên máy
   Nếu chưa có Git, app sẽ hướng dẫn cài thêm
```

---

## Step 3 — Cài Git (nếu dùng Cursor hoặc terminal)

Nếu bạn dùng **Cursor AI** để làm việc với repo thì cần cài Git:

**Windows:** Tải tại [git-scm.com/download/win](https://git-scm.com/download/win) → cài Next Next Next là xong

**Mac:** Mở Terminal gõ:
```bash
git --version
# Nếu chưa có, Mac sẽ tự hỏi cài Xcode Command Line Tools → bấm Install
```

Kiểm tra cài thành công:
```bash
git --version
# Git version 2.x.x → ✅ OK
```

> 🖼️ **[Ảnh cần có: Terminal hiện "git version 2.x.x" sau khi cài thành công]**

---

---

# 📁 PHẦN 3 — Tạo Repo đầu tiên cho BA

## Tạo repo trên GitHub web

1. Đăng nhập [github.com](https://github.com)
2. Click nút **"New"** (hoặc dấu `+` góc trên phải → **New repository**)
3. Điền thông tin:

```
Repository name:  ba-workspace  (hoặc tên dự án của bạn)
Description:      Workspace của BA team — docs, task, notes
Visibility:       Private (chỉ mình và team thấy)
                  hoặc Public (ai cũng thấy — chọn nếu muốn share rộng)
☑️ Add a README file  ← tick vào cái này!
```

4. Click **"Create repository"**

> 🖼️ **[Ảnh cần có: Form tạo repo mới trên GitHub — highlight các trường Repository name, Visibility (Private), và checkbox Add README]**

---

## Cấu trúc repo gợi ý cho BA

Sau khi tạo repo, tổ chức thư mục như này:

```
📁 ba-workspace/
├── 📄 README.md              ← Giới thiệu repo, mục đích dùng
├── 📁 requirements/          ← PRD, BRD, user story
│   ├── PRD-feature-X.md
│   └── BRD-project-Y.md
├── 📁 meeting-notes/         ← Biên bản họp, MoM
│   └── 2026-03-04-kickoff.md
├── 📁 research/              ← Nghiên cứu thị trường, benchmark
├── 📁 tasks/                 ← Task tracking, todo list
│   └── sprint-01.md
└── 📁 templates/             ← Template dùng lại: PRD, MoM, user story...
```

> 💡 **Tip:** File `.md` (Markdown) là "đặc sản" của GitHub — hiển thị đẹp trên web, AI tools đọc được tốt, và viết cũng không khó hơn Word là mấy.

---

---

# 📅 PHẦN 4 — Dùng GitHub hàng ngày (không cần code)

## 4.1 — Viết và lưu tài liệu (Edit trực tiếp trên web)

Cách nhanh nhất để bắt đầu — không cần cài gì thêm:

1. Vào repo trên [github.com](https://github.com)
2. Click vào file cần sửa (ví dụ `README.md`)
3. Click **nút bút chì (✏️ Edit)** góc trên phải
4. Chỉnh sửa nội dung
5. Cuộn xuống cuối → phần **"Commit changes"**:
   - Dòng đầu: ghi tóm tắt thay đổi (vd: `Cập nhật PRD màn login`)
   - Dòng dưới: ghi chi tiết hơn nếu cần
6. Click **"Commit changes"** → lưu xong!

> 🖼️ **[Ảnh cần có: Giao diện edit file trên GitHub web — highlight nút bút chì và form Commit changes phía dưới]**

```
✅ Mỗi lần commit = 1 snapshot
   GitHub tự lưu toàn bộ lịch sử → bạn xem lại, khôi phục được bất kỳ version nào
```

---

## 4.2 — Tạo file mới trên web

1. Trong repo → click **"Add file"** → **"Create new file"**
2. Đặt tên file (nhớ đuôi `.md` để hiển thị đẹp trên GitHub)
3. Viết nội dung bằng Markdown
4. Commit

> 🖼️ **[Ảnh cần có: Nút "Add file" → dropdown "Create new file" trên GitHub repo]**

---

## 4.3 — Quản lý task bằng GitHub Issues

**Issues** là tính năng cực kỳ hữu ích — như Jira nhưng nhẹ hơn, miễn phí và nằm ngay trong repo.

### Tạo Issue mới

1. Trong repo → tab **"Issues"**
2. Click **"New issue"**
3. Điền:
   - **Title:** Tên task (vd: `[PRD] Viết tài liệu cho màn upload document`)
   - **Description:** Mô tả chi tiết, checklist, acceptance criteria
   - **Assignees:** Gán cho ai làm
   - **Labels:** Phân loại (bug, feature, docs, question...)
   - **Milestone:** Gắn vào sprint/milestone nào

> 🖼️ **[Ảnh cần có: Form tạo Issue mới — highlight Title, Description có checklist, Labels, Assignees]**

### Dùng Markdown checklist trong Issue

```markdown
## Checklist
- [x] Phỏng vấn stakeholder
- [x] Draft PRD v1
- [ ] Review với PM
- [ ] Sign-off từ Dev Lead
- [ ] Update Jira
```

Hiển thị như này trên GitHub:

```
✅ Phỏng vấn stakeholder
✅ Draft PRD v1
⬜ Review với PM
⬜ Sign-off từ Dev Lead
⬜ Update Jira
```

> 🖼️ **[Ảnh cần có: Issue với checklist hiển thị trên GitHub — các dòng đã tick hiện dấu ✅ màu xanh]**

---

## 4.4 — Xem lịch sử thay đổi

Đây là siêu năng lực của GitHub so với Google Drive:

1. Trong repo → click tab **"Commits"** (hoặc click vào "X commits" phía trên list file)
2. Thấy toàn bộ lịch sử: ai sửa, sửa lúc nào, sửa gì
3. Click vào bất kỳ commit → thấy **diff** (màu xanh = thêm mới, màu đỏ = xóa đi)

> 🖼️ **[Ảnh cần có: Trang Commits history — danh sách commit theo thứ tự thời gian, mỗi dòng có avatar, tên người commit, message, và thời gian]**

> 🖼️ **[Ảnh cần có: Trang xem diff của 1 commit — phần màu đỏ (xóa) và màu xanh (thêm) trong file .md]**

```
💡 Use case thực tế:
   PM hỏi "Hồi trước anh em thống nhất gì về feature X vậy?"
   → Bạn vào Commits → tìm commit ngày đó → xem lại chính xác từng chữ đã thay đổi
   Không còn "hình như hôm đó mình có sửa gì đó..." nữa 😌
```

---

## 4.5 — Làm việc nhóm với Branch + Pull Request

Khi làm việc nhóm, tránh mọi người cùng sửa 1 file gây conflict:

**Cách đơn giản nhất:**

1. Tạo branch mới từ main: `feature/prd-login` (đặt tên có nghĩa)
2. Làm việc trên branch đó
3. Khi xong → tạo **Pull Request** để merge vào main
4. Người review đọc, comment, approve → merge

> 🖼️ **[Ảnh cần có: Tab Pull Requests trên GitHub — danh sách PR, mỗi PR có status (Open/Merged/Closed), người tạo, và số comments]**

```
💡 Với BA, dùng PR = "xin review tài liệu"
   PM/Tech Lead comment trực tiếp vào từng dòng → dễ track feedback hơn email
```

---

---

# 🏆 PHẦN 5 — Tại sao BA nên dùng GitHub thay vì chỉ dùng Google Drive?

## So sánh thực tế

| Tình huống | Google Drive | GitHub |
|-----------|--------------|--------|
| Lưu PRD | ✅ Được | ✅ Được |
| Xem ai sửa gì | ⚠️ Có nhưng khó tìm | ✅ Rõ ràng từng dòng, từng người |
| Khôi phục version cũ | ⚠️ Có nhưng hạn chế | ✅ Dễ dàng, không giới hạn |
| Track task | ❌ Phải dùng Sheet riêng | ✅ Issues ngay trong repo |
| AI tool đọc context | ❌ Phải upload tay | ✅ Cursor/AI tự đọc từ repo |
| Tìm kiếm nội dung | ⚠️ Search cơ bản | ✅ Search toàn bộ repo, kể cả nội dung file |
| Review tài liệu nhóm | ⚠️ Comment trên Doc | ✅ PR + comment từng dòng |
| Offline | ❌ Cần internet | ✅ Clone về máy → làm offline |
| Miễn phí | ✅ | ✅ (plan free đủ dùng) |

---

## 3 lý do BA "AI-augmented" cần GitHub

### 1. 🤖 AI hiểu bạn hơn khi có repo

Khi bạn dùng **Cursor AI** với một repo GitHub:
- AI đọc được toàn bộ context dự án (PRD, meeting notes, spec...)
- Câu trả lời của AI chính xác hơn nhiều so với hỏi "không có context"
- AI có thể suggest, viết, edit tài liệu đúng format và style của team

```
❌ Không có repo: "Em ơi viết PRD cho tính năng login"
   → AI viết generic, phải sửa nhiều

✅ Có repo: "Em ơi viết PRD cho tính năng login, tham khảo file 
   requirements/PRD-feature-X.md để đúng format của team mình"
   → AI viết đúng format, đúng style, tiết kiệm 60-70% thời gian
```

### 2. 📜 Lịch sử làm việc = tài sản của bạn

Mỗi commit = 1 dấu vết. Sau 6 tháng làm việc:
- Bạn có **portfolio** thực tế: đã làm gì, quyết định gì, thay đổi gì và vì sao
- PM/Manager xem được progress qua commit history
- Onboard người mới dễ hơn nhiều

### 3. 🔁 Tái sử dụng tài liệu thông minh

- Template PRD → dùng cho dự án mới
- Meeting note format → clone cho mọi buổi họp
- Checklist review → áp dụng lại mà không cần nhớ

---

---

# 💡 PHẦN 6 — Tips & Tricks cho BA

## Tip 1 — Viết commit message có ý nghĩa

```
❌ Tệ:   "update", "fix", "sửa file"

✅ Tốt:  "feat: thêm AC cho màn upload document"
         "fix: sửa lỗi typo trong PRD v2.1"
         "docs: cập nhật MoM họp ngày 04/03"
         "chore: tổ chức lại cấu trúc thư mục requirements"
```

**Format gợi ý:** `[loại]: [mô tả ngắn gọn]`

| Loại | Dùng khi |
|------|---------|
| `feat` | Thêm tài liệu/nội dung mới |
| `fix` | Sửa lỗi, sai sót |
| `docs` | Cập nhật tài liệu có sẵn |
| `chore` | Dọn dẹp, tổ chức file |
| `wip` | Work in progress, chưa hoàn thành |

---

## Tip 2 — Dùng Markdown như pro

Markdown học 10 phút là dùng được:

```markdown
# Tiêu đề lớn (H1)
## Tiêu đề vừa (H2)
### Tiêu đề nhỏ (H3)

**In đậm**
*In nghiêng*
~~Gạch ngang~~

- Bullet point
- Bullet point

1. Danh sách có số
2. Danh sách có số

- [ ] Todo chưa làm
- [x] Todo đã xong

> Blockquote — dùng cho note/warning

`inline code` hoặc

\```
code block
\```

| Cột 1 | Cột 2 |
|-------|-------|
| A     | B     |
```

> 🖼️ **[Ảnh cần có: Bên trái là raw Markdown, bên phải là preview hiển thị đẹp trên GitHub — đặt cạnh nhau để so sánh]**

---

## Tip 3 — Dùng GitHub Projects để quản lý sprint

GitHub có tính năng **Projects** (Kanban board miễn phí):

1. Trong repo → tab **"Projects"** → **"New project"**
2. Chọn template **"Board"** (Kanban)
3. Columns mặc định: `Todo` | `In Progress` | `Done`
4. Tạo Issue → kéo vào board → track progress

> 🖼️ **[Ảnh cần có: GitHub Projects board dạng Kanban — 3 cột Todo/In Progress/Done, có các card task trong từng cột]**

```
💡 Có thể link Issue vào card → khi đóng Issue thì card tự move sang Done
   Hoàn toàn miễn phí, không cần Jira cho các task nhỏ!
```

---

## Tip 4 — Pin repo quan trọng lên profile

Trên trang profile GitHub của bạn, có thể pin tối đa 6 repo để highlight:

1. Vào trang profile → click **"Customize your pins"**
2. Chọn repo muốn pin
3. Profile bạn trông "chuyên nghiệp" hơn hẳn khi chia sẻ với recruiter hoặc stakeholder

---

## Tip 5 — GitHub CLI hoặc GitHub.dev cho power user

Nếu đã quen rồi muốn nhanh hơn:

- **github.dev**: Mở bất kỳ repo nào → nhấn phím `.` → VS Code editor chạy ngay trên browser!
- **GitHub CLI**: `gh issue create`, `gh pr create`... dùng trong terminal

> 🖼️ **[Ảnh cần có: Nhấn dấu "." trên repo GitHub → màn hình chuyển sang github.dev với giao diện VS Code trên browser]**

---

---

# 🚀 Thực chiến — BA dùng GitHub thế nào?

## Case 1: Quản lý tài liệu PRD có version history

**Tình huống:** PM thay đổi requirement lần thứ 5, bạn muốn so sánh với version ban đầu.

**Workflow:**
```
Viết PRD v1 → commit "feat: PRD v1 màn login"
        ↓
PM yêu cầu thay → sửa → commit "fix: cập nhật AC theo feedback PM 04/03"
        ↓
Dev hỏi lại → vào Commits → xem diff từng thay đổi → trả lời chính xác
```

⏱️ **Tiết kiệm:** Không còn mở 5 file `PRD_v1_final_FINAL_ok.docx` để so sánh nữa 😂

---

## Case 2: Track sprint của BA với Issues + Projects

**Tình huống:** Sprint 3 có 12 task BA, cần biết đang ở đâu.

**Workflow:**
```
Tạo 12 Issues → label "sprint-3" → assign cho mình
        ↓
Kéo vào GitHub Projects board
        ↓
Mỗi ngày: move card, comment progress, close issue khi done
        ↓
Cuối sprint: nhìn board là biết làm được gì
```

---

## Case 3: Onboard BA mới vào dự án

**Tình huống:** BA mới join, cần hiểu context dự án trong 1 ngày.

**Workflow:**
```
Share link repo → BA mới đọc README.md (overview)
        ↓
Xem thư mục requirements/ → đọc PRD các feature
        ↓
Xem commit history → hiểu evolution của dự án
        ↓
Xem Issues → biết đang làm gì, còn gì pending
```

⏱️ **Tiết kiệm:** Không cần họp onboard 3 tiếng chỉ để giải thích context nữa

---

---

# 📚 Tài nguyên thêm

| Link | Mô tả |
|------|-------|
| [github.com](https://github.com) | Đăng ký tài khoản |
| [desktop.github.com](https://desktop.github.com) | Cài GitHub Desktop |
| [docs.github.com](https://docs.github.com/en/get-started) | Docs chính thức của GitHub |
| [www.markdownguide.org](https://www.markdownguide.org/cheat-sheet/) | Markdown cheatsheet |
| [git-scm.com](https://git-scm.com/downloads) | Cài Git |
| [github.com/features/project-management](https://github.com/features/project-management) | GitHub Projects (Kanban) |

---

# 🎁 Checklist để bookmark

```
SETUP BAN ĐẦU
□ Tạo tài khoản GitHub
□ Cài GitHub Desktop
□ Cài Git (nếu dùng Cursor/terminal)
□ Tạo repo đầu tiên (với README.md)
□ Tổ chức thư mục: requirements/, meeting-notes/, tasks/, templates/

HÀNG NGÀY
□ Sửa/thêm file → Commit với message có ý nghĩa
□ Tạo Issue cho task mới
□ Cập nhật checklist trong Issue khi có progress
□ Push lên GitHub

NÂNG CAO
□ Thử tạo Branch cho tài liệu mới
□ Tạo Pull Request → nhờ PM/peer review
□ Dùng GitHub Projects (Kanban) để track sprint
□ Thử nhấn "." trên repo → khám phá github.dev
```

---

# ⏭️ Bước tiếp theo

Khi đã có GitHub, bạn sẵn sàng bước vào thế giới **AI-augmented BA** thực sự:

👉 **[Đọc bài tiếp: Dùng Cursor MCP + Figma để đọc và edit design như một pro →](./bắt-đầu-vơi-cursor-mcp-figma.md)**

Bài đó sẽ hướng dẫn bạn kết nối **Cursor AI** với **Figma** — đọc màn hình design, review UX, thậm chí chỉnh sửa Figma từ... Cursor. Không cần đụng tay vào Figma nếu không muốn 🎨🤖

---

> 💬 **Feedback / câu hỏi?**  
> Thả vào Slack `#ai-ba-lab` hoặc tạo Issue ngay trong repo này nhé!  
> Happy committing! 🐙✌️
