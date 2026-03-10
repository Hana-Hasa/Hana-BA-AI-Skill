# BAKit Configuration

> File cấu hình trung tâm của BAKit — mô tả cách các thành phần kết nối với nhau.

---

## Thông tin chung

| Field        | Value                          |
|---|---|
| Tên kit      | BAKit – BA AI Skill Kit        |
| Phiên bản    | 1.0.0                          |
| Chuẩn tham chiếu | BABOK v3                  |
| Ngôn ngữ mặc định | Tiếng Việt             |
| Audience     | Business Analyst – VNG Hana    |

---

## Cấu trúc thư mục

```
.bakit/
├── commands/       ← điểm bắt đầu workflow (trigger)
├── skills/         ← logic phân tích (brain)
│   ├── strategy-analysis/
│   ├── stakeholder-planning/
│   ├── discovery/
│   ├── requirement/
│   ├── system-analysis/
│   ├── product-thinking/
│   ├── solution-evaluation/
│   ├── documentation/
│   ├── process-modeling/
│   └── delivery/
├── agents/         ← góc nhìn chuyên môn
├── prompts/        ← cách giao tiếp với AI
├── templates/      ← format output chuẩn
├── knowledge/      ← context hệ thống / domain
└── bakit.config.md ← file này
```

---

## Luồng chạy

```
User (BA)
   ↓ gõ /command
Command  →  Agent  →  Skill  →  Prompt  →  Knowledge  →  Template
                                                              ↓
                                                         AI Output
```

---

## Mapping BABOK → BAKit

| BABOK Giai đoạn                 | Skills Folder              | Commands chính              |
|---|---|---|
| 1. Strategy Analysis             | `strategy-analysis/`       | `/strategy`                 |
| 2. BA Planning & Stakeholder     | `stakeholder-planning/`    | `/stakeholder`              |
| 3. Elicitation & Collaboration   | `discovery/`               | `/discover`, `/elicitation` |
| 4. Requirements Analysis & Design | `requirement/`, `system-analysis/` | `/analyze-feature`, `/userstory`, `/impact` |
| 5. Requirements Life Cycle Mgmt  | `system-analysis/`         | `/change-request`           |
| 6. Solution Evaluation           | `solution-evaluation/`     | `/evaluate`, `/testcase`    |
| 📄 BA Doing – Tài liệu đặc tả  | `documentation/`           | `/write-doc`                |
| 🔄 BA Doing – Mô hình hóa      | `process-modeling/`        | `/model-process`            |
| 📦 BA Doing – Bàn giao          | `delivery/`                | `/release-note`             |

---

## Ghi chú

- Mỗi file placeholder sẽ được điền nội dung theo từng sprint làm việc.
- Ưu tiên build theo thứ tự: **requirement → documentation → delivery** (thường dùng nhất).
- Khi thêm skill mới, cập nhật mapping table ở trên.
