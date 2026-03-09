# 🧠 Skill là gì và cách hoạt động

> **Tác giả:** BA AI Team — VNG Hana
> **Đối tượng:** Business Analyst muốn hiểu và tự viết Skill cho AI
> **Ngày cập nhật:** 2026-03-09

---

## Tại sao bạn cần quan tâm đến Skill?

Bạn đã bao giờ phải lặp đi lặp lại cùng một yêu cầu cho AI chưa? Mỗi lần bắt đầu conversation mới, bạn lại phải giải thích ngữ cảnh, format đầu ra, quy tắc viết... Skill sinh ra để giải quyết đúng vấn đề đó — **đóng gói kiến thức và quy trình thành một "bộ não chuyên môn" mà AI có thể tái sử dụng mỗi khi cần**.

> 💡 Hãy tưởng tượng Skill giống như một **SOP (Standard Operating Procedure)** — nhưng thay vì dành cho con người đọc, nó được viết để AI đọc và thực thi.

---

## Skill là gì?

**Skill** là một tập hợp hướng dẫn (instructions) được đóng gói trong file Markdown (`.md`), giúp AI thực hiện một tác vụ cụ thể một cách nhất quán và chính xác. Ví dụ:

- Biến đổi tệp tin theo format chuẩn
- Trích xuất dữ liệu từ tài liệu
- Tạo mã lập trình theo pattern nhất định
- Tự động hóa một chuỗi bước công việc (flow nhiều tác vụ)

Mỗi Skill bao gồm:

| Thành phần | Vai trò |
|---|---|
| **YAML Frontmatter** (name + description) | "Nhãn" để AI nhận diện khi nào cần dùng Skill |
| **Thân SKILL.md** | Hướng dẫn chi tiết từng bước AI cần làm |
| **References/** | Tài liệu tham khảo bổ sung (style guide, glossary...) |
| **Scripts/** | Script hỗ trợ tái sử dụng (Python, JS...) |
| **Assets/** | Template, font, icon cho đầu ra |

```
skill-name/
├── SKILL.md              ← bắt buộc: frontmatter + hướng dẫn
├── references/           ← tùy chọn: tài liệu ngữ cảnh
│   └── writing-style.md
├── scripts/              ← tùy chọn: script hỗ trợ
└── assets/               ← tùy chọn: template, tài nguyên
    └── template.md
```

---

## Cách Skill hoạt động

Khi người dùng gửi yêu cầu cho AI, quy trình diễn ra như sau:

```
Người dùng gửi prompt
        ↓
AI đọc "description" của tất cả Skill có sẵn
        ↓
AI đánh giá: "Yêu cầu này có khớp với Skill nào không?"
        ↓
  ┌─ Có → Kích hoạt Skill, đọc toàn bộ SKILL.md, thực thi theo hướng dẫn
  └─ Không → AI tự xử lý bằng kiến thức chung
```

> ⚠️ **Điểm quan trọng:** AI chỉ kích hoạt Skill khi nó đánh giá rằng yêu cầu phù hợp. Vì vậy phần `description` trong YAML frontmatter cực kỳ quan trọng — nó là "cơ chế kích hoạt" chính.

---

## Ưu điểm và nhược điểm của Skill

### ✅ Ưu điểm

| Ưu điểm | Giải thích |
|---|---|
| **Nhất quán** | Mỗi lần chạy, AI đều tuân theo cùng một quy trình — không bỏ bước, không quên format |
| **Tái sử dụng** | Viết một lần, dùng mãi. Chia sẻ cho cả team cùng sử dụng |
| **Giảm prompt lặp lại** | Không cần giải thích lại ngữ cảnh mỗi conversation mới |
| **Kiểm soát chất lượng** | Đầu ra có thể đo lường, so sánh, cải tiến qua từng phiên bản |
| **Mở rộng được** | Có thể ghép nhiều Skill lại hoặc thêm script hỗ trợ |
| **Dễ bảo trì** | Sửa SKILL.md là thay đổi hành vi AI ngay lập tức, không cần code |

### ❌ Nhược điểm

| Nhược điểm | Giải thích |
|---|---|
| **Tốn token** | Toàn bộ nội dung SKILL.md được nạp vào context mỗi lần kích hoạt — Skill dài = tốn token = tốn tiền |
| **Cần đầu tư thời gian viết** | Skill tốt cần qua nhiều vòng test và cải tiến, không phải viết xong là xài được ngay |
| **Kích hoạt sai** | Nếu description viết không chính xác, AI có thể gọi Skill khi không cần (false positive) hoặc bỏ lỡ khi cần (false negative) |
| **Giới hạn bởi context window** | Skill quá dài + prompt người dùng dài = có thể vượt giới hạn context của model |
| **Cứng nhắc nếu viết quá chi tiết** | Skill quá nhiều quy tắc "BẮT BUỘC/KHÔNG BAO GIỜ" sẽ khiến AI mất linh hoạt trong các tình huống ngoại lệ |

---

## 💡 Cách viết Skill tốn ít token

Đây là phần quan trọng nhất mà nhiều người bỏ qua. Mỗi token đều có chi phí — Skill ngắn mà đủ ý luôn tốt hơn Skill dài mà rườm rà.

### Nguyên tắc 1 — Giữ SKILL.md dưới 500 dòng

Nếu vượt quá, tách nội dung chi tiết sang `references/` và chỉ tham chiếu từ SKILL.md:

```markdown
## Writing Style
> See `references/writing-style.md` for full rules. Key points:
> - Tone: friendly colleague
> - Explain "why" before "how"
```

> 💡 AI chỉ đọc file references khi SKILL.md chỉ dẫn đến — giúp tiết kiệm token khi reference không cần thiết.

### Nguyên tắc 2 — Dùng câu mệnh lệnh, bỏ từ thừa

```
❌ "Bạn cần phải đảm bảo rằng bước tiếp theo là kiểm tra xem file đầu vào
    có đúng format hay không trước khi tiến hành xử lý"

✅ "Kiểm tra format file đầu vào trước khi xử lý"
```

### Nguyên tắc 3 — Dùng bảng và bullet thay vì đoạn văn

Bảng và bullet list truyền tải thông tin dày đặc hơn paragraph, giúp AI parse nhanh hơn và tốn ít token hơn.

### Nguyên tắc 4 — Tránh lặp lại hướng dẫn

Nếu một quy tắc đã nêu ở phần trên, không cần nhắc lại ở phần dưới. AI đọc toàn bộ file, không quên giữa các section.

### Nguyên tắc 5 — Dùng example thay vì giải thích dài

```
❌ "Đầu ra cần được format theo dạng bảng Markdown, với cột đầu tiên là tên
    field, cột thứ hai là kiểu dữ liệu, cột thứ ba là mô tả, và mỗi hàng
    tương ứng với một field trong API response..."

✅ "Output format:"
   | Field | Type | Description |
   |-------|------|-------------|
   | name  | string | Tên người dùng |
   | age   | number | Tuổi |
```

### Nguyên tắc 6 — Dùng script thay vì hướng dẫn lặp

Nếu AI phải lặp lại một khối logic giống nhau ở nhiều bài test, hãy viết một script hỗ trợ (ví dụ: `scripts/format_output.py`) và gắn vào Skill. AI gọi script thay vì tự viết lại logic mỗi lần — nhanh hơn, ít token hơn, ít lỗi hơn.

### Nguyên tắc 7 — Description ngắn gọn nhưng đủ trigger

```yaml
# Tốt — 1 dòng, rõ ràng, có trigger phrases
description: Tạo PRD từ meeting notes cho BA team. Dùng khi user nói "viết PRD",
  "tạo PRD", "chuyển meeting notes thành PRD".

# Không tốt — quá dài, mô tả chung chung
description: Đây là skill giúp Business Analyst có thể tạo ra một Product
  Requirements Document chuyên nghiệp từ nhiều nguồn đầu vào khác nhau bao gồm
  nhưng không giới hạn ở meeting notes, email, chat log...
```

---

## 🔄 Action nhiều tác vụ theo flow

Trong thực tế, một yêu cầu của BA thường không chỉ là "làm một việc" mà là một **chuỗi các bước nối tiếp nhau** (flow). Skill hỗ trợ điều này thông qua phần **Step-by-Step Instructions**.

### Cách thiết kế flow nhiều tác vụ trong Skill

**Bước 1 — Vẽ flow trước khi viết**

Trước khi viết Skill, hãy vẽ ra chuỗi tác vụ bằng diagram:

```
Input (meeting notes)
    ↓
Step 1: Trích xuất key decisions
    ↓
Step 2: Phân loại theo epic/feature
    ↓
Step 3: Viết user stories cho từng feature
    ↓
Step 4: Tạo acceptance criteria
    ↓
Step 5: Format thành PRD template
    ↓
Output (PRD hoàn chỉnh)
```

**Bước 2 — Mỗi step là một action rõ ràng**

Mỗi step trong SKILL.md cần:
1. **Tên action** bắt đầu bằng động từ (Trích xuất, Phân loại, Viết, Tạo, Format...)
2. **Tại sao step này quan trọng** (1 câu)
3. **Input của step** — lấy từ đâu (từ user hay từ output của step trước)
4. **Output của step** — tạo ra gì, format nào
5. **Ví dụ** expected result

```markdown
### Step 1 — Trích xuất key decisions từ meeting notes

Meeting notes thường dài và lẫn nhiều thông tin không liên quan.
Bước này lọc ra chỉ những quyết định quan trọng.

1. Đọc toàn bộ meeting notes
2. Tìm các câu chứa từ khóa: "quyết định", "đồng ý", "sẽ làm", "deadline"
3. Liệt kê thành danh sách bullet

**Output:**
- Quyết định 1: Dùng React cho frontend — deadline 15/03
- Quyết định 2: API dùng REST, không dùng GraphQL
```

**Bước 3 — Kết nối các step bằng output → input**

Đảm bảo output của step trước là input của step sau. Ghi rõ trong hướng dẫn:

```markdown
### Step 2 — Phân loại decisions theo epic/feature

Dùng danh sách decisions từ Step 1, nhóm chúng theo epic hoặc feature.
```

> 💡 **Mẹo:** Nếu flow có bước rẽ nhánh (ví dụ: "nếu có API thì làm X, nếu không thì làm Y"), hãy viết rõ điều kiện trong Skill. AI xử lý logic if/else rất tốt nếu bạn mô tả rõ ràng.

### Ví dụ flow phức tạp — Skill review code cho BA

```
Input: Pull Request URL
    ↓
Step 1: Đọc PR description + diff
    ↓
Step 2: Kiểm tra PR có ảnh hưởng đến business logic không?
    ├─ Có → Step 3a: Liệt kê business rules bị thay đổi
    └─ Không → Step 3b: Tóm tắt thay đổi technical
    ↓
Step 4: Tạo review checklist cho BA
    ↓
Step 5: Viết comment review bằng tiếng Việt
    ↓
Output: Review comment sẵn sàng paste vào PR
```

### Khi nào nên tách flow thành nhiều Skill?

| Tình huống | Nên làm gì |
|---|---|
| Flow dưới 5 steps, các step liên quan chặt | Giữ trong 1 Skill |
| Flow trên 7 steps hoặc có step dùng lại ở flow khác | Tách thành nhiều Skill, gọi lần lượt |
| Step có logic phức tạp cần script riêng | Viết script vào `scripts/`, gọi từ Skill |

---

## 🛠️ Quy trình tạo Skill chuẩn — 7 bước

```
1. Capture Intent    → Xác định mục tiêu, đối tượng, trigger
2. Write SKILL.md    → Viết nháp theo template chuẩn
3. Build Test Cases  → Tạo 2-3 prompt kiểm thử thực tế
4. Run & Evaluate    → Chạy thử, so sánh có/không Skill
5. Improve           → Loại bỏ hướng dẫn rườm rà, thêm script nếu cần
6. Optimize Trigger  → Tinh chỉnh description để AI kích hoạt đúng
7. Package           → Đóng gói thành folder chuẩn, sẵn sàng chia sẻ
```

### Chi tiết từng bước

**1. Capture Intent — Trả lời 5 câu hỏi**

| # | Câu hỏi | Ví dụ |
|---|---------|-------|
| 1 | Skill này giúp AI làm gì? | Tạo PRD từ meeting notes |
| 2 | Ai sẽ dùng? | BA team, không biết code |
| 3 | Khi nào kích hoạt? | User nói "viết PRD", "tạo PRD" |
| 4 | Output tốt trông như thế nào? | File MD, tiếng Việt, theo template công ty |
| 5 | Có ví dụ nào để tham khảo? | PRD cũ trong Confluence |

**2. Write SKILL.md — Theo template chuẩn**

```yaml
---
name: [Tên skill — tối đa 64 ký tự]
description: [Làm gì + khi nào trigger. Tối đa 200 ký tự.]
---
```

Các section bắt buộc: When to Use, Inputs, Output Format, Step-by-Step Instructions, Examples, Limitations.

**3-4. Test & Evaluate — So sánh A/B**

Tạo prompt thực tế, chạy 2 phiên: một có Skill, một không. So sánh:
- Chất lượng output
- Thời gian xử lý
- Số token tiêu thụ
- Tỷ lệ đúng format

**5. Improve — Cắt bỏ mỡ thừa**

- Xóa hướng dẫn mà AI vẫn làm đúng khi không có (vì đã nằm trong kiến thức chung)
- Thay paragraph bằng bảng/bullet
- Chuyển logic lặp thành script

**6. Optimize Trigger — Viết description "pushy"**

```yaml
# Pattern:
description: [Động từ] [sản phẩm đầu ra] cho [đối tượng].
  Dùng khi [trigger 1], [trigger 2], hoặc [trigger 3].
```

**7. Package — Kiểm tra trước khi giao**

```
SKILL QUALITY CHECK
□ YAML frontmatter có name + description hợp lệ
□ Description ≤ 200 ký tự, có trigger phrases
□ Có section "When to Use"
□ Mỗi step giải thích "tại sao" trước "làm gì"
□ Output format/template được định nghĩa rõ
□ Ít nhất 1 ví dụ (input → output)
□ Có section Limitations
□ SKILL.md dưới 500 dòng
□ Nội dung dài đã tách sang references/
```

---

## 🎯 Tóm tắt

| Bạn muốn... | Hãy nhớ... |
|---|---|
| Hiểu Skill là gì | SOP cho AI — đóng gói hướng dẫn để AI thực thi nhất quán |
| Viết Skill tốn ít token | Dưới 500 dòng, câu mệnh lệnh, dùng bảng, tách references, dùng example thay giải thích |
| Tạo flow nhiều tác vụ | Vẽ diagram trước, mỗi step có input/output rõ ràng, nối output → input giữa các step |
| Tránh lỗi phổ biến | Đừng viết quá nhiều quy tắc cứng, test description kỹ để tránh kích hoạt sai |

> 💡 **Skill tốt nhất không phải Skill dài nhất — mà là Skill ngắn nhất vẫn cho kết quả đúng.**
