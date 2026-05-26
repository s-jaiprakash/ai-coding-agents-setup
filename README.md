# Build an App with Codex — 30-Minute Workshop

You don't need to know how to code. By the end of this workshop you will have told an AI exactly what to build and watched it write the code — all from inside VS Code.

---

## What is Codex?

Codex is an AI agent built into VS Code by OpenAI. You describe what you want in plain English, and it writes, edits, and runs code for you. Think of it as a junior developer who works at the speed of typing.

The key difference from ChatGPT: Codex operates **inside your project folder**. It reads your files, writes new ones, and runs commands — it doesn't just answer questions in a chat box.

---

## The Secret Ingredient: `AGENTS.md`

Every project has one file that Codex reads first: **`AGENTS.md`**.

This file is your **standing instructions** to the AI. It tells Codex:
- What the app should do
- What rules to follow
- Which tools and libraries to use
- Even how to talk to you

**Whoever controls `AGENTS.md` controls what the AI builds and how it behaves.**

Open `AGENTS.md` now and read it before doing anything else. Notice BOXY already has opinions.

---

## Prerequisites

You need two things before the workshop starts:

1. **VS Code** — [code.visualstudio.com](https://code.visualstudio.com)
2. **The Codex extension** — install it from the VS Code Marketplace:
   - Open VS Code
   - Press `Ctrl+Shift+X` (or `Cmd+Shift+X` on Mac)
   - Search for **Codex** and install it
   - Sign in with your OpenAI account when prompted

**Open this folder in VS Code** before the workshop:
- `File → Open Folder` → select the folder containing this README

That's it. No terminal, no installation commands.

---

## How to talk to Codex in VS Code

Once the extension is installed, open the Codex panel:

- Click the Codex icon in the left sidebar, **or**
- Press `Ctrl+Shift+P` → type `Codex: Open` → Enter

You'll see a chat-style input. Type your instruction and press Enter. Codex will show you a plan and ask for your approval before changing any files.

---

## Step 1 — Pick Your App (5 minutes)

Choose one idea from the table below, or invent your own. The app should be something you'd actually find useful.

| Idea | What it does |
|------|-------------|
| **Idea Jar** | Save a shower thought and retrieve a random one back |
| **Daily Wins** | Log small wins through the day, get a summary at the end |
| **Link Stash** | Paste a URL with a note, search them later |
| **Mood Log** | Record how you feel (1–5) with a note |
| **Team Standup** | Post your standup note, see today's list for the whole team |

Keep your choice in mind — you'll describe it in the next step.

---

## Step 2 — Read and Edit `AGENTS.md` (10 minutes)

Open `AGENTS.md`. You will see BOXY's rules, including a **rules table** and a **starter app** that looks like this:

**Rules table (what BOXY will enforce):**
| Rule | Current value |
|------|--------------|
| Topic of the app | **office supplies inventory** |
| Maximum endpoints | **3** |
| Allowed HTTP methods | **GET, POST only** |

**Starter app (what BOXY has already planned):**
```
POST /supplies        — add a new office supply (name, quantity)
GET  /supplies        — list all supplies
GET  /supplies/{id}   — get one supply by id
```

This is your "before". Your task is to change the rules so that BOXY builds something you actually want instead.

**What to edit — pick at least one:**

1. **Change the topic** — replace `office supplies inventory` in the rules table with your app idea.
2. **Update the starter app block** — rewrite the endpoints and the example record to match your data.
3. **Optionally** unlock more endpoints, add DELETE, or change BOXY's personality.

You are not writing code. You are writing instructions in plain English.

**Example — changing the topic to "Idea Jar":**
```
| Topic of the app | **a place to save random ideas and retrieve one at random** |
```

Save `AGENTS.md` when done.

---

## Step 3 — Ask Codex to Build It (10 minutes)

Open the Codex panel and type:

```
Build the app described in AGENTS.md. Create all the files needed to run it.
```

Watch what happens. Codex will:
1. Read your `AGENTS.md`
2. Plan what files to create
3. Show you each change before applying it
4. Ask for your approval at each step

Click **Accept** to let Codex write the files.

When it finishes, you will see new files appear in the Explorer panel on the left — something like `main.py`.

**To run the app**, open the VS Code terminal (`Ctrl+`` ` ``) and type:
```
pip install fastapi uvicorn
uvicorn main:app --reload
```

Then open your browser to **`http://localhost:8000/docs`** — you will see a visual interface to test every endpoint you described.

---

## Step 4 — Pick a Challenge, Rebuild (5 minutes)

Go back to `AGENTS.md`, make one of the changes below, then tell Codex:

```
Update the app to match the latest AGENTS.md.
```

Watch the diff. One sentence in `AGENTS.md` can add or remove entire sections of code.

---

### Workshop challenges

Pick one — or stack several if you're feeling bold.

| # | Challenge | What to change in `AGENTS.md` |
|---|-----------|-------------------------------|
| 1 | **Change the topic** | Swap `office supplies inventory` in the rules table for your own app idea |
| 2 | **Unlock DELETE** | Add `DELETE` to the allowed HTTP methods row |
| 3 | **Add a field** | Add a `category` or `tags` field to the starter app record |
| 4 | **Raise the limit** | Change maximum endpoints from `3` to `6` and describe two new routes |
| 5 | **Unlock LangGraph** | Add the line `LangGraph: unlocked` under the Stack section, then ask BOXY to add an AI-powered summary endpoint |
| 6 | **Change BOXY's personality** | Edit the Personality section — make BOXY respond like a pirate, a poet, or a sports commentator |

> Every change in behaviour starts with a change in `AGENTS.md`.
> The AI does not decide — you do.

---

## What You Just Learned

| Concept | What it means in practice |
|---------|--------------------------|
| **AGENTS.md as a contract** | Change the spec, change the app. The AI follows the file, not its own opinions. |
| **Plain English is enough** | You never touched code. You wrote instructions. |
| **Approval loop** | Codex shows every change before applying it — you stay in control. |
| **Iteration** | Building with AI is a conversation. One rule change at a time beats one giant prompt. |

---

## Tips for Better Results

- **Be specific about edge cases.** "Return a 404 if the id does not exist" beats "handle errors."
- **Describe the data first.** If Codex knows the shape of your data, everything else follows.
- **One change at a time.** Small edits to `AGENTS.md` produce cleaner, easier-to-review diffs.
- **Read the plan.** Codex explains its reasoning before acting. That explanation teaches you more than the code itself.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Can't find the Codex panel | Press `Ctrl+Shift+P`, type `Codex`, and look for `Codex: Open` |
| Codex asks for a sign-in | Sign in with your OpenAI account in the extension popup |
| App won't start | Open the terminal and run `pip install fastapi uvicorn` first |
| Codex ignores part of my description | Give that rule its own bullet point or table row in `AGENTS.md` |
| Codex changes something unexpected | Click **Reject** on that step, then clarify the rule in `AGENTS.md` |

---

## Further Reading

- [Codex VS Code extension](https://marketplace.visualstudio.com/items?itemName=openai.codex)
- [OpenAI Codex docs](https://platform.openai.com/docs/codex)
- [AGENTS.md specification](https://openai.com/index/codex)
