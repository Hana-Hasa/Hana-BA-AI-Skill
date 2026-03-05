---
name: BA How-To Writing Style Guide
description: Viết tài liệu hướng dẫn kỹ thuật cho BA non-tech theo chuẩn Hana BA — cấu trúc từng bước, văn phong thân thiện tiếng Việt, có emoji, code block, bảng so sánh, case study thực tế và checklist.
---

# Mục đích của Skill này

Skill này giúp AI tạo ra các tài liệu hướng dẫn **kỹ thuật dành cho BA non-tech** theo đúng phong cách đang được áp dụng trong series "Bướ![1772678383454](image/skill-how-to/1772678383454.png)c đầu trở thành BA AI thực thụ" của team VNG Hana.

Khi được yêu cầu viết hướng dẫn (how-to, tutorial, setup guide, onboarding doc...), AI phải tuân thủ cấu trúc, văn phong và các quy tắc dưới đây.

---

# PHẦN 1 — Cấu trúc bắt buộc của một bài hướng dẫn

Mỗi bài hướng dẫn **phải có đủ** các thành phần sau, theo đúng thứ tự:

## 1.1 — Tiêu đề H1

```
# [emoji phù hợp] [Tên chủ đề ngắn gọn] — [Tagline hấp dẫn giải thích bài dùng để làm gì]
```

**Ví dụ:**
```
# 🐙 Bước đầu trở thành BA AI thực thụ — Làm quen với GitHub
# 🎨 BA x AI x Figma — Cẩm nang "đu trend" MCP Figma với Cursor
```

Tiêu đề phải: ngắn, có emoji liên quan, phần sau `—` giải thích bài dùng làm gì.

---

## 1.2 — Block metadata (header)

```markdown
> ✍️ **Tác giả:** [tên tác giả hoặc team]
> 🗓️ **Ngày viết:** [Tháng M/YYYY]
> 🎯 **Dành cho:** [mô tả đối tượng cụ thể]
> 📚 **Series:** [tên series — Bài N/N] ← chỉ thêm nếu là bài trong series
```

---

## 1.3 — Section "Why should you care?" (Lời mở đầu)

- Bắt đầu bằng **pain point thực tế** của người đọc — không bắt đầu bằng định nghĩa kỹ thuật
- Mô tả "trước đây làm thế nào" vs "bây giờ làm được gì"
- Kết bằng 1 câu kêu gọi đọc tiếp
- Tone: nhẹ nhàng, đồng cảm, có thể dùng emoji cảm xúc

**Ví dụ cấu trúc:**
```
[Mô tả cách làm cũ mệt mỏi như thế nào]

Nhưng giờ khác rồi! Với [công cụ/phương pháp], bạn có thể:
- [benefit 1]
- [benefit 2]
- [benefit 3]

[Câu hook → đọc tiếp]
```

---

## 1.4 — Roadmap tổng quan

Dùng code block để tóm tắt cấu trúc bài hoặc các hành trình:

```
1. [Tên phần 1]
2. [Tên phần 2]
3. [Tên phần 3]
...
```

Hoặc dạng so sánh 2 hành trình:

```
Hành trình 1: [Tên]  →  [Công cụ]  (mục đích ngắn)
Hành trình 2: [Tên]  →  [Công cụ]  (mục đích ngắn)
```

---

## 1.5 — Các PHẦN / HÀNH TRÌNH chính

Mỗi phần lớn dùng `# H1 IN HOA` với emoji và tên rõ ràng:

```markdown
# 🛤️ HÀNH TRÌNH 1 — [Tên hành trình]
# 🧠 PHẦN 1 — [Tên phần]
```

Bên trong mỗi phần: chia thành các **Step** đánh số từ 1.

---

## 1.6 — Các Step (bước thực hành)

```markdown
## Step N — [Tên bước ngắn gọn, bắt đầu bằng động từ]
```

Mỗi step bao gồm:
1. **Mô tả ngắn** (1-2 câu) tại sao làm bước này
2. **Danh sách hành động** đánh số hoặc bullet
3. **Code block** nếu có lệnh/config cần copy
4. **Kết quả mong đợi** — chỉ rõ ✅ thành công trông như thế nào
5. **Placeholder ảnh** (nếu cần visual)

**Mẫu code block kết quả:**
```
✅ Thành công: [mô tả trạng thái thành công]
❌ Lỗi: [mô tả lỗi thường gặp và cách fix]
```

---

## 1.7 — Bảng tóm tắt cuối mỗi hành trình

```markdown
## ✅ [Tên hành trình] — Tóm tắt

| Bước | Việc cần làm |
|------|-------------|
| 1    | [action]    |
| 2    | [action]    |
```

Kèm danh sách **"Dùng được để làm gì"** và **"Không làm được gì"** bằng ✅/❌.

---

## 1.8 — Section Tips & Tricks

```markdown
# 💡 Tips & Tricks cho BA

### [Số]. [Tên tip ngắn gọn]
[Nội dung]
```

---

## 1.9 — Section Thực chiến (Case Study)

```markdown
# 🚀 Thực chiến — Case study thực tế

## Case [N]: [Tên tình huống]

> "[Câu prompt/yêu cầu thực tế người dùng đã gõ]"

**AI đã làm:**
- [action 1]
- [action 2]

⏱️ **Tiết kiệm:** [mô tả thời gian/công sức tiết kiệm được]
```

---

## 1.10 — Bảng Tài nguyên

```markdown
# 📚 Tài nguyên thêm

| Link | Mô tả |
|------|-------|
| [tên](url) | [mô tả ngắn] |
```

---

## 1.11 — Checklist tổng (bookmark-able)

Luôn kết thúc bằng checklist trong code block — người đọc có thể bookmark lại:

```
TÊN HÀNH TRÌNH
□ [bước 1]
□ [bước 2]
□ [bước 3]
```

---

## 1.12 — Footer

```markdown
> 💬 **Feedback / câu hỏi?**
> Thả vào Slack `#[tên channel]` hoặc tạo Issue ngay trong repo này nhé!
> [Câu kết vui vẻ phù hợp chủ đề] ✌️
```

---

---

# PHẦN 2 — Quy tắc văn phong

## 2.1 — Giọng điệu (Tone of Voice)

| Nên | Không nên |
|-----|-----------|
| Thân thiện như đồng nghiệp nói chuyện | Formal như văn bản hành chính |
| "bạn", "mình", "team mình" | "quý vị", "người dùng", "độc giả" |
| "Mệt lắm bạn ơi 😮‍💨" | "Đây là một thách thức không nhỏ" |
| Nhẹ nhàng thừa nhận khó khăn | Pretend mọi thứ đơn giản |
| Hỏi ngược lại ("Nghe bá đạo không?") | Độc thoại một chiều |

---

## 2.2 — Cách giải thích khái niệm kỹ thuật

**Luôn dùng analogy quen thuộc trước khi giải thích kỹ thuật:**

```
❌ "Git là distributed version control system"

✅ "Git như Google Docs có track changes — nhưng mạnh hơn nhiều,
   và chạy ngay trên máy bạn"
```

**Luôn trả lời "Tại sao?" trước "Làm thế nào?":**

```
❌ [Step 1 ngay lập tức]

✅ [1-2 câu giải thích tại sao bước này cần thiết]
   → [rồi mới đến các action cụ thể]
```

---

## 2.3 — Emoji

- Dùng emoji **có chủ đích**, không spam
- Mỗi section/phần lớn: 1 emoji đặc trưng ở đầu heading
- Trong nội dung: dùng để nhấn mạnh hoặc tạo nhịp điệu
- Checklist: dùng ✅ ❌ □ nhất quán
- Cảm xúc: 😅 😮‍💨 🎉 ✌️ dùng tự nhiên, không gượng

**Bộ emoji chuẩn theo loại nội dung:**

| Loại | Emoji |
|------|-------|
| Hành trình / con đường | 🛤️ 🚀 |
| Lý thuyết / khái niệm | 🧠 📚 |
| Thực hành / setup | 🛠️ ⚙️ |
| Mẹo / tricks | 💡 |
| Cảnh báo | ⚠️ |
| So sánh / tổng kết | 🎯 📊 |
| Tài nguyên | 📚 🔗 |
| Checklist | 🎁 ✅ |
| Case study | 🚀 ⏱️ |
| Placeholder ảnh | 🖼️ |

---

## 2.4 — Code blocks

Dùng code block cho:
- Lệnh terminal/shell
- File config (JSON, YAML...)
- ASCII flow diagram
- Ví dụ trước/sau (❌ tệ vs ✅ tốt)
- Checklist bookmark
- Kết quả mong đợi (✅/❌)

**Luôn ghi ngôn ngữ** khi có syntax highlighting: ` ```json `, ` ```bash `, ` ```powershell `

**Dùng code block không có ngôn ngữ** cho flow diagram, checklist, kết quả text thuần.

---

## 2.5 — Blockquotes

| Ký hiệu | Dùng khi |
|---------|----------|
| `> 💡` | Tip bổ sung, thông tin hay biết |
| `> ⚠️` | Cảnh báo, điều kiện bắt buộc, gotcha |
| `> 🖼️` | Placeholder cho ảnh cần chụp/cung cấp sau |
| `> 💬` | Câu hỏi thường gặp (FAQ inline) |
| `> 🎯` | Rule of thumb, nguyên tắc chọn lựa |

---

## 2.6 — Bảng (Tables)

Dùng table khi so sánh 2+ thứ. Luôn có cột tiêu đề rõ ràng.

Cột so sánh dùng: ✅ (có/tốt), ❌ (không/xấu), ⚠️ (có nhưng hạn chế).

**Mẫu bảng so sánh 2 options:**

```markdown
| | **Option A** | **Option B** |
|---|---|---|
| **Điểm X** | ✅ Tốt | ❌ Không có |
| **Điểm Y** | ⚠️ Hạn chế | ✅ Đầy đủ |
```

---

---

# PHẦN 3 — Quy tắc đặc biệt cho BA non-tech

## 3.1 — Giả định về người đọc

Luôn viết cho người:
- **Không biết code**, không quen dòng lệnh
- **Biết công việc BA**: PRD, user story, wireframe, meeting notes, Jira
- **Đang dùng**: Windows (chủ yếu), Mac (một số)
- **Mục tiêu**: Dùng AI để làm việc nhanh hơn, không phải học lập trình

---

## 3.2 — Khi đề cập lệnh terminal

- Luôn cung cấp **cả Windows và Mac** nếu khác nhau
- Giải thích **tác dụng của lệnh** trước khi đưa lệnh
- Sau lệnh, luôn có **cách kiểm tra thành công**

**Mẫu:**
```markdown
Kiểm tra cài thành công:
```bash
bun --version
# Kết quả: 1.x.x là thành công ✅
```
```

---

## 3.3 — Luôn nói rõ giới hạn

Sau mỗi hành trình/tool, phải có section **"Giới hạn cần biết"** hoặc block ⚠️ liệt kê rõ:
- Điều công cụ **không làm được**
- Lý do tại sao (để người đọc không nghĩ mình làm sai)
- Cách workaround (nếu có)

---

## 3.4 — Placeholder ảnh

Khi biết cần ảnh minh họa mà chưa có, thêm placeholder:

```markdown
> 🖼️ *[Ảnh: mô tả cụ thể cần chụp/vẽ gì, ở đâu, highlight element nào]*
```

Ví dụ:
```markdown
> 🖼️ *[Ảnh: Figma Preferences → Enable local MCP server được toggle ON]*
```

---

---

# PHẦN 4 — Ví dụ đầu ra mong đợi

Khi nhận yêu cầu: *"Viết hướng dẫn setup Notion cho BA"*

AI phải tạo ra file `.md` có đủ:

```
✅ H1 tiêu đề + emoji
✅ Block metadata (tác giả, ngày, đối tượng)
✅ Section "Tại sao BA cần Notion?" — bắt đầu bằng pain point
✅ Roadmap code block
✅ Các PHẦN chia rõ ràng
✅ Step 1..N với action + kết quả mong đợi + placeholder ảnh
✅ Bảng tóm tắt cuối mỗi phần
✅ Tips & Tricks
✅ Ít nhất 1 Case Study thực tế với ⏱️ tiết kiệm
✅ Bảng tài nguyên
✅ Checklist bookmark trong code block
✅ Footer với kênh feedback
```

---

# PHẦN 5 — Checklist trước khi publish

```
KIỂM TRA TRƯỚC KHI PUBLISH
□ Tiêu đề H1 có emoji và tagline rõ ràng
□ Đã có block metadata (tác giả, ngày, đối tượng)
□ Bài mở đầu bằng pain point, không bằng định nghĩa
□ Mỗi bước đều có kết quả mong đợi (✅/❌)
□ Lệnh terminal đều có cả Windows + Mac
□ Đã thêm placeholder ảnh cho những điểm cần visual
□ Đã nêu giới hạn/gotcha của công cụ
□ Có ít nhất 1 case study thực tế
□ Có checklist bookmark ở cuối
□ Footer có kênh feedback
□ File đặt tên dạng kebab-case tiếng Việt không dấu hoặc có dấu (nhất quán với repo)
```
