# 📈 GROW: 13 free Claude skills that run your Instagram

You commented **GROW**. Here's your "new employee": the **Instagram agent skill**, a free, open-source pack of 13 Claude skills by Jake Schincariol.

👉 **The link:** https://github.com/Jakeschincariol/instagram-agent-skill

It's MIT-licensed, needs no signup and no API key, and **nothing gets posted until you say yes.** The skills write; you post.

---

## Install it (pick one)

**Easiest: paste this into Claude**

```
https://github.com/Jakeschincariol/instagram-agent-skill

Install this skill, then confirm /ig-reel works.
```

**In Claude Code, yourself:**

```bash
git clone https://github.com/Jakeschincariol/instagram-agent-skill.git
cp -r instagram-agent-skill/skills/ig-* ~/.claude/skills/
```

**Or as a plugin in Claude Code:**

```
/plugin marketplace add Jakeschincariol/instagram-agent-skill
/plugin install instagram-agent
```

**No Claude Code?** You can paste a single skill's `SKILL.md` at the top of a chat and it works as a mode. You lose the five Python tools (the hook scorer, beat timer, caption checker and humanizer), so Claude Code is the full version.

---

## Do this first: teach it your voice (10 minutes)

Every skill reads one file: `voice.md`. Copy `templates/voice.md` from the repo to `~/.claude/instagram/voice.md` and fill it in, or send Claude three of your own Reels and say *"write my voice.md from these"*. This is what makes the ideas sound like you.

---

## The 13 skills

| Command | What it does |
|---|---|
| `/ig-reel` | One idea into a Reel: 3 hooks from 26 formulas, scored, then the script and a timed beat sheet |
| `/ig-viral` | Finds Reels working in your niche, ranks them by how far each beat its own account's normal views, names the hook |
| `/ig-caption` | Writes the caption and shows what people see before "more" |
| `/ig-carousel` | Swipe posts: the cover, slide copy and the files |
| `/ig-story` | Your daily story sequence |
| `/ig-profile` | Scores your profile out of 100 and rewrites what lost points |
| `/ig-plan` | Your week: what to post, which format, when, and who to engage with |
| `/ig-human` | The humanizer: strips em dashes, stock AI phrases and invisible characters |
| `/ig-comment` | Comments for other people's posts |
| `/ig-reply` | Drafts replies to the comments on your posts |
| `/ig-dm` | Keyword replies, first messages and follow-ups |
| `/ig-repurpose` | Turns one video or newsletter into a week of posts |
| `/ig-audit` | Looks back at what you posted and what worked |

---

## Good to know

- **The viral skill needs a browser tool** (like Claude in Chrome or an in-app browser) to look at Reels. It never logs into Instagram for you.
- **You stay in charge.** It drafts; you review and post. Read everything before it goes live.
- **It's free and open source** (MIT). If it helps you, give the author's repo a ⭐.
- Results depend on your content. It's a writing and research helper, not a growth guarantee.

---

*Follow Girmetheus for more AI tools.*
