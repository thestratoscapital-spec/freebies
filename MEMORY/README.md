# 🧠 MEMORY: give Claude Code a memory between sessions

You commented **MEMORY**. Here's Claude-Mem from the video: the link, the setup steps, and how to use it.

**The problem:** every new Claude Code session starts blank. Your project, yesterday's bug fix, the decisions you made… you explain it all again.

---

## Claude-Mem

**Link:** https://github.com/thedotmack/claude-mem
**License:** Apache-2.0 (open source)

**How it works**
1. **Watches** what your agent does in a session (files read, fixes, decisions) through Claude Code's hooks.
2. **Compresses** it with AI into short notes, saved in a local SQLite database on your computer.
3. **Loads the useful parts back in** automatically when you start a new session.
4. **Search your history** in plain English: "what did we change on the login page last week?"

---

## Setup

**Option A: one command**
```
npx claude-mem install
```
Restart Claude Code. Context from past sessions will appear in new ones.

**Option B: from inside Claude Code**
```
/plugin marketplace add thedotmack/claude-mem
/plugin install claude-mem
```

⚠️ **Good to know before you install:**
- The installer offers to **sign you in to claude-mem's hosted memory** (a 30-day free trial, no card). You don't have to: pass a `--provider` flag (your Anthropic plan, or your own OpenRouter/Gemini key) or set `CLAUDE_MEM_ONLINE_OPTIN=false` to skip sign-in.
- **Don't** use `npm install -g claude-mem`: that only installs the library, not the plugin hooks.
- **Cloud Sync and screenshots are opt-in** (off by default).

---

## Keep secrets out

Wrap anything you never want stored in private tags:
```
<private>
STRIPE_KEY = sk_live_...
</private>
```
Content inside `<private>` is excluded from memory.

---

## Works with

Claude Code, Cursor, Codex, OpenCode and more (see the README for the `--ide` flag for each).

---

Facts checked on November 3, 2026 against the claude-mem README. Star counts change daily (112k on that day).
