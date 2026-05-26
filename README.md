# Build an App with Codex — 30-Minute Workshop

You don't need to know how to code. By the end you will have told an AI what to build and watched it write the code — all from inside VS Code.

---

## What is Codex?

Codex is an AI agent built into VS Code. You describe what you want in plain English, and it writes, edits, and runs code for you.

The key difference from a chatbot: Codex works **inside your project folder**. It reads your files, writes new ones, and runs commands.

---

## The Secret Ingredient: `AGENTS.md`

Every project has one file Codex reads first: **`AGENTS.md`**.

This file is your **standing instructions** to the AI — what to build, what rules to follow, and how to behave.

**Whoever controls `AGENTS.md` controls what the AI builds.**

Open it now and read it before doing anything else.

---

## Before You Start

You need:

1. **VS Code** — [code.visualstudio.com](https://code.visualstudio.com)
2. **The Codex extension** — `Ctrl+Shift+X` → search **Codex** → install → sign in with your OpenAI account
3. **This folder open in VS Code** — `File → Open Folder`

No terminal, no other installs.

---

## How to open Codex

Click the Codex icon in the left sidebar, or press `Ctrl+Shift+P` → type `Codex: Open` → Enter.

---

## Step 1 — Pick your app (5 min)

Choose one idea, or invent your own:

| Idea | What it does | What gets stored |
|------|-------------|-----------------|
| **Quote Wall** | Save your favourite quotes. Get them all back in a list. | The quote and who said it |
| **Mood Log** | Record how you're feeling right now with a short note. See all your entries in order. | A mood (good / ok / bad) and a note |
| **Wish List** | Add things you want to buy one day. Mark them as bought when you get them. | Item name and whether it's bought |
| **Daily Wins** | Write down one good thing that happened today. Read back your list any time. | A short win and today's date |

---

## Step 2 — Edit `AGENTS.md` (10 min)

Open `AGENTS.md`. You'll see a rules table and a starter app.

**Your task:** change at least one rule so BOXY builds something you actually want.

| What to change | How |
|----------------|-----|
| **Topic** | Replace `a wall of favourite quotes` with your idea |
| **Starter app** | Rewrite the routes to match your data |
| **Unlock DELETE** | Add `DELETE` to the allowed HTTP methods |

You are writing instructions, not code. Save when done.

---

## Step 3 — Ask Codex to build it (10 min)

Open the Codex panel and type:

```
Build the app described in AGENTS.md. Create all the files needed to run it.
```

Codex will plan the files and ask your approval before changing anything. Click **Accept**.

When it finishes, open the VS Code terminal (`` Ctrl+` ``) and run:

```
pip install fastapi uvicorn
uvicorn main:app --reload
```

Then open **`http://localhost:8000/docs`** — you'll see a visual interface to test every route.

---

## Step 4 — Change one rule, rebuild (5 min)

Edit `AGENTS.md`, then tell Codex:

```
Update the app to match the latest AGENTS.md.
```

One sentence in `AGENTS.md` can add or remove entire sections of code.

---

## Challenges

Pick one — or stack several.

| # | Challenge | What to change in `AGENTS.md` |
|---|-----------|-------------------------------|
| 1 | **Unlock DELETE** | Add `DELETE` to the allowed HTTP methods row |
| 2 | **Add a field** | Add `source` (where you found the quote) to the starter app record |
| 3 | **Unlock LangGraph** | Add `LangGraph: unlocked`, then ask BOXY to add an AI-powered summary endpoint |
| 4 | **Change BOXY's personality** | Edit the Personality section — make BOXY respond like a pirate or a poet |

> Every change in behaviour starts with a change in `AGENTS.md`. The AI follows the file, not its own opinions.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Can't find the Codex panel | `Ctrl+Shift+P` → type `Codex: Open` |
| App won't start | Run `pip install fastapi uvicorn` in the terminal first |
| Codex ignores part of my description | Give that rule its own row in `AGENTS.md` |
