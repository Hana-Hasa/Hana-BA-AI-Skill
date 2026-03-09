# **BAKit structure chi tiết:**

.bakit
│
├── commands
│   ├── discover.md
│   ├── analyze-feature.md
│   ├── userstory.md
│   ├── impact.md
│   └── testcase.md
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
│   └── testcase_template.md
│
├── knowledge
│   ├── product_context.md
│   ├── system_architecture.md
│   └── glossary.md
│
└── bakit.config.md

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
