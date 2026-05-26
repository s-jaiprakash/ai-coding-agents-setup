---
marp: true
theme: default
paginate: true
style: |
  section {
    font-family: 'Segoe UI', sans-serif;
    padding: 60px;
  }
  h1 { color: #1a1a2e; }
  h2 { color: #16213e; border-bottom: 3px solid #0f3460; padding-bottom: 8px; }
  strong { color: #0f3460; }
  blockquote { border-left: 4px solid #0f3460; color: #555; }
  ul li { margin-bottom: 10px; }
---

# Coding with AI
## What changes. What doesn't.

Workshop — May 2026

---

## The shift that's already happening

- Writing code used to require years of training
- AI tools like Codex let **anyone describe what they want** and see it built
- The bottleneck is no longer typing code — it's knowing what to ask for

> The most valuable skill is now clarity of thought, not syntax.

---

## What Codex can do for you

| Task | Before | With Codex |
|------|--------|------------|
| Build a simple API | Hours, needs a developer | Minutes, needs a clear description |
| Add a new feature | Edit multiple files carefully | One sentence in `AGENTS.md` |
| Fix a bug | Read and understand the code first | Describe the symptom, review the fix |
| Explore an idea | Prototype takes days | Running prototype in under an hour |

---

## Things to keep in mind

- **You are the architect.** Codex builds what you describe — vague instructions produce vague software.
- **Review every change.** Codex shows you a diff before applying it. Read it.
- **One change at a time.** Small, focused instructions produce clean, understandable results.
- **The file is the contract.** `AGENTS.md` is what the AI actually follows — keep it honest and up to date.

---

## What to avoid altogether

- **Blind trust** — generated code can be wrong, outdated, or insecure. Always review.
- **Pasting sensitive data** — never put passwords, API keys, or personal data into a prompt.
- **Using AI to skip understanding** — if you don't know what the code does, you can't catch when it goes wrong.
- **One giant prompt** — "build me an entire app" produces a mess. Break it into steps.
- **Ignoring the diff** — clicking Accept without reading is how bugs get introduced silently.

---

## The rule

> **Whoever controls `AGENTS.md` controls what the AI builds.**

The AI does not have opinions about your product.
It follows instructions.

Write better instructions — get better software.

---

## Today's workshop

1. Read `AGENTS.md` — understand the rules
2. Change one rule — make it yours
3. Ask Codex to build it — review and accept
4. Change another rule — watch the code change

**The goal isn't a finished app. It's understanding the loop.**
