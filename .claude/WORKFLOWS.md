# Classroom Workflows — novice-dev-with-ai

> This file extends the ECC workflow system with classroom-specific playbooks.
> The ECC base system (agents, skills, hooks) remains fully intact.

---

## 1. New Student Onboarding Workflow

When a student starts their first session:

```
Step 1 → Run /learn command with topic: "HTML Basics"
Step 2 → AI explains what a webpage is (concept-first)
Step 3 → AI shows the minimal 5-line HTML boilerplate
Step 4 → Student types it manually (no copy-paste)
Step 5 → AI reviews their version with beginner rubric
Step 6 → Student saves and opens in browser
Step 7 → AI celebrates success + previews next concept
```

**Key rule**: Never skip Step 2. Concepts before code, always.

---

## 2. Lesson Delivery Workflow

For every new concept introduced:

```
[EXPLAIN] → Plain English definition (1-3 sentences)
[ANALOGY] → Real-world comparison
[VISUAL]  → ASCII diagram or description of what it looks like
[MINIMAL] → Smallest possible working code example (< 20 lines)
[EXERCISE]→ Student writes a variation themselves
[REVIEW]  → AI reviews with beginner rubric
[CONNECT] → How this connects to the next concept
```

**Example — Teaching Flexbox:**

> **EXPLAIN**: Flexbox is a CSS layout system that arranges elements in a single row or column.
>
> **ANALOGY**: Think of a bookshelf. Flexbox lets you say "put all my books in a row, spread them out evenly, and center them vertically."
>
> **MINIMAL CODE** (shown after explanation):
> ```css
> .container {
>   display: flex;        /* Turn on flexbox */
>   justify-content: center; /* Center horizontally */
>   align-items: center;    /* Center vertically */
> }
> ```

---

## 3. Error Recovery Workflow

When a student's code has a bug:

```
Step 1 → Identify the type of error (syntax, logic, visual)
Step 2 → Explain the error in plain English
         BAD:  "You have an unclosed tag"
         GOOD: "Your <div> on line 5 doesn't have a matching </div>.
                Every opening tag needs a closing tag, like opening
                and closing a pair of parentheses."
Step 3 → Ask the student to find the error themselves first
Step 4 → Give a hint if they're stuck (30 seconds)
Step 5 → Show the fix if they need it — but annotate the fix
Step 6 → Ask the student to explain the fix back to you
```

---

## 4. Code Review Workflow (Beginner Edition)

Triggered when student asks "can you check my code?" or after any submission:

```
1. Read the full file before commenting
2. Apply beginner rubric (see CLAUDE.md)
3. Highlight 1 thing they did WELL first
4. Identify the single most important issue only
5. Ask guiding questions before giving the answer:
   "What do you think happens if we remove that closing tag?"
6. Suggest one improvement for the NEXT version
```

**Rubric scoring:**
- ✅ Great — Give specific praise ("Your class names are very descriptive!")
- ⚠️ Needs work — Explain why + give a guiding question
- ❌ Missing — Explain the concept from scratch

---

## 5. Project Build Workflow (Beginner)

For student projects (personal portfolio, landing page, etc.):

```
Phase 1 — Wireframe in words
  → Student describes what they want (no code yet)
  → AI creates a written content outline
  → AI sketches the structure in plain English

Phase 2 — HTML skeleton
  → Build semantic structure ONLY (no CSS)
  → Review semantics before any styling

Phase 3 — CSS: Typography + Reset
  → body font, margins reset, color variables
  → Nothing else yet

Phase 4 — CSS: Layout
  → Choose Flexbox OR Grid (not both)
  → Mobile layout first

Phase 5 — CSS: Polish
  → Colors, spacing, hover states

Phase 6 — Responsive
  → One breakpoint: 768px tablet
  → Another: 480px mobile

Phase 7 — Final review
  → Run beginner code review rubric
  → Accessibility check
  → Browser check (Chrome + mobile view)
```

---

## 6. AI Interaction Guidance for Students

How students should talk to the AI:

### Good prompts (teach the student to use these):
- "Explain what [X] is in simple terms before showing me code"
- "Review my code and tell me what I did well and what needs improving"
- "I'm stuck on [X] — give me a hint, not the answer"
- "Show me the smallest example of [X]"
- "Why does this code not work?" + paste the broken code

### Anti-patterns to avoid:
- ❌ "Write my whole website for me"
- ❌ "Fix all the bugs in my code"
- ❌ "Give me the final version of [X]"

### The "3 Before AI" Rule:
Before asking the AI, students must:
1. Re-read the lesson notes
2. Try one more approach on their own
3. Look at the error message carefully

---

## 7. ECC System Integration

The classroom layer sits on top of ECC v1.9.0. All ECC workflows remain active:

| ECC Workflow | Classroom Override? | Notes |
|---|---|---|
| TDD workflow | No — not used in Modules 1-7 | JavaScript only (Module 8+) |
| Code review | Extended with beginner rubric | ECC reviewer still runs, but beginner filter applied |
| Security review | No change | Keep all security checks |
| Build error resolver | Extended: plain English first | Always translate errors before fixing |
| Planner agent | Extended: concept maps for lessons | Use for lesson planning |
| Git workflow | Simplified for students | Commit message format: "add: [what you built]" |
