# 1️⃣ ONE: the one-agent setup

You commented **ONE**. You don't need ten AI agents. You need one, set up right. Here's the setup from the video: a rulebook, skills, your tools, and helpers. It's the same setup I use to make these videos.

It works in **Claude Code** (best for files and projects) and in the **Claude app** (claude.ai, desktop or phone). Each step tells you where it goes in both.

---

## Step 1: give it a rulebook (one instructions file)

One file that says who you are, how you work, and what never to do. Claude reads it at the start of every chat, so you stop repeating yourself.

- **Claude Code:** create a file called `CLAUDE.md` in your project folder. Claude Code reads it every session.
- **Claude app:** make a **Project** and paste the rulebook into the project's **instructions**. Every chat in that project follows it.

**Copy this and fill in the [brackets]:**

```markdown
# Who I am
I'm [name], a [what you do]. My audience is [who].

# How I work
- Keep answers short. Use plain words.
- Ask me before doing anything you can't undo (sending, posting, deleting).
- When you finish a task, tell me what's done and what's still left.

# Never
- Never share or print my passwords, API keys or private info.
- Never make up facts or numbers. If you're not sure, say so.

# My usual jobs
- [weekly report] → use the [report] skill
- [content ideas] → use the [ideas] skill
```

💡 **How mine works:** my video folder has a `CLAUDE.md` that says "for any reel request, follow the reel kit's instructions", plus my rules: my channel name, my voice settings, never post without asking me.

---

## Step 2: give it skills (saved recipes)

A skill is a saved recipe for a job you repeat. It's a folder with a `SKILL.md` file: a short description at the top, then the steps. Claude only loads a skill when the job needs it, so you can have lots of them without slowing it down.

- **Claude Code:** put it at `.claude/skills/<skill-name>/SKILL.md` in your project (or in `~/.claude/skills/` for every project).
- **Claude app:** go to **Settings → Capabilities → Skills** and upload the skill folder as a .zip. (Skills are on paid plans, and code execution needs to be on.)

**Starter skill:** save this as `weekly-report/SKILL.md`:

```markdown
---
name: weekly-report
description: Writes my weekly report. Use when I ask for the weekly report or a summary of my week.
---

1. Ask me for this week's numbers (or read them from the file I give you).
2. Write it in my style: 5 bullet points max, wins first, then problems, then next week's plan.
3. End with one line: "Biggest thing next week: ..."
4. Show me the draft. Only send it to the team after I say yes.
```

The **description** is the important part: it's how Claude knows when to pick up the skill. Say what the skill does and when to use it.

💡 **How mine works:** my whole video editor is one big skill. Script → voice → animation → sound → export, with my style rules written in.

---

## Step 3: connect your tools

Connectors let Claude work inside your real tools (calendar, docs, email) instead of you copying and pasting.

- **Claude app:** **Settings → Connectors**. Turn on Google Calendar, Gmail, Google Drive and others, then sign in.
- **Claude Code:** add tools as **MCP servers** (type `/mcp` in Claude Code to see and manage them).

Then you can say things like *"check my calendar and find a free hour on Thursday"* or *"read the doc called Q3 plan and summarize it"*.

✅ Only connect what you need. Claude can read whatever you connect, so leave out accounts you don't want it touching.

---

## Step 4: let it send out helpers (for big jobs)

When a job is too big, Claude Code can split it up and send out **subagents**. These are helpers that each take a piece of the work (research, drafting, checking) and report back. You still talk to just one agent.

- **Claude Code:** just ask for it: *"Use subagents: one researches, one drafts, one checks the facts."* You can also save your own helpers as files in `.claude/agents/`.
- **Claude app:** for big research jobs, turn on **Research** mode and it runs a long multi-step search for you.

---

## Good to know

- **Start small.** A 10-line rulebook and one skill already beat ten separate agents.
- **Fix the rulebook, not the chat.** When Claude gets something wrong twice, add a line to your instructions file so it never happens again.
- **Features change.** Menu names and plan limits move around, so check Claude's help pages if something looks different.

---

*Follow Girmetheus for more AI tools.*
