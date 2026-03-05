# BA Writing Style Reference

Full style rules for all VNG Hana BA skills and how-to guides.
Read this file when drafting a skill that produces written content for BA audiences.

---

## Audience Profile

Always write for someone who:
- **Does not code** — no assumed knowledge of terminal, CLI, or programming
- **Knows BA work** — PRD, user story, wireframe, Jira, Confluence, meeting notes
- **Primary device** — Windows (majority), Mac (some)
- **Goal** — use AI to work faster, not to become a developer

---

## Tone of Voice

| Do | Don't |
|----|-------|
| Friendly like a colleague | Formal like a policy document |
| "you", "we", "our team" | "users", "one should", "it is recommended" |
| Acknowledge pain points openly | Pretend everything is simple |
| Ask rhetorical questions to engage | One-way lecture |
| Light humor that fits the context | Forced jokes or cringe puns |

---

## Structure Rules

### Explain "why" before "how"

Every instruction step must say why it matters before listing actions.

```
❌ Step 1: Run `bun --version`

✅ Step 1 — Verify Bun is installed
   Bun is the runtime that powers the socket server in Journey 2.
   Before starting, confirm it's installed on your machine:
   → Run `bun --version`
```

### Use analogies for technical concepts

Map unfamiliar terms to things BAs already know:

```
❌ "Git is a distributed version control system"
✅ "Git is like Google Docs with full version history — runs on your machine"

❌ "The socket server acts as a message broker"
✅ "The socket server is a middleman — like a receptionist passing messages
    between Cursor (outside) and Figma (inside)"
```

---

## Markdown Elements

### Headings

| Level | Use for |
|-------|---------|
| `# H1` | Major sections / journeys (use ALL CAPS for section name) |
| `## H2` | Steps within a section |
| `### H3` | Sub-steps or named tips |

### Code Blocks

Use for:
- Terminal commands
- Config files (JSON, YAML)
- ASCII flow diagrams
- Before/after examples (❌ vs ✅)
- Expected results and error messages
- Bookmark checklists

Always tag the language when syntax highlighting helps:
` ```bash ` ` ```json ` ` ```powershell ` ` ```markdown `

Use plain ` ``` ` (no tag) for flow diagrams, checklists, and plain-text results.

### Blockquotes

| Symbol | When to use |
|--------|-------------|
| `> 💡` | Tips, nice-to-know extras |
| `> ⚠️` | Warnings, prerequisites, gotchas |
| `> 🖼️` | Placeholder for screenshot to add later |
| `> 💬` | Inline FAQ / common question |
| `> 🎯` | Rule of thumb, decision guide |

### Tables

Use tables for:
- Comparing 2+ options side by side
- Glossaries and term definitions
- Step summaries at end of a section

Comparison columns: ✅ yes/good | ❌ no/bad | ⚠️ partial/limited

---

## Emoji Convention

Use emoji **intentionally** — one per section heading, sparingly in body text.

| Content type | Emoji |
|---|---|
| Journey / path | 🛤️ 🚀 |
| Concepts / theory | 🧠 📚 |
| Setup / hands-on | 🛠️ ⚙️ |
| Tips | 💡 |
| Warnings | ⚠️ |
| Comparison / summary | 🎯 📊 |
| Resources | 📚 🔗 |
| Checklist | 🎁 ✅ |
| Case study | 🚀 ⏱️ |
| Image placeholder | 🖼️ |
| Emotions (use sparingly) | 😅 😮‍💨 🎉 ✌️ |

---

## Required Sections for How-To Guides

Every how-to guide must include these in order:

```
1. H1 title with emoji + tagline
2. Metadata block (author, date, audience)
3. "Why should you care?" — opens with pain point, not definition
4. Roadmap overview (code block)
5. Main SECTIONS / JOURNEYS (H1 headings)
   └── Steps 1..N (H2 headings)
       ├── Why this step matters (1-2 sentences)
       ├── Action list
       ├── Expected result (✅/❌ code block)
       └── Image placeholder if needed
6. Summary table per section
7. Tips & Tricks
8. Real-world case study with ⏱️ time saved
9. Resources table
10. Bookmark checklist (code block)
11. Footer with feedback channel
```

---

## Image Placeholder Format

When a screenshot is needed but not yet available:

```markdown
> 🖼️ *[Screenshot: describe exactly what to capture,
   which UI element to highlight, and what state it should show]*
```

Example:
```markdown
> 🖼️ *[Screenshot: Figma Preferences panel — toggle "Enable local MCP server" set to ON]*
```

---

## Terminal Command Format

When the guide includes terminal commands:

1. Explain what the command does in plain language first
2. Provide both Windows and Mac/Linux versions when they differ
3. Always follow with a verification command + expected output

```markdown
Check that the installation succeeded:

**Windows (PowerShell):**
\```powershell
bun --version
\```

**Mac/Linux:**
\```bash
bun --version
\```

\```
✅ Success: output shows 1.x.x
❌ Error: "command not found" → Bun was not installed. Retry the install step.
\```
```

---

## Limitation Section Format

Every skill or guide that uses a tool must explicitly state what the tool **cannot** do:

```markdown
## ⚠️ Known Limitations

\```
❌ [What it cannot do — stated plainly]
   → Why: [short explanation so reader doesn't think they made a mistake]
   → Workaround: [alternative approach if one exists]

✅ [What it can do — clarify scope]
\```
```
