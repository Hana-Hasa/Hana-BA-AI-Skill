# **BAKit basic:**

.bakit
│
├── commands
│   ├── discover.md
│   ├── analyze-feature.md
│   ├── userstory.md
│   ├── impact.md
│   ├── testcase.md
│   └── write-doc.md        ← viết SRS / PRD
│
├── skills
│   ├── discovery
│   │   ├── problem-analysis.md
│   │   ├── stakeholder-analysis.md
│   │   └── persona-creation.md
│   │
│   ├── requirement
│   │   ├── userstory-writing.md
│   │   ├── acceptance-criteria.md
│   │   └── edgecase-discovery.md
│   │
│   ├── system-analysis
│   │   ├── impact-analysis.md
│   │   ├── dependency-analysis.md
│   │   └── risk-analysis.md
│   │
│   ├── product-thinking
│   │   ├── prioritization.md
│   │   └── metric-definition.md
│   │
│   ├── documentation
│   │   ├── srs-writing.md      ← Software Requirements Specification
│   │   └── prd-writing.md      ← Product Requirements Document
│   │
│   └── Delivery
│       ├── Release planning
│       └── Documentation
│
├── agents
│   ├── product-strategist.md
│   ├── business-analyst.md
│   ├── solution-architect.md
│   ├── ux-designer.md
│   ├── qa-engineer.md
│   └── data-analyst.md
│
├── prompts
│   ├── discovery_prompt.md
│   ├── requirement_prompt.md
│   ├── impact_prompt.md
│   └── testing_prompt.md
│
├── templates
│   ├── prd_template.md
│   ├── userstory_template.md
│   ├── acceptance_template.md
│   ├── testcase_template.md
│   ├── srs_template.md         ← [MỚI]
│   └── prd_template_full.md    ← [MỚI] bản đầy đủ có context
│
├── knowledge
│   ├── product_context.md
│   ├── system_architecture.md
│   └── glossary.md
│
└── bakit.config.md

---

# **BAKit Structure Update theo BABOK:**

> Bổ sung và chỉnh sửa để bao phủ đủ **6 giai đoạn vòng đời BA** theo chuẩn BABOK v3.

```
.bakit
│
├── commands
│   ├── discover.md              ← giữ nguyên (giai đoạn 3)
│   ├── analyze-feature.md       ← giữ nguyên (giai đoạn 4)
│   ├── userstory.md             ← giữ nguyên (giai đoạn 4)
│   ├── impact.md                ← giữ nguyên (giai đoạn 4 & 5)
│   ├── testcase.md              ← giữ nguyên (giai đoạn 6)
│   ├── strategy.md              ← [MỚI] giai đoạn 1: phân tích chiến lược
│   ├── stakeholder.md           ← [MỚI] giai đoạn 2: mapping stakeholder
│   ├── elicitation.md           ← [MỚI] giai đoạn 3: khơi gợi & tổng hợp yêu cầu
│   ├── change-request.md        ← [MỚI] giai đoạn 5: quản lý thay đổi
│   ├── evaluate.md              ← [MỚI] giai đoạn 6: đánh giá giải pháp
│   ├── write-doc.md             ← [MỚI] tạo tài liệu đặc tả (SRS/BRD/PRD/FRD)
│   ├── model-process.md         ← [MỚI] mô hình hóa quy trình (BPMN/workflow)
│   └── release-note.md          ← [MỚI] tạo release note & tài liệu bàn giao
│
├── skills
│   ├── strategy-analysis        ← [MỚI] giai đoạn 1
│   │   ├── current-state-analysis.md    ← Current State Data Miner
│   │   ├── business-case-generator.md   ← Business Case Generator
│   │   ├── swot-canvas-builder.md       ← Output SWOT / Business Model Canvas
│   │   └── competitive-research.md      ← [MỚI] So sánh đối thủ, benchmark, market gap
│   │
│   ├── stakeholder-planning     ← [MỚI] giai đoạn 2
│   │   ├── stakeholder-mapper.md        ← Stakeholder Mapper & RACI
│   │   ├── persona-creation.md          ← chuyển từ discovery sang đây
│   │   └── communication-plan.md        ← Communication Plan Configurator
│   │
│   ├── discovery                ← giữ, tinh chỉnh (giai đoạn 3)
│   │   ├── problem-analysis.md          ← giữ nguyên
│   │   ├── elicitation-prep.md          ← [ĐỔI TÊN] stakeholder-analysis.md
│   │   ├── elicitation-synthesizer.md   ← [MỚI] Tổng hợp biên bản khơi gợi
│   │   └── user-research.md             ← [MỚI] Tổng hợp insight từ interview/survey
│   │
│   ├── requirement              ← giữ, bổ sung (giai đoạn 4)
│   │   ├── userstory-writing.md         ← giữ nguyên
│   │   ├── acceptance-criteria.md       ← giữ nguyên
│   │   ├── edgecase-discovery.md        ← giữ nguyên
│   │   ├── requirements-modeler.md      ← [MỚI] sinh PlantUML / diagram
│   │   └── requirements-verifier.md     ← [MỚI] chấm điểm INVEST checklist
│   │
│   ├── system-analysis          ← giữ, bổ sung (giai đoạn 4 & 5)
│   │   ├── impact-analysis.md           ← giữ nguyên
│   │   ├── dependency-analysis.md       ← giữ nguyên
│   │   ├── risk-analysis.md             ← giữ nguyên
│   │   ├── change-impact-analyzer.md    ← [MỚI] Change Impact Analyzer
│   │   └── technical-research.md        ← [MỚI] Đánh giá lựa chọn kỹ thuật / vendor từ góc nhìn BA
│   │
│   ├── product-thinking         ← giữ nguyên
│   │   ├── prioritization.md
│   │   └── metric-definition.md
│   │
│   ├── solution-evaluation      ← [MỚI] giai đoạn 6
│   │   ├── performance-analyzer.md      ← Performance Data Analyzer
│   │   └── root-cause-analysis.md       ← Root Cause Analysis
│   │
│   ├── documentation            ← [MỚI] BA Doing – Viết tài liệu đặc tả
│   │   ├── srs-writing.md               ← Software Requirements Specification
│   │   ├── brd-writing.md               ← Business Requirements Document
│   │   ├── frd-writing.md               ← Functional Requirements Document
│   │   ├── prd-writing.md               ← Product Requirements Document
│   │   ├── api-spec-writing.md          ← API Specification (BA perspective)
│   │   └── data-dictionary.md           ← Định nghĩa field, data type, business rule
│   │
│   ├── process-modeling         ← [MỚI] Mô hình hóa quy trình
│   │   ├── bpmn-modeling.md             ← BPMN 2.0 (As-Is / To-Be)
│   │   ├── workflow-mapping.md          ← Swimlane, flowchart, process flow
│   │   ├── as-is-to-be.md               ← Gap analysis quy trình
│   │   └── sequence-flow.md             ← Sequence diagram từ góc nhìn BA
│   │
│   └── delivery                 ← [MỞ RỘNG] tài liệu bàn giao & vận hành
│       ├── release-planning.md          ← sửa từ "Release planning"
│       ├── documentation.md             ← sửa từ "Documentation"
│       ├── release-note-writing.md      ← [MỚI] Release Note gửi KH / internal
│       ├── uat-plan-writing.md          ← [MỚI] UAT Plan, test scenario business
│       ├── mom-writing.md               ← [MỚI] Minutes of Meeting chuẩn
│       ├── traceability-matrix.md       ← [MỚI] Ma trận truy xuất yêu cầu (RTM)
│       └── handover-doc.md              ← [MỚI] Tài liệu bàn giao dev/QA/ops
│
├── agents
│   ├── product-strategist.md    ← giữ nguyên
│   ├── business-analyst.md      ← giữ nguyên
│   ├── solution-architect.md    ← giữ nguyên
│   ├── ux-designer.md           ← giữ nguyên
│   ├── qa-engineer.md           ← giữ nguyên
│   ├── data-analyst.md          ← giữ nguyên
│   └── change-analyst.md        ← [MỚI] xử lý change request & traceability
│
├── prompts
│   ├── discovery_prompt.md      ← giữ nguyên
│   ├── requirement_prompt.md    ← giữ nguyên
│   ├── impact_prompt.md         ← giữ nguyên
│   ├── testing_prompt.md        ← giữ nguyên
│   ├── strategy_prompt.md       ← [MỚI]
│   ├── stakeholder_prompt.md    ← [MỚI]
│   ├── elicitation_prompt.md    ← [MỚI]
│   ├── evaluation_prompt.md     ← [MỚI]
│   ├── documentation_prompt.md  ← [MỚI] viết SRS/BRD/PRD/FRD
│   ├── process_prompt.md        ← [MỚI] mô hình hóa BPMN/workflow
│   └── delivery_prompt.md       ← [MỚI] release note, UAT, handover
│
├── templates
│   ├── prd_template.md               ← giữ nguyên
│   ├── userstory_template.md         ← giữ nguyên
│   ├── acceptance_template.md        ← giữ nguyên
│   ├── testcase_template.md          ← giữ nguyên
│   ├── business_case_template.md     ← [MỚI]
│   ├── stakeholder_map_template.md   ← [MỚI]
│   ├── impact_report_template.md     ← [MỚI]
│   ├── release_note_template.md      ← [MỚI]
│   ├── srs_template.md               ← [MỚI]
│   ├── brd_template.md               ← [MỚI]
│   ├── frd_template.md               ← [MỚI]
│   ├── api_spec_template.md          ← [MỚI]
│   ├── bpmn_annotation_template.md   ← [MỚI]
│   ├── uat_plan_template.md          ← [MỚI]
│   ├── mom_template.md               ← [MỚI]
│   ├── traceability_matrix_template.md  ← [MỚI]
│   └── handover_template.md          ← [MỚI]
│
├── knowledge
│   ├── product_context.md       ← giữ nguyên
│   ├── system_architecture.md   ← giữ nguyên
│   ├── glossary.md              ← giữ nguyên
│   └── business_rules.md        ← [MỚI] Business Rules từ elicitation phase
│
└── bakit.config.md
```

## Mapping Skills theo 6 giai đoạn BABOK + 2 nhóm BA Doing

| Giai đoạn / Nhóm               | Skills Folder                          | Commands                                                |
| --------------------------------- | -------------------------------------- | ------------------------------------------------------- |
| 1. Strategy Analysis              | `strategy-analysis/`                 | `strategy.md`                                         |
| 2. BA Planning & Stakeholder      | `stakeholder-planning/`              | `stakeholder.md`                                      |
| 3. Elicitation & Collaboration    | `discovery/`                         | `discover.md`, `elicitation.md`                     |
| 4. Requirements Analysis & Design | `requirement/`, `system-analysis/` | `analyze-feature.md`, `userstory.md`, `impact.md` |
| 5. Requirements Life Cycle Mgmt   | `system-analysis/` (change)          | `change-request.md`                                   |
| 6. Solution Evaluation            | `solution-evaluation/`               | `evaluate.md`, `testcase.md`                        |
| 📄 BA Doing – Viết tài liệu   | `documentation/`                     | `write-doc.md`                                        |
| 🔄 BA Doing – Mô hình hóa     | `process-modeling/`                  | `model-process.md`                                    |
| 📦 BA Doing – Bàn giao          | `delivery/`                          | `release-note.md`                                     |

## Tóm tắt thay đổi

| Loại          | Action                  | Số lượng |
| -------------- | ----------------------- | ----------- |
| Commands       | ➕ Thêm mới           | 8           |
| Skills folders | ➕ Thêm mới           | 5           |
| Skill files    | ➕ Thêm mới           | 21          |
| Skill files    | ✏️ Đổi tên / Sửa  | 3           |
| Skill files    | 🔬 Research skills mới | 3           |
| Agents         | ➕ Thêm mới           | 1           |
| Templates      | ➕ Thêm mới           | 13          |
| Prompts        | ➕ Thêm mới           | 7           |
| Knowledge      | ➕ Thêm mới           | 1           |

---

giải thích **mối quan hệ các phần của BAKit** theo 3 cách để bạn dễ hình dung:

1. **Luồng chạy thực tế của BAKit**
2. **Vai trò từng thành phần**
3. **Ẩn dụ dễ hiểu (BAKit như một công ty / một nhà bếp)**

---

# 1. Luồng chạy tổng thể của BAKit

Khi BA dùng BAKit, luồng thực tế sẽ như sau:

<pre class="overflow-visible! px-0!" data-start="308" data-end="420"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class=""><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>User (BA)</span><br/><span>   ↓</span><br/><span>Command</span><br/><span>   ↓</span><br/><span>Agent</span><br/><span>   ↓</span><br/><span>Skill</span><br/><span>   ↓</span><br/><span>Prompt</span><br/><span>   ↓</span><br/><span>Knowledge</span><br/><span>   ↓</span><br/><span>Template</span><br/><span>   ↓</span><br/><span>AI Output</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

**Ví dụ BA nhập:**

`/analyze-feature`

Feature: Login with Google

**BAKit sẽ xử lý như sau:**

1️⃣ **Command** nhận yêu cầu

→ `/analyze-feature`

2️⃣ **Agent** được chọn

→ Business Analyst

→ Architect

→ QA

3️⃣ **Skill** được gọi

→ product thinking

→ requirement writing

→ impact analysis

→ edge case discovery

4️⃣ **Prompt Template** được build

5️⃣ **Knowledge Base** được thêm context hệ thống

6️⃣ **Template** format output

7️⃣ **AI trả kết quả**

---

# 2. Vai trò của từng thành phần

| Thành phần | Vai trò                   |
| ------------ | -------------------------- |
| Command      | điểm bắt đầu workflow |
| Agent        | góc nhìn chuyên môn    |
| Skill        | logic phân tích          |
| Prompt       | cách giao tiếp với AI   |
| Knowledge    | context hệ thống         |
| Template     | format output              |

---

## 1️⃣ Command – Nút bấm hành động

Command giống như  **API endpoint của BAKit** .

Ví dụ:

<pre class="overflow-visible! px-0!" data-start="1243" data-end="1284"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>/discover</span><br/><span>/userstory</span><br/><span>/impact</span><br/><span>/prd</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

Command chỉ làm nhiệm vụ:

> **Trigger workflow**

---

## 2️⃣ Agent – Góc nhìn chuyên môn

Agent đại diện cho  **vai trò trong team product** .

Ví dụ:

* Product Strategist
* Business Analyst
* Solution Architect
* QA Engineer
* UX Designer
* Data Analyst

Agent giúp AI  **suy nghĩ như người thật trong team** .

---

## 3️⃣ Skill – Năng lực phân tích

Skill là  **trí tuệ thật sự của BAKit** .

Ví dụ skill của BA:

* Requirement elicitation
* System thinking
* Edge case discovery
* Risk analysis
* Product prioritization

Skill chứa:

* checklist
* logic
* reasoning framework

---

## 4️⃣ Prompt – Ngôn ngữ nói chuyện với AI

Prompt chỉ là  **cách diễn đạt yêu cầu cho AI** .

Ví dụ:

<pre class="overflow-visible! px-0!" data-start="1982" data-end="2102"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>You are a Senior Business Analyst.</span><br/><span>Analyze the following feature.</span><br/><span>Generate user stories and acceptance criteria.</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

Prompt chỉ là  **wrapper cho skill** .

---

## 5️⃣ Knowledge – Context hệ thống

Knowledge giúp AI hiểu:

* product
* system architecture
* business domain
* glossary

Ví dụ:

<pre class="overflow-visible! px-0!" data-start="2279" data-end="2358"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>System uses OAuth for authentication.</span><br/><span>User data stored in User Service.</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

Nếu không có knowledge → AI sẽ  **viết requirement sai context** .

---

## 6️⃣ Template – Format output

Template giúp output  **chuẩn hóa tài liệu BA** .

Ví dụ template:

<pre class="overflow-visible! px-0!" data-start="2530" data-end="2593"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>User Story</span><br/><span>Acceptance Criteria</span><br/><span>Edge Cases</span><br/><span>System Impact</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

---

# 3. Ẩn dụ 1 – BAKit như một công ty

Hãy tưởng tượng BAKit là  **một công ty product mini chạy bằng AI** .

| Thành phần | Trong công ty                    |
| ------------ | --------------------------------- |
| Command      | CEO ra yêu cầu                  |
| Agent        | nhân viên                       |
| Skill        | kỹ năng của nhân viên        |
| Prompt       | cách nhân viên viết báo cáo |
| Knowledge    | tài liệu nội bộ               |
| Template     | form báo cáo                    |

Ví dụ:

CEO nói:

> “Phân tích feature login bằng Google”

Luồng sẽ là:

<pre class="overflow-visible! px-0!" data-start="2996" data-end="3017"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>CEO → Command</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

↓

<pre class="overflow-visible! px-0!" data-start="3022" data-end="3058"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>Team được giao việc → Agents</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

↓

<pre class="overflow-visible! px-0!" data-start="3063" data-end="3102"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>Nhân viên dùng kỹ năng → Skills</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

↓

<pre class="overflow-visible! px-0!" data-start="3107" data-end="3136"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>Viết báo cáo → Prompt</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

↓

<pre class="overflow-visible! px-0!" data-start="3141" data-end="3186"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>Dựa trên tài liệu công ty → Knowledge</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

↓

<pre class="overflow-visible! px-0!" data-start="3191" data-end="3228"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>Xuất báo cáo chuẩn → Template</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

---

# 4. Ẩn dụ 2 – BAKit như một nhà bếp

Một ẩn dụ khác rất dễ hiểu.

| BAKit     | Nhà bếp       |
| --------- | --------------- |
| Command   | order món      |
| Agent     | đầu bếp      |
| Skill     | kỹ thuật nấu |
| Prompt    | công thức     |
| Knowledge | nguyên liệu   |
| Template  | plating         |

Ví dụ:

Khách order:

<pre class="overflow-visible! px-0!" data-start="3486" data-end="3510"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute end-1.5 top-1 z-2 md:end-2 md:top-1"></div><div class="pt-3"><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>/analyze-feature</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

↓

Đầu bếp (Agent) nhận order

↓

Dùng kỹ thuật nấu (Skill)

↓

Theo công thức (Prompt)

↓

Dùng nguyên liệu (Knowledge)

↓

Bày món ra đĩa (Template)

↓

Khách nhận món ăn (AI Output)

---

# 5. Mối quan hệ giữa Skill – Command – Prompt

Đây là điểm nhiều người nhầm.

<pre class="overflow-visible! px-0!" data-start="3782" data-end="3843"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class=""><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>Command = Trigger</span><br/><span>Skill = Brain</span><br/><span>Prompt = Language</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

Hoặc:

<pre class="overflow-visible! px-0!" data-start="3852" data-end="3930"><div class="relative w-full mt-4 mb-1"><div class=""><div class="relative"><div class="h-full min-h-0 min-w-0"><div class="h-full min-h-0 min-w-0"><div class="border border-token-border-light border-radius-3xl corner-superellipse/1.1 rounded-3xl"><div class="h-full w-full border-radius-3xl bg-token-bg-elevated-secondary corner-superellipse/1.1 overflow-clip rounded-3xl lxnfua_clipPathFallback"><div class="pointer-events-none absolute inset-x-4 top-12 bottom-4"><div class="pointer-events-none sticky z-40 shrink-0 z-1!"><div class="sticky bg-token-border-light"></div></div></div><div class=""><div class="relative z-0 flex max-w-full"><div id="code-block-viewer" dir="ltr" class="q9tKkq_viewer cm-editor z-10 light:cm-light dark:cm-light flex h-full w-full flex-col items-stretch ͼk ͼy"><div class="cm-scroller"><div class="cm-content q9tKkq_readonly"><span>Command → gọi Skill</span><br/><span>Skill → dùng Prompt</span><br/><span>Prompt → nói chuyện với AI</span></div></div></div></div></div></div></div></div></div><div class=""><div class=""></div></div></div></div></div></pre>

# BAKit Architecture

![1773024580764](image/BAKit-Structure/1773024580764.png)

# BAKit Cognitive Loop

![1773023745010](image/BAKit-Structure/1773023745010.png)
