# 🔒 LOCK: stop your AI coding agent from reading your `.env`

You commented **LOCK**. Here's the exact settings file from the video, how to install it in 60 seconds, and the three extra steps that actually keep your keys safe.

---

## Why this matters (30-second version)

Your API keys usually live in a `.env` file inside your project. To an AI coding agent, that's just another file. If it reads it, those keys become part of what gets sent to the model.

Security researchers at Sonar planted a fake key in a `.env` file and watched it show up word for word in a coding agent's traffic.

Telling your agent *"don't read my secrets"* is a **request**. A deny rule is a **lock**.

---

## The settings file

```json
{
  "permissions": {
    "deny": [
      "Read(./.env)",
      "Read(./.env.*)"
    ]
  }
}
```

- `Read(./.env)` blocks the main `.env` file.
- `Read(./.env.*)` blocks the variants: `.env.local`, `.env.production`, and so on.

(The same file is in this folder as [`settings.json`](settings.json).)

---

## Install it (Claude Code)

Pick **one** place to put it:

| File | Applies to |
|---|---|
| `~/.claude/settings.json` | **every** project on your computer (recommended) |
| `.claude/settings.json` inside a project | just that project, and shared with your team if you commit it |

1. Open the file (create it if it doesn't exist).
2. Paste the JSON above. If the file already has a `"permissions"` section, just add the two lines to its `"deny"` list.
3. Save, then restart Claude Code.

**Check that it works:** ask Claude Code to *"read my .env file"*. It should say it doesn't have permission.

---

## ⚠️ The honest part: a lock is not a vault

Deny rules cover Claude Code's own file-reading tools. They're a strong first layer, but they're **not a guarantee**: an agent could still reach a secret another way (for example, through a shell command). That's why the video says *"then go further"*:

### 1. Keep real secrets out of your project folder
If the key isn't in the folder the agent works in, it can't stumble on it. Use placeholder values in the project, like this one:

```
OPENAI_API_KEY=sk-FAKE-placeholder
```

### 2. Use a secrets manager
Load real keys at runtime from a secrets manager or your password manager's CLI, instead of a plain-text file sitting next to your code.

### 3. Scan before you push
Run a secret scanner before every commit or push, so a key never lands on GitHub by accident. Popular free ones: **gitleaks** and **GitHub's built-in secret scanning**.

---

## Sources

- Claude Code settings docs (permissions and deny rules): https://code.claude.com/docs/en/settings
- Sonar: *Your secrets are leaking to AI coding agents*: https://www.sonarsource.com/blog/your-secrets-are-leaking-to-ai-coding-agents/
- Knostic: Claude Code / Cursor `.env` secret leakage: https://www.knostic.ai/blog/claude-cursor-env-file-secret-leakage

---

*Found this useful? Follow for more short, fact-checked AI dev tips.*
