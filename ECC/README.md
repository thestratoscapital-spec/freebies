# 🤖 ECC: an open-source AI engineering team for your coding agent

You commented **ECC**. Here's the link, how to install it, and how to actually use it.

👉 **Official repo:** https://github.com/affaan-m/ECC

> ECC is built and maintained by its author, not by me. This page is a quick-start guide; the repo is the source of truth for the latest commands and features.

---

## What it is

ECC is a big, free collection of **agents and skills** for AI coding tools. When the video was made it had **70+ agents and 300+ skills**: planners, builders, reviewers, test writers and a security reviewer, all working inside the tool you already use.

Instead of one chatbot writing snippets, you get a full dev workflow: **plan → build → secure → test**.

---

## Install (Claude Code)

Run these two commands inside Claude Code:

```
/plugin marketplace add affaan-m/ECC
/plugin install ecc@ecc
```

That's it. Restart Claude Code if it asks you to.

- **Codex:** supported too. See the repo's README for its install steps.
- **Cursor:** uses an install script. See the repo's README.

---

## How to use it

Talk to it in plain English, one step at a time:

| Say something like | What happens |
|---|---|
| **"Plan this feature: …"** | It maps out the architecture and the steps before writing code |
| **"Build it."** | It writes the code, in your project's language |
| **"Secure it."** | A security reviewer checks the code and scans for problems |
| **"Test it."** | It writes tests and keeps going until coverage reaches about 80% |

**Tip:** do one step at a time and read the plan before you say "build it". You stay the lead engineer, and the agents are your team.

---

## Before you install anything

- Read the repo's README and look at what the plugin adds.
- Check the license in the repo before reusing any of its files in your own projects.
- Numbers (stars, agents, skills) change fast; the repo has the current ones.

---

*Found this useful? Follow for more short, fact-checked AI dev tips.*
