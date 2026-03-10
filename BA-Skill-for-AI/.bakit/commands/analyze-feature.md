# Command: /analyze-feature

> **Trigger:** Nhập `/analyze-feature` để thực hiện Requirements Analysis & Design Definition kết hợp Requirements Life Cycle Management theo chuẩn IIBA BABOK v3.

---

## IIBA BABOK v3 Reference

| Trường | Nội dung |
|---|---|
| **Knowledge Areas** | Ch.6 — Requirements Analysis & Design Definition (RADD) · Ch.5 — Requirements Life Cycle Management (RLCM) |
| **Tasks** | 6.4 Define Requirements Architecture · 6.5 Define Design Options · 5.4 Assess Requirements Changes · 7.3 Assess Risks |
| **Core Techniques** | Impact Analysis (9.21) · Risk Analysis and Management (9.26) · Dependency Mapping · Decision Analysis (9.8) · Non-functional Requirements Analysis (9.19) |
| **Inputs** | Requirements (Specified) từ `/userstory` · Business Case · Current State Architecture |
| **Outputs** | Requirements Architecture · Design Options · Risk Assessment · Change Impact |

> 📚 Mục tiêu theo BABOK: *"Understand how requirements relate to one another and to the overall solution, and assess risks and constraints."*

---

## Mô tả

`/analyze-feature` thực hiện **Requirements Architecture** (BABOK 6.4) — nhìn tính năng không chỉ theo chiều dọc (user → hệ thống) mà còn theo **chiều ngang**: tính năng này ảnh hưởng đến đâu, phụ thuộc vào gì, rủi ro là gì.

Đây là bước **bắt buộc** trước khi đưa requirements vào sprint — nhiều bug và scope creep đến từ việc bỏ qua bước này.

AI sẽ đóng vai **Business Analyst** + **Solution Architect** + **QA Engineer** cùng lúc.

---

## Cách dùng

**Cách 1 — Từ mô tả tính năng:**
```
/analyze-feature

[Mô tả tính năng]
```

**Cách 2 — Từ User Stories đã viết:**
```
/analyze-feature

[Paste US-01, US-02... từ /userstory]
```

**Ví dụ:**
```
/analyze-feature

Tính năng: Khách hàng tự đăng ký tài khoản VKS online
- US-01: Đăng ký qua web/app với CCCD
- US-02: Duyệt tự động qua eKYC, gửi email kết quả
```

---

## Agents được kích hoạt

| Agent | Vai trò |
|---|---|
| 📋 Business Analyst | Requirements Architecture, Business Impact |
| 🏗️ Solution Architect | Technical Impact, Design Options (BABOK 6.5) |
| 🧪 QA Engineer | Risk Identification, Edge Cases, Testability |

---

## Skills được gọi

1. `system-analysis/impact-analysis.md` — Impact Analysis Technique (BABOK 9.21)
2. `system-analysis/dependency-analysis.md` — Requirements Architecture (BABOK 6.4)
3. `system-analysis/risk-analysis.md` — Risk Analysis & Management (BABOK 9.26)
4. `requirement/edgecase-discovery.md` — Use Cases & Scenarios (BABOK 9.30)
5. `system-analysis/change-impact-analyzer.md` — Assess Requirements Changes (BABOK 5.4)

---

## AI sẽ làm gì

### Bước 1 — Define Requirements Architecture *(BABOK 6.4)*

Phân rã tính năng thành các flow có cấu trúc:

```
Happy Path    → luồng thành công chính
Alt Paths     → luồng thay thế hợp lệ
Exception Paths → luồng lỗi cần xử lý
Admin/Backend → luồng nghiệp vụ nội bộ
```

### Bước 2 — Impact Analysis *(BABOK Technique 9.21)*

Xác định tất cả thành phần bị ảnh hưởng:

```markdown
### Impact Map

| Affected Component   | Impact Type      | Description                      | Confirm With   |
|---|---|---|---|
| [Module / Service]   | 🔴 Direct        | Thay đổi trực tiếp               | [Team]         |
| [Module / Service]   | 🟡 Indirect      | Bị ảnh hưởng gián tiếp           | [Team]         |
| [External System]    | 🔴 Integration   | Tích hợp mới / thay đổi contract | [Vendor/Dev]   |
| [Module / Service]   | 🟢 Optional      | Có thể defer, không block         | [Team]         |

Impact Summary: [X] Direct · [Y] Indirect · [Z] New Integrations
```

### Bước 3 — Assess Requirements Changes *(BABOK 5.4)*

Phân tích dependency và tracing:

```markdown
### Dependency Analysis

🔴 Hard Dependencies (must resolve before dev starts):
- [Dependency 1 — lý do block]

🟡 Soft Dependencies (ảnh hưởng nhưng không block):
- [Dependency 1 — workaround nếu chưa có]

📋 Data Dependencies (cần clarify):
- [Field / entity nào cần define trước?]

📜 Traceability:
- US-01 → BR-01, BR-02 → [System Component]
- US-02 → [External API] → [Internal Service]
```

### Bước 4 — Risk Analysis & Management *(BABOK 9.26)*

```markdown
### Risk Register

| # | Risk Description           | Category      | Probability | Impact | Risk Level | Mitigation Strategy        |
|---|---|---|---|---|---|---|
| R1 | [Rủi ro 1]               | Technical     | High/Med/Low | H/M/L  | 🔴/🟡/🟢  | [Cách giảm thiểu]          |
| R2 | [Rủi ro 2]               | Business      |              |        |             |                            |
| R3 | [Rủi ro 3]               | External      |              |        |             |                            |

Risk Categories (BABOK): Technical · Business · Project · External
```

### Bước 5 — Define Design Options *(BABOK 6.5)*

Nếu có nhiều hướng giải quyết, AI trình bày trade-off:

```markdown
### Design Options

| Option | Description | Pros | Cons | Recommendation |
|---|---|---|---|---|
| A | [Hướng 1] | | | |
| B | [Hướng 2] | | | ✅ Recommended |
```

### Bước 6 — Open Questions (Elicitation Gaps còn lại)

```markdown
### Open Questions

🔧 Technical — hỏi Dev/Architect:
- [ ] [Câu hỏi kỹ thuật cần xác nhận]

📋 Business — hỏi Stakeholder/PO:
- [ ] [Câu hỏi nghiệp vụ chưa rõ]

🔗 External — hỏi Vendor/Partner:
- [ ] [Câu hỏi liên quan third-party]
```

---

## Output mẫu (tóm tắt)

```
Feature Analysis: Đăng ký tài khoản VKS online
BABOK: RADD (6.4) + RLCM (5.4) + Risk Analysis (9.26)

📊 Impact: 4 components (1 new integration — eKYC)
⚠️ Highest Risk: eKYC timeout [🔴 HIGH] → Mitigation: manual fallback
🔗 Hard Dependency: eKYC API contract must be confirmed
❓ Open Questions: 6 (3 technical, 2 business, 1 external)

✅ Ready to refine after 2 critical questions answered:
   → eKYC vendor approval?
   → Manual review SLA?
```

---

## Tips

> 💡 **BABOK insight:** RADD 6.4 (Requirements Architecture) nhắc nhở rằng requirements không tồn tại độc lập — chúng có quan hệ với nhau và với architecture. Bỏ qua bước này dẫn đến scope creep.

> ⚠️ **Risk Categories theo BABOK 9.26:** Đừng chỉ xét Technical risk — Business risk (stakeholder không approve) và External risk (vendor delay) cũng hay xảy ra trong thực tế.

> 🎯 **Decision Analysis (9.8):** Dùng cho bước Design Options khi có nhiều trade-off phức tạp cần stakeholder quyết định.

---

## Output liên quan

- → [`/impact`](./impact.md) — đào sâu vào một component cụ thể (BABOK 9.21)
- → [`/testcase`](./testcase.md) — sinh test case từ risk và edge case (Solution Evaluation)
- → [`/write-doc`](./write-doc.md) — đưa toàn bộ analysis vào SRS/PRD (Documentation)
- → [`/change-request`](./change-request.md) — nếu đây là phân tích cho CR (RLCM 5.4)
