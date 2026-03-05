---
name: BA How-To Writing Style Guide
description: Write technical how-to guides for non-tech BAs following the VNG Hana BA standard — step-by-step structure, friendly tone, emoji, code blocks, comparison tables, real-world case studies, and checklists.
---

# Purpose of This Skill

This skill helps AI produce **technical how-to guides for non-tech BAs** in the exact style used by the VNG Hana "Becoming an AI-Augmented BA" series.

When asked to write a guide (how-to, tutorial, setup guide, onboarding doc, etc.), AI must follow the structure, tone, and rules defined below.

---

# SECTION 1 — Required Structure of a How-To Guide

Every guide **must include** all of the following components, in order:

## 1.1 — H1 Title

```
# [relevant emoji] [Short topic name] — [Tagline explaining what the guide is for]
```

**Examples:**
```
# 🐙 Your First Step as an AI-Augmented BA — Getting Started with GitHub
# 🎨 BA x AI x Figma — The Ultimate Guide to MCP Figma with Cursor
```

The title must be: short, have a relevant emoji, and the part after `—` must explain what the guide is for.

---

## 1.2 — Metadata Block (Header)

```markdown
> ✍️ **Author:** [author name or team]
> 🗓️ **Date:** [Month YYYY]
> 🎯 **Audience:** [specific audience description]
> 📚 **Series:** [series name — Article N/N] ← only include if part of a series
```

---

## 1.3 — "Why Should You Care?" Section (Opening)

- Start with a **real pain point** the reader faces — never start with a technical definition
- Describe "how it used to be done" vs "what you can do now"
- End with one hook sentence to encourage reading on
- Tone: empathetic, warm, can use emotional emojis

**Template structure:**
```
[Describe how the old way was exhausting]

But now things are different! With [tool/method], you can:
- [benefit 1]
- [benefit 2]
- [benefit 3]

[Hook sentence → keep reading]
```

---

## 1.4 — Overview Roadmap

Use a code block to summarize the article structure or journeys:

```
1. [Section name 1]
2. [Section name 2]
3. [Section name 3]
...
```

Or a two-journey comparison format:

```
Journey 1: [Name]  →  [Tool]  (short purpose)
Journey 2: [Name]  →  [Tool]  (short purpose)
```

---

## 1.5 — Main SECTIONS / JOURNEYS

Each major section uses `# H1 ALL CAPS` with an emoji and a clear name:

```markdown
# 🛤️ JOURNEY 1 — [Journey name]
# 🧠 SECTION 1 — [Section name]
```

Inside each section: break down into numbered **Steps** starting from 1.

---

## 1.6 — Steps (Hands-On Actions)

```markdown
## Step N — [Short step name, starting with a verb]
```

Each step includes:
1. **Short description** (1-2 sentences) of why this step is needed
2. **Numbered or bulleted action list**
3. **Code block** if there are commands/configs to copy
4. **Expected result** — clearly show what ✅ success looks like
5. **Image placeholder** (if a visual is needed)

**Expected result code block template:**
```
✅ Success: [description of the successful state]
❌ Error: [description of a common error and how to fix it]
```

---

## 1.7 — Summary Table at the End of Each Journey

```markdown
## ✅ [Journey name] — Summary

| Step | Action |
|------|--------|
| 1    | [action] |
| 2    | [action] |
```

Follow with a **"What you can do"** and **"What you cannot do"** list using ✅/❌.

---

## 1.8 — Tips & Tricks Section

```markdown
# 💡 Tips & Tricks for BAs

### [Number]. [Short tip name]
[Content]
```

---

## 1.9 — Real-World Practice (Case Study) Section

```markdown
# 🚀 Real-World Practice — Case Studies

## Case [N]: [Situation name]

> "[Actual prompt/request the user typed]"

**What AI did:**
- [action 1]
- [action 2]

⏱️ **Time saved:** [description of time/effort saved]
```

---

## 1.10 — Resources Table

```markdown
# 📚 Additional Resources

| Link | Description |
|------|-------------|
| [name](url) | [short description] |
```

---

## 1.11 — Master Checklist (Bookmark-able)

Always end with a checklist inside a code block — readers can bookmark it:

```
JOURNEY NAME
□ [step 1]
□ [step 2]
□ [step 3]
```

---

## 1.12 — Footer

```markdown
> 💬 **Feedback / questions?**
> Drop a message in Slack `#[channel name]` or open an Issue in this repo!
> [Fun closing line relevant to the topic] ✌️
```

---

---

# SECTION 2 — Writing Style Rules

## 2.1 — Tone of Voice

| Do | Don't |
|----|-------|
| Friendly like a colleague chatting | Formal like a corporate document |
| "you", "we", "our team" | "users", "readers", "one should" |
| "That used to be such a pain 😮‍💨" | "This presents a considerable challenge" |
| Gently acknowledge difficulties | Pretend everything is simple |
| Ask rhetorical questions ("Sounds powerful, right?") | One-way monologue |

---

## 2.2 — Explaining Technical Concepts

**Always use a familiar analogy before the technical explanation:**

```
❌ "Git is a distributed version control system"

✅ "Git is like Google Docs with Track Changes — but far more powerful,
   and it runs directly on your machine"
```

**Always answer "Why?" before "How?":**

```
❌ [Jump straight to Step 1]

✅ [1-2 sentences explaining why this step is necessary]
   → [then the specific actions]
```

---

## 2.3 — Emoji

- Use emoji **intentionally**, not as decoration spam
- Each major section/part: 1 characteristic emoji at the start of the heading
- In body text: use to emphasize or create rhythm
- Checklists: use ✅ ❌ □ consistently
- Emotions: 😅 😮‍💨 🎉 ✌️ used naturally, not forced

**Standard emoji set by content type:**

| Content Type | Emoji |
|---|---|
| Journey / path | 🛤️ 🚀 |
| Theory / concepts | 🧠 📚 |
| Hands-on / setup | 🛠️ ⚙️ |
| Tips / tricks | 💡 |
| Warnings | ⚠️ |
| Comparison / summary | 🎯 📊 |
| Resources | 📚 🔗 |
| Checklist | 🎁 ✅ |
| Case study | 🚀 ⏱️ |
| Image placeholder | 🖼️ |

---

## 2.4 — Code Blocks

Use code blocks for:
- Terminal/shell commands
- Config files (JSON, YAML, etc.)
- ASCII flow diagrams
- Before/after examples (❌ bad vs ✅ good)
- Bookmark checklists
- Expected results (✅/❌)

**Always specify the language** when syntax highlighting applies: ` ```json `, ` ```bash `, ` ```powershell `

**Use plain code blocks** (no language tag) for flow diagrams, checklists, and plain text results.

---

## 2.5 — Blockquotes

| Symbol | When to use |
|--------|-------------|
| `> 💡` | Bonus tips, nice-to-know information |
| `> ⚠️` | Warnings, prerequisites, gotchas |
| `> 🖼️` | Placeholder for screenshots to be added later |
| `> 💬` | Inline FAQ, common questions |
| `> 🎯` | Rule of thumb, decision-making principle |

---

## 2.6 — Tables

Use tables when comparing 2+ things. Always include clear column headers.

Comparison columns use: ✅ (yes/good), ❌ (no/bad), ⚠️ (partial/limited).

**Two-option comparison table template:**

```markdown
| | **Option A** | **Option B** |
|---|---|---|
| **Feature X** | ✅ Supported | ❌ Not available |
| **Feature Y** | ⚠️ Limited | ✅ Full support |
```

---

---

# SECTION 3 — Special Rules for Non-Tech BA Audience

## 3.1 — Assumed Reader Profile

Always write for someone who:
- **Does not know how to code**, is not familiar with the command line
- **Knows BA work**: PRDs, user stories, wireframes, meeting notes, Jira
- **Uses**: Windows (primarily), Mac (some)
- **Goal**: Use AI to work faster — not to learn programming

---

## 3.2 — When Mentioning Terminal Commands

- Always provide **both Windows and Mac** versions when they differ
- Explain **what the command does** before showing it
- After the command, always include **how to verify success**

**Template:**
```markdown
Verify successful installation:
```bash
bun --version
# Expected output: 1.x.x → ✅ Success
```
```

---

## 3.3 — Always State Limitations Clearly

After each journey/tool section, include a **"Known Limitations"** section or ⚠️ block listing:
- What the tool **cannot do**
- Why (so the reader doesn't think they did something wrong)
- Workaround (if available)

---

## 3.4 — Image Placeholders

When a screenshot is needed but not yet available, add a placeholder:

```markdown
> 🖼️ *[Screenshot: describe exactly what needs to be captured, where, and which element to highlight]*
```

Example:
```markdown
> 🖼️ *[Screenshot: Figma Preferences → Enable local MCP server toggle set to ON]*
```

---

---

# SECTION 4 — Expected Output Example

Given the request: *"Write a setup guide for Notion for BAs"*

AI must produce a `.md` file containing:

```
✅ H1 title with emoji
✅ Metadata block (author, date, audience)
✅ "Why do BAs need Notion?" section — starting with a pain point
✅ Roadmap code block
✅ Clearly divided SECTIONS
✅ Steps 1..N with actions + expected results + image placeholders
✅ Summary table at the end of each section
✅ Tips & Tricks
✅ At least 1 real-world case study with ⏱️ time saved
✅ Resources table
✅ Bookmark checklist in a code block
✅ Footer with feedback channel
```

---

# SECTION 5 — Pre-Publish Checklist

```
PRE-PUBLISH CHECK
□ H1 title has emoji and a clear tagline
□ Metadata block present (author, date, audience)
□ Article opens with a pain point, not a definition
□ Every step has an expected result (✅/❌)
□ Terminal commands include both Windows + Mac versions
□ Image placeholders added for all points that need visuals
□ Tool limitations and gotchas are explicitly stated
□ At least one real-world case study included
□ Bookmark checklist at the end
□ Footer with feedback channel
□ Filename uses kebab-case consistent with the repo naming convention
```
