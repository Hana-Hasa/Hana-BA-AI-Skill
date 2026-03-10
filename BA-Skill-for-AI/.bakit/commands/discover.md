# Command: /discover

> **Trigger:** Nhập `/discover` để bắt đầu quá trình Elicitation & Collaboration theo chuẩn IIBA BABOK v3.

---

## IIBA BABOK v3 Reference

| Trường | Nội dung |
|---|---|
| **Knowledge Area** | Chapter 4 — Elicitation and Collaboration |
| **Tasks** | 4.1 Prepare for Elicitation · 4.2 Conduct Elicitation · 4.3 Confirm Elicitation Results · 4.4 Communicate Business Analysis Information |
| **Core Techniques** | Interviews (9.16) · Brainstorming (9.3) · Focus Groups (9.11) · Observation (9.20) · Workshops (9.33) · Mind Mapping (9.18) |
| **Inputs** | Business Need · Stakeholder Engagement Approach · Existing Process / System Documentation |
| **Outputs** | Elicitation Results (Confirmed) → Business Requirements (unconfirmed) |

> 📚 Mục tiêu theo BABOK: *"Draw out, explore, and identify information relevant to the change from stakeholders and other sources."*

---

## Mô tả

`/discover` là điểm khởi đầu của mọi dự án hoặc tính năng mới.  
Command này giúp BA **đặt câu hỏi đúng**, **hiểu vấn đề thật sự** và **xác định scope** trước khi đi vào viết requirement — theo đúng tinh thần của BABOK Task **4.1 Prepare for Elicitation**: chuẩn bị kỹ trước khi hỏi.

Khi bạn gõ `/discover`, AI sẽ đóng vai **Business Analyst** kết hợp **Product Strategist**, dẫn dắt bạn qua một phiên elicitation có cấu trúc.

---

## Cách dùng

```
/discover

[Mô tả ngắn về tính năng / vấn đề / dự án cần khám phá]
```

**Ví dụ:**
```
/discover

Sản phẩm VKS cần thêm tính năng cho phép khách hàng tự đăng ký
tài khoản online thay vì phải qua nhân viên tư vấn.
```

---

## Agents được kích hoạt

| Agent | Vai trò |
|---|---|
| 🎯 Business Analyst | Dẫn dắt phiên elicitation, đặt câu hỏi khơi gợi yêu cầu |
| 🏗️ Product Strategist | Đánh giá business value và strategic fit |

---

## Skills được gọi

1. `discovery/problem-analysis.md` — phân tích Business Need (BABOK 4.1 input)
2. `discovery/elicitation-prep.md` — chuẩn bị câu hỏi, chọn technique phù hợp (BABOK 4.1)
3. `stakeholder-planning/stakeholder-mapper.md` — xác định stakeholder involvement (BABOK 4.4)
4. `discovery/user-research.md` — nếu có dữ liệu user cần tổng hợp (BABOK 4.3)

---

## AI sẽ làm gì

### Bước 1 — Prepare for Elicitation *(BABOK 4.1)*

Xác định scope và cách tiếp cận trước khi hỏi:
- Business Need là gì? Ai là stakeholder chủ chốt?
- Technique phù hợp: Interview 1-1, Workshop, hay Document Analysis?

### Bước 2 — Conduct Elicitation *(BABOK 4.2)*

Đặt câu hỏi theo 5 chiều để khám phá đầy đủ Business Requirements:

```
🎯 WHY    — Business Need thật sự là gì? (Business Objectives)
👤 WHO    — Stakeholder nào liên quan? (Stakeholder Analysis)
📋 WHAT   — Current State là gì? Future State mong muốn là gì?
⚙️ HOW   — Constraints và Assumptions nào đang tồn tại?
📏 SCOPE  — In Scope / Out of Scope là gì? (Solution Scope)
```

### Bước 3 — Confirm Elicitation Results *(BABOK 4.3)*

AI tổng hợp và xác nhận lại với bạn trước khi xuất output:

```
"Dựa trên thông tin bạn cung cấp, tôi hiểu như sau:
[tóm tắt ngắn]
Điều này có chính xác không? Có gì cần bổ sung?"
```

### Bước 4 — Output: Elicitation Summary *(BABOK 4.4)*

```markdown
## Elicitation Summary: [Tên tính năng / Dự án]
BABOK Reference: Elicitation & Collaboration — Ch.4

### Business Need
[Vấn đề thật sự cần giải quyết — 2–3 câu]

### Stakeholders Identified
| Stakeholder       | Role   | Interest Level | Involvement |
|---|---|---|---|
| [Tên / Nhóm]      |        | High/Med/Low   | Consult/Inform/Approve |

### Current State (As-Is)
[Quy trình / hệ thống đang hoạt động như thế nào]

### Future State (To-Be)
[Mong muốn sau khi implement]

### Solution Scope
✅ Trong scope:
- [Item 1]
❌ Ngoài scope:
- [Item 1]

### Assumptions & Constraints
- Assumption: [Điều được giả định là đúng]
- Constraint: [Ràng buộc không thể thay đổi]

### Open Questions (Elicitation Gaps)
- [Câu hỏi còn tồn đọng — cần elicitation thêm]

### Recommended Next Steps
→ /userstory — Chuyển Business Requirements thành Functional Requirements
→ /stakeholder — Lập Stakeholder Engagement Plan chi tiết hơn
```

---

## Tips

> 💡 **BABOK insight:** Một trong những sai lầm phổ biến nhất là đi thẳng vào "solution" mà bỏ qua bước xác định Business Need. `/discover` giúp bạn tránh cái bẫy này.

> ⚠️ Command này tương ứng với **Elicitation**, không phải **Requirements Analysis** — output là "raw requirements" chưa được phân tích. Dùng `/analyze-feature` hoặc `/userstory` cho bước tiếp theo.

> 🎯 **BABOK Technique gợi ý:** Nếu có nhiều stakeholder → dùng Workshop (9.33). Nếu chưa rõ vấn đề → dùng Root Cause Analysis (9.25) kết hợp Five Whys.

---

## Output liên quan

- → [`/userstory`](./userstory.md) — chuyển Business Requirements thành User Stories (RADD)
- → [`/analyze-feature`](./analyze-feature.md) — phân tích impact và risk (RADD + RLCM)
- → [`/stakeholder`](./stakeholder.md) — lập Stakeholder Engagement Plan (BA Planning)
