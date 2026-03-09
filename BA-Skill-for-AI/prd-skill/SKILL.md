---
name: PRD Writer
description: Viết Product Requirements Document (PRD) chuẩn cho BA team VNG Hana. Dùng khi user nói "viết PRD", "tạo PRD", "draft PRD", "write PRD", "tạo tài liệu yêu cầu sản phẩm", hoặc muốn chuyển từ meeting notes/idea thành PRD.
---

# PRD Writer

Skill này giúp AI tạo ra một PRD (Product Requirements Document) hoàn chỉnh theo chuẩn VNG Hana — bao gồm overview, user stories (Gherkin), functional requirements, UI/UX specs, validation rules, technical notes, success metrics và risk analysis.

---

## When to Use This Skill

- User yêu cầu viết PRD cho một feature mới
- User muốn chuyển meeting notes, idea, hoặc brief thành PRD
- User cần chuẩn hóa một tài liệu yêu cầu sản phẩm đang ở dạng thô
- User nói "viết PRD", "tạo PRD", "draft PRD", "tạo spec"

---

## Inputs

User cung cấp một hoặc nhiều trong số sau:

- Mô tả feature/product cần viết PRD
- Meeting notes hoặc brief từ stakeholder
- User stories ở dạng thô
- Wireframe/mockup description
- Tài liệu hiện trạng (current state)
- Business context hoặc pain points

> ⚠️ Nếu user chưa cung cấp đủ thông tin, hỏi các câu sau trước khi viết:
> 1. Feature này giải quyết vấn đề gì? (Pain points)
> 2. Ai là người dùng chính? (Target user)
> 3. Scope bao gồm và không bao gồm những gì?
> 4. Có UI thay đổi không? Mô tả current state vs proposed state
> 5. Có dependencies với hệ thống nào khác không?

---

## Output Format

Output là một file Markdown (.md) theo cấu trúc PRD chuẩn VNG Hana gồm 8 sections.

**Ngôn ngữ:** Tiếng Việt cho nội dung mô tả. Tiếng Anh cho technical terms, Gherkin scenarios, field names, và component types.

**Tone:** Chuyên nghiệp, rõ ràng, súc tích. Không dùng ngôn ngữ mơ hồ.

---

## Step-by-Step Instructions

### Step 1 — Tạo Document Information và Overview (Sections 1)

Phần header giúp stakeholder nhanh chóng nắm được context mà không cần đọc toàn bộ PRD.

1. Tạo bảng Document Information:

```markdown
# PRD: [Tên Feature]

## Document Information

| Field        | Value              |
| ------------ | ------------------ |
| Product      | [Tên sản phẩm]    |
| Feature      | [Tên feature]     |
| Version      | 1.0                |
| Created Date | [YYYY-MM-DD]       |
| Status       | Draft              |
| Author       | [Tên tác giả]     |
```

2. Viết section Overview gồm 3 phần:

**1.1 Background:**
- Mô tả hiện trạng (current state) — hệ thống đang hoạt động như thế nào
- Liệt kê pain points dưới dạng bullet
- So sánh rõ ràng current state vs proposed state (dùng bold + dash)
- Thêm blockquote `> **Lưu ý:**` cho các giới hạn quan trọng

**1.2 Objective:**
- Liệt kê 3-5 mục tiêu cụ thể, đo lường được, bắt đầu bằng động từ

**1.3 Scope:**
- Bảng scope gồm: Function | Description | Portal (UI changes) | User Story ID
- Liệt kê rõ **Ngoài phạm vi (Out of Scope)** bằng bullet

### Step 2 — Viết User Stories ở định dạng Gherkin (Section 2)

User Stories theo chuẩn Gherkin giúp QC team dễ dàng chuyển thành test cases mà không cần diễn giải thêm.

1. Mỗi User Story gồm:
   - ID: `US-XX`
   - Tiêu đề mô tả hành động
   - Format: As a / I want / So that
   - Acceptance Criteria viết bằng Gherkin trong code block

2. Gherkin format chuẩn:

```gherkin
Feature: [Tên feature]

  Background:
    Given [điều kiện tiên quyết chung]

  Scenario: [Tên kịch bản]
    Given [ngữ cảnh cụ thể]
    When [hành động của user]
    Then [kết quả mong đợi]
    And [kết quả bổ sung]

  Scenario Outline: [Tên kịch bản có nhiều dữ liệu]
    Given [ngữ cảnh]
    When [hành động với <biến>]
    Then [kết quả với <biến>]

    Examples:
      | biến_1 | biến_2 | result  |
      | val_1  | val_2  | Valid   |
      | val_3  | val_4  | Invalid |
```

3. Quy tắc viết Gherkin:
   - Background chứa điều kiện dùng chung cho tất cả Scenario trong Feature
   - Mỗi Scenario mô tả 1 flow cụ thể (happy path, error, edge case)
   - Dùng `Scenario Outline` + `Examples` khi có nhiều tổ hợp dữ liệu cùng logic
   - Validation scenarios: viết riêng cho từng rule (chưa đủ data, data sai format, data hợp lệ)
   - User Stories không thay đổi UI ghi chú: `> **Note:** US này không thay đổi UI portal hiện tại, chỉ mô tả behavior cần QC verify.`

### Step 3 — Viết Functional Requirements (Section 3)

Phần này mô tả chi tiết thay đổi trên từng trang/component — là tài liệu chính để dev và designer triển khai.

Mỗi page/section viết theo pattern:

```markdown
### 3.X [Tên trang/section]

#### 3.X.1 Current State
- [Mô tả trạng thái hiện tại của UI/logic]

#### 3.X.2 Proposed Changes
- Dùng bảng để mô tả thay đổi chi tiết: Field | Type | Behavior | Required
- Mô tả Behavior cho từng control plane availability hoặc condition
- Dùng ASCII diagram hoặc tree structure cho layout phức tạp

#### 3.X.3 Business Rules
- Bảng: Rule | Description
```

Quy tắc:
- Luôn viết Current State trước Proposed Changes để người đọc thấy sự khác biệt
- Dùng bảng cho field definitions — không viết paragraph dài
- Business Rules liệt kê tất cả ràng buộc logic, bao gồm cả immutable rules (không đổi sau khi tạo)
- Dùng `> **⚠️ Prerequisite:**` cho điều kiện tiên quyết quan trọng
- Format hiển thị (display value) phải cụ thể đến mức dev có thể implement mà không cần hỏi lại

### Step 4 — Viết UI/UX Specifications (Section 4)

Section này là bảng tham chiếu nhanh cho designer và frontend dev — tách biệt khỏi logic để dễ review.

1. Liệt kê components theo từng page:

```markdown
### 4.X [Tên trang]

| Component       | Type                    | Mô tả                        |
| --------------- | ----------------------- | ----------------------------- |
| [Tên component] | [Badge/Dropdown/Chip..] | [Mô tả ngắn gọn]            |
```

2. Kết thúc bằng Component Types Summary:

```markdown
### 4.X Component Types Summary

| Component Type           | Sử dụng cho                    |
| ------------------------ | ------------------------------ |
| Badge (text)             | [Liệt kê nơi sử dụng]        |
| Dropdown (single-select) | [Liệt kê nơi sử dụng]        |
```

### Step 5 — Viết Validation Rules (Section 5)

Validation rules đảm bảo dev implement đúng logic kiểm tra — tránh bug và bad UX.

Chia thành 3 phần:

1. **Field Validation** — bảng: Field | Rule | Error Message
2. **Sub-section Validation** (nếu có form con) — bảng tương tự
3. **Business Rules** — bảng: Rule | Description

Quy tắc:
- Error message viết bằng tiếng Việt, thân thiện, chỉ rõ user cần làm gì
- Mỗi rule 1 dòng trong bảng, không gộp nhiều rule chung

### Step 6 — Viết Technical Notes (Section 6)

Phần này giúp dev team và QC hiểu architecture và dependencies — tránh assumption sai.

Bao gồm:

1. **Architecture** — mô tả kiến trúc kèm ASCII diagram nếu phù hợp
2. **Dependencies** — bảng: Component | Role | Status (Done/In Progress/QC)
3. **QC Test Criteria** — bảng: User Story | Description | Expected Behavior, chia theo Category
4. **Backend Requirements** (nếu có) — chia MUST HAVE và SHOULD HAVE

Quy tắc:
- ASCII diagram dùng box drawing characters (`┌ ─ ┐ │ └ ┘ ├ ┤ ┬ ┴ ┼`)
- QC criteria là guideline, ghi rõ `> **Note:** QC sẽ tự define chi tiết test cases`
- Backend requirements ngoài scope UI ghi rõ `> **Note:** không thuộc scope UI của PRD này`

### Step 7 — Viết Success Metrics và Risks (Sections 7-8)

Metrics và risks giúp PM và stakeholder đánh giá ROI và chuẩn bị contingency plan.

**Success Metrics** — bảng:

| Metric          | Target  | Measurement          |
| --------------- | ------- | -------------------- |
| [Tên metric]    | [Mục tiêu cụ thể] | [Cách đo lường] |

**Risks & Mitigations** — chia theo loại (UI/UX Risks, Infrastructure Risks...):

| Risk            | Impact  | Mitigation           |
| --------------- | ------- | -------------------- |
| [Mô tả risk]   | [Tác động] | [Cách giảm thiểu] |

---

## Examples

**Example 1 — Input:**

> "Viết PRD cho tính năng Multi-AZ support cho Kubernetes Control Plane. Hiện tại chỉ hỗ trợ Single-AZ, cần cho phép user chọn Multi-AZ khi tạo cluster để đảm bảo HA."

**Output:** PRD hoàn chỉnh 8 sections bao gồm:
- Document Info + Overview với pain points và current vs proposed comparison
- 6 User Stories (US-01 đến US-06) với Gherkin acceptance criteria
- Functional Requirements cho 4 pages: List, Detail, Create, Node Group Setting
- UI/UX specs với component type mapping
- Validation rules cho Create flow
- Technical notes với ASCII architecture diagram
- Success Metrics (5 metrics) và Risks (UI/UX + Infrastructure)

---

## Tips & Tricks

> 💡 **Viết Current State trước:** Luôn mô tả hiện trạng trước khi nói thay đổi — giúp reviewer thấy rõ delta.

> 💡 **Dùng Scenario Outline cho validation:** Khi có nhiều tổ hợp valid/invalid, dùng `Scenario Outline` + `Examples` table thay vì viết nhiều Scenario riêng lẻ — gọn hơn và dễ maintain.

> 💡 **Business Rules tập trung 1 chỗ:** Dù đã mention trong Functional Requirements, vẫn nên tổng hợp lại ở Section 5.3 để dev có 1 nơi tra cứu duy nhất.

> 💡 **Error message = hành động:** Thay vì "Lỗi subnet", viết "Vui lòng chọn ít nhất 2 subnet" — user biết ngay cần làm gì.

> 💡 **Out of Scope quan trọng như In Scope:** Liệt kê rõ những gì KHÔNG làm để tránh scope creep.

---

## Limitations

- ❌ Skill này không tạo wireframe hoặc mockup — chỉ mô tả UI bằng text và bảng
- ❌ Không viết API contract hoặc database schema chi tiết — chỉ ghi technical notes ở mức overview
- ❌ Không thay thế được buổi review PRD với stakeholder — PRD vẫn cần được validate bởi con người
- ❌ Gherkin scenarios là guideline cho QC, không phải automated test scripts

---

## Related Skills

- **BA How-To Writing Style Guide** — dùng khi cần viết hướng dẫn how-to thay vì tài liệu yêu cầu
- **Requirements Verifier & Grader** — dùng sau khi viết PRD để kiểm tra chất lượng user stories theo tiêu chuẩn INVEST
- **Change Impact Analyzer** — dùng khi có change request cần đánh giá tác động lên PRD hiện tại

---

## PRD Quality Checklist

```
PRE-PUBLISH CHECK
□ Document Information đầy đủ (Product, Feature, Version, Date, Status, Author)
□ Background có pain points và current vs proposed comparison
□ Objective có 3-5 mục tiêu đo lường được
□ Scope table có Function, Description, Portal, User Story ID
□ Out of Scope được liệt kê rõ ràng
□ Mỗi User Story có format As a/I want/So that + Gherkin AC
□ Gherkin có Background, happy path, error scenarios, edge cases
□ Functional Requirements có Current State + Proposed Changes + Business Rules
□ UI/UX Specs liệt kê đủ component types cho từng page
□ Validation Rules có Error Message bằng tiếng Việt
□ Business Rules không bị trùng lặp, tập trung 1 section
□ Technical Notes có architecture + dependencies + QC criteria
□ Success Metrics có Target và Measurement cụ thể
□ Risks có Impact và Mitigation cho mỗi risk
□ Không dùng ngôn ngữ mơ hồ ("có thể", "nên", "tùy trường hợp")
```
