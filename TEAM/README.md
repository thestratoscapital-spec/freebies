# 🎬 TEAM: turn Claude into your YouTube team

You commented **TEAM**. Here's the **YouTube Agent Skill**: 11 free Claude skills for scripts, titles and thumbnails, edit plans, comments, planning and finding what's working in your niche. It's by **Jake Schincariol**, the same developer behind the Instagram pack from my GROW video.

👉 **The link:** https://github.com/Jakeschincariol/youtube-agent-skill

Free (MIT licence). No signup, no API key, nothing to connect.

---

## Install it (pick one)

**Easiest: paste this into Claude Code**

```
https://github.com/Jakeschincariol/youtube-agent-skill

Install this skill, then confirm /yt-script works.
```

**As a plugin (Claude Code):**

```
/plugin marketplace add Jakeschincariol/youtube-agent-skill
/plugin install youtube-agent@youtube-agent-skill
```

**By hand (Claude Code):**

```bash
git clone https://github.com/Jakeschincariol/youtube-agent-skill.git
cp -r youtube-agent-skill/skills/yt-* ~/.claude/skills/
```

> No Claude Code? You can paste any single skill's `SKILL.md` at the top of a normal Claude chat and it works as a mode. You lose the built-in tools (most useful for `/yt-script`, `/yt-retention` and `/yt-edit`), but the rest still works.

---

## Step 2: your voice file (10 minutes, do this first)

Every skill reads one file that describes how **you** talk. Copy `templates/voice.md` to `~/.claude/youtube/voice.md` and fill it in, or just send Claude three of your own videos and say:

```
Write my voice.md from these.
```

---

## The 11 skills

| Type this | What you get |
|---|---|
| `/yt-script` | Your idea turned into a script: 5 hooks from 21 hook formulas, each scored, then the full script |
| `/yt-package` | Your title and thumbnail written **as a pair**, checked so they don't repeat each other or get cut off |
| `/yt-edit` | An edit plan from your transcript: dead air, "ums" and retakes, with timecodes (you make the cuts) |
| `/yt-comment` | Your comments sorted into piles, replies drafted in your voice, and which one to pin |
| `/yt-plan` | A week that fits the hours you actually have |
| `/yt-viral` | What's working in your niche: videos ranked by how far they beat **their own channel's** usual views |
| `/yt-retention` | Your audience-retention export read for you: where people left, and what you were saying then |
| `/yt-shorts` | The Shorts already hiding inside a long video, each with a new first line |
| `/yt-seo` | Your description, the few tags worth having, and the searches this video should win |
| `/yt-chapters` | Chapters from your transcript that follow YouTube's rules, so they actually show up |
| `/yt-audit` | Your whole channel reviewed, ending in **one** fix to make first |

**Try this first:**
```
/yt-script I want to make a video about [your idea]. My audience is [who].
```

---

## Good to know

- **It writes, you post.** Nothing gets uploaded or published for you. Every skill ends with something you copy and a question: ship it or change it?
- **The hook score is a guide, not a promise.** The author built it from 74 real hooks and says plainly that a high score doesn't guarantee views.
- **`/yt-viral` reads public pages only.** It never logs in as you. It tells you which hook a video used, but that's not proof of *why* the video took off.
- **It won't make up numbers.** If it needs a figure it doesn't have, it asks you.
- **The skills are free; Claude isn't.** You use your own Claude plan.
- If it helps you, give the repo a ⭐.

---

*Follow Girmetheus for more AI tools.*
