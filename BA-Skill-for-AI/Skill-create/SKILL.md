---
name: BA Skill Creator
description: Create a new Claude skill (.md + folder structure) tailored for non-tech BA workflows at VNG Hana. Use this skill whenever a user wants to build a new skill, capture a repeatable BA workflow as a skill, or improve an existing BA skill. Triggers on: "create a skill", "write a skill for", "make a skill that", "turn this workflow into a skill", "new skill for BA".
---

# BA Skill Creator

A meta-skill for building new skills that help Business Analysts work faster with AI.

When triggered, your job is to interview the user, draft a well-structured skill, and deliver a ready-to-use folder following the standard layout below.

---

## Skill Anatomy (always produce this structure)

```
skill-name/
├── SKILL.md              ← required: YAML frontmatter + instructions
├── references/           ← optional: docs loaded into context as needed
│   ├── writing-style.md  ← BA writing style rules (guidance for AI)
│   └── [domain].md       ← domain-specific reference (add as needed)
├── scripts/              ← optional: reusable Python/JS helpers
└── assets/               ← optional: templates, icons, fonts used in output
    └── ba-skill-template.md  ← blank template to clone for new skills
```

Keep `SKILL.md` under 500 lines. If you need more, split content into `references/` files and point to them clearly from `SKILL.md`.

---

## Step 1 — Capture Intent

Before writing anything, ask the user these questions (only the ones not already answered in the conversation):

1. **What should this skill enable Claude to do?** (one sentence)
2. **Who will use it?** (BA role, technical level, team context)
3. **When should it trigger?** (what user phrases or situations)
4. **What does a good output look like?** (format, length, tone, language)
5. **Any examples of past work to reference?** (existing docs, templates, repo files)

Extract answers from context first — don't ask questions the user already answered.

---

## Step 2 — Draft the SKILL.md

Use this exact template. Fill every section based on the interview. Delete optional sections only if genuinely not needed.

```markdown
---
name: [Human-readable skill name, max 64 chars]
description: [What it does + when to trigger it. Be specific and slightly "pushy" — 
mention trigger phrases so Claude doesn't under-trigger. Max 200 chars.]
---

# [Skill Name]

[1–2 sentence overview: what the skill does and why a BA would use it.]

---

## When to Use This Skill

- [Trigger situation 1]
- [Trigger situation 2]
- [Trigger situation 3]

---

## Inputs

What the user typically provides:
- [Input type 1, e.g. "A rough list of requirements"]
- [Input type 2, e.g. "A Figma link or screenshot"]

---

## Output Format

[Describe the expected output: file type, structure, language (Vietnamese/English), 
tone, length. Include a template if the output has a fixed structure.]

**Template:**
[paste exact output template here if applicable]

---

## Step-by-Step Instructions

### Step 1 — [Action verb + short description]

[Why this step matters — 1 sentence]

[What to do — numbered list or bullets]

\```
[Example or expected result]
\```

### Step 2 — [Next action]

[Repeat pattern above]

---

## Examples

**Example 1:**
Input: [realistic user request]
Output: [what good output looks like]

---

## Limitations

- [What this skill cannot do]
- [When to use a different approach instead]

---

## Related Skills

- [Name of another skill that pairs well with this one, if any]
```

---

## Step 3 — Writing Style Rules for BA Skills

All BA skills at VNG Hana follow these rules. Apply them when drafting skill instructions and any output templates:

> See `references/writing-style.md` for the full style guide. Key rules summarized below.

**Tone:** Friendly colleague — not a corporate manual. Use "you", "we", direct verbs.

**Explain "why" before "how":** Every instruction step should say why it matters before listing what to do.

**Use analogies for technical concepts:** Map unfamiliar things to what BAs already know.
```
❌ "Use a distributed version control system"
✅ "Think of it like Google Docs with full version history — but faster and smarter"
```

**Use code blocks for:** commands, configs, ASCII flow diagrams, before/after examples, checklists.

**Use blockquotes for:**
- `> 💡` tips
- `> ⚠️` warnings / prerequisites
- `> 🖼️` image placeholders

**Emoji convention** — intentional, not decorative:

| Section type | Emoji |
|---|---|
| Journey / path | 🛤️ 🚀 |
| Concepts | 🧠 📚 |
| Setup / hands-on | 🛠️ ⚙️ |
| Tips | 💡 |
| Warnings | ⚠️ |
| Case study | 🚀 ⏱️ |
| Checklist | 🎁 ✅ |

---

## Step 4 — Describe Field Optimization

The `description` field in YAML frontmatter is the primary trigger mechanism — Claude reads this to decide whether to invoke the skill.

**Rules for a good description:**
- State **what the skill does** clearly
- State **when to trigger** — include specific phrases users might type
- Be slightly "pushy": instead of "how to do X", write "use this whenever the user wants X, even if they don't use the exact word X"
- Max 200 characters

**Pattern:**
```
[Action verb] [what it produces] for [audience/context]. 
Use whenever [trigger phrase 1], [trigger phrase 2], or [trigger phrase 3].
```

**Example:**
```yaml
description: Write step-by-step technical guides for non-tech BAs at VNG Hana.
Use whenever asked to write a how-to, tutorial, setup guide, or onboarding doc,
even if the word "guide" isn't mentioned.
```

---

## Step 5 — Deliver the Skill

After drafting:

1. Create the folder structure: `skill-name/` with `SKILL.md` + subdirs as needed
2. If a reusable reference doc is needed (e.g., writing style, domain glossary), write it to `references/`
3. If a template is needed (e.g., blank SKILL structure to clone), write it to `assets/`
4. If a reusable script is needed (e.g., a formatter, a template filler), write it to `scripts/`
5. Show the user the final tree:

```
skill-name/
├── SKILL.md
├── references/
│   └── [any-reference].md
├── scripts/
└── assets/
    └── [any-template].md
```

6. Ask: "Does this look right? Anything to add or adjust before we zip it up?"

---

## Pre-Delivery Checklist

Before handing off, verify:

```
SKILL QUALITY CHECK
□ SKILL.md has valid YAML frontmatter (name + description)
□ description field is ≤200 chars and includes trigger phrases
□ Skill has a clear "When to Use" section
□ Every instruction step explains "why" before "how"
□ Output format or template is clearly defined
□ At least 1 example (input → output) is included
□ Limitations section lists what the skill cannot do
□ SKILL.md is under 500 lines
□ Large reference content is moved to references/ folder
□ Folder structure matches the standard anatomy
```

---

## Reference Files in This Skill

- `references/writing-style.md` — Full BA writing style rules (tone, emoji, tables, code blocks)
- `assets/ba-skill-template.md` — Blank SKILL.md template to clone for new skills
