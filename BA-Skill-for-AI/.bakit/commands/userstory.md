# Command: /userstory

> **Trigger:** Nhập `/userstory` để Specify & Model Requirements theo chuẩn IIBA BABOK v3.

---

## IIBA BABOK v3 Reference

| Trường | Nội dung |
|---|---|
| **Knowledge Area** | Chapter 6 — Requirements Analysis and Design Definition (RADD) |
| **Tasks** | 6.1 Specify and Model Requirements · 6.2 Verify Requirements · 6.3 Validate Requirements |
| **Core Techniques** | User Stories (9.33) · Acceptance and Evaluation Criteria (9.1) · Use Cases and Scenarios (9.30) · Functional Decomposition (9.12) · Business Rules Analysis (9.4) |
| **Inputs** | Elicitation Results (Confirmed) từ `/discover` · Stakeholder Needs |
| **Outputs** | Requirements (Specified & Modelled) · Requirements Verification Results |

> 📚 Mục tiêu theo BABOK: *"Analyze, synthesize, and refine elicitation results into requirements and designs."*

---

## Mô tả

`/userstory` giúp BA chuyển Business Requirements (output của `/discover`) thành **Functional Requirements** dạng User Story — có cấu trúc, testable, và đã được verify theo tiêu chuẩn IIBA.

BABOK v3 nhấn mạnh: requirements phải đồng thời **Verified** (đúng cấu trúc, không mâu thuẫn) và **Validated** (thật sự phản ánh nhu cầu stakeholder). AI sẽ kiểm tra cả hai.

---

## Cách dùng

**Cách 1 — Từ mô tả tính năng:**
```
/userstory

[Mô tả tính năng cần viết user story]
```

**Cách 2 — Từ Elicitation Summary của /discover:**
```
/userstory

[Paste Elicitation Summary]
```

**Ví dụ:**
```
/userstory

Khách hàng muốn tự đăng ký tài khoản VKS online.
Họ cần nhập thông tin cá nhân, upload CCCD và chờ duyệt.
Sau khi duyệt sẽ nhận email thông báo.
```

---

## Agents được kích hoạt

| Agent | Vai trò |
|---|---|
| 📋 Business Analyst | Specify & Model Requirements (BABOK 6.1) |
| 🧪 QA Engineer | Verify Requirements — AC có đủ testable không? (BABOK 6.2) |

---

## Skills được gọi

1. `requirement/userstory-writing.md` — Specify & Model (BABOK 6.1)
2. `requirement/acceptance-criteria.md` — Acceptance and Evaluation Criteria Technique (BABOK 9.1)
3. `requirement/edgecase-discovery.md` — Use Cases and Scenarios (BABOK 9.30)
4. `requirement/requirements-verifier.md` — Verify Requirements (BABOK 6.2)

---

## AI sẽ làm gì

### Bước 1 — Specify and Model Requirements *(BABOK 6.1)*

AI phân tích input và xác định:
- Actors (stakeholders tương tác với hệ thống)
- Business Events (điều gì kích hoạt use case)
- Pre/Post Conditions
- Business Rules áp dụng

### Bước 2 — Sinh User Stories theo chuẩn

Mỗi user story theo format:

```markdown
## US-[XX]: [Tên ngắn — dạng động từ hành động]

**As a** [role — actor cụ thể, không dùng "user" chung chung]
**I want to** [action — hành động rõ ràng]
**So that** [business value — lợi ích đo được]

### Acceptance Criteria *(BABOK Technique 9.1)*
- [ ] AC1: Given [precondition] / When [trigger/action] / Then [observable result]
- [ ] AC2: Given [precondition] / When [trigger/action] / Then [observable result]
- [ ] AC3: (negative/exception scenario)

### Edge Cases & Exception Flows *(Use Cases & Scenarios — BABOK 9.30)*
- ❗ [Exception 1] → System response: [...]
- ❗ [Exception 2] → System response: [...]

### Business Rules Applied *(Business Rules Analysis — BABOK 9.4)*
- BR-[XX]: [Quy tắc nghiệp vụ ràng buộc story này]

### Out of Scope
- ❌ [Điều không thuộc story này]

### Dependencies
- Depends on: [US-XX | External System | API]
```

### Bước 3 — Verify Requirements *(BABOK 6.2)*

AI kiểm tra theo **BABOK Verification Criteria**:

```
BABOK Requirements Quality Check:
✅ Atomic      — Mỗi AC kiểm tra đúng 1 điều kiện
✅ Complete    — Không thiếu scenario quan trọng
✅ Consistent  — Không mâu thuẫn với US khác
✅ Concise     — Ngắn gọn, không thừa
✅ Feasible    — Có thể implement được
✅ Unambiguous — Chỉ có một cách hiểu
✅ Testable    — QA có thể viết test case từ AC

[+ INVEST Check cho User Story format]
✅ Independent · Negotiable · Valuable · Estimable · Small · Testable
```

### Bước 4 — Validate Requirements *(BABOK 6.3)*

AI đặt câu hỏi validation để bạn xác nhận:

```
"Story US-01 có phản ánh đúng nhu cầu của [actor] không?
Business value 'So that...' có đo được không, hay cần cụ thể hơn?"
```

---

## Output mẫu

```markdown
## US-01: Đăng ký tài khoản VKS online
BABOK: RADD — Specify & Model Requirements (6.1)

**As a** khách hàng mới chưa có tài khoản VKS
**I want to** tự hoàn thành đăng ký tài khoản qua web/app
**So that** tôi có thể sử dụng dịch vụ mà không cần đến văn phòng

### Acceptance Criteria
- [ ] AC1: Given chưa có tài khoản / When điền đúng form + CCCD hợp lệ / Then tạo hồ sơ + gửi email "đang chờ duyệt" trong 5 phút
- [ ] AC2: Given CCCD đã hết hạn / When upload / Then hiển thị lỗi "CCCD không còn hiệu lực, vui lòng dùng CCCD mới"
- [ ] AC3: Given email đã tồn tại / When submit / Then hiển thị "Email đã được đăng ký, thử Đăng nhập"

### Business Rules
- BR-01: CCCD phải còn hiệu lực (ngày hết hạn > ngày đăng ký)
- BR-02: Mỗi email chỉ được đăng ký 1 tài khoản

### Edge Cases
- ❗ Mất kết nối giữa chừng → Lưu form nháp, cho tiếp tục sau
- ❗ CCCD ảnh mờ / không đọc được → Yêu cầu chụp lại, có hướng dẫn

BABOK Verify: ✅ 7/7 criteria passed
```

---

## Tips

> 💡 **BABOK insight:** Business Rules (9.4) thường là nguồn gốc của exception flows — hỏi "quy tắc nào ràng buộc hành động này?" để tìm AC bị thiếu.

> ⚠️ BABOK phân biệt rõ **Verify** (đúng cấu trúc, không mâu thuẫn) vs **Validate** (phản ánh đúng nhu cầu thật). Cả hai đều cần làm trước khi chuyển sang dev.

> 🎯 Dùng **Functional Decomposition (9.12)** khi feature lớn: tách thành hierarchy trước, rồi viết story cho từng leaf node.

---

## Output liên quan

- → [`/analyze-feature`](./analyze-feature.md) — phân tích impact & risk của stories (RADD 6.4 + RLCM)
- → [`/testcase`](./testcase.md) — sinh test case từ AC (Solution Evaluation)
- → [`/write-doc`](./write-doc.md) — đưa stories vào SRS/PRD (Documentation)
