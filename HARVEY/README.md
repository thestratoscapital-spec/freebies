# 🤝 HARVEY: an AI agent that finds you customers

You commented **HARVEY**. Here's the free, open-source sales agent from the video: the link, what you need, and the setup.

---

## Harvey

**Link:** https://github.com/ethanplusai/harvey
**License:** MIT (free to use and change)

**What it does, in a loop on your own computer (every 15 minutes by default)**
1. **Finds businesses** that could buy from you. The default source, OpenStreetMap, is free with no account.
2. **Reads each website** (free, no AI call) and spots something specific: no online booking, a blog nobody updates, a job they're hiring for, which agency built their site.
3. **Writes a cold email** about exactly what it found, using Claude.
4. **Reads the replies**, drafts the follow-up and works each conversation toward a meeting.
5. **Live dashboard** for your leads, conversations and pipeline (on your computer at `localhost:5555`).

**Nothing sends without you.** By default every email waits in the **Outbox** until you approve it. There's also a kill switch: `harvey sending pause`.

---

## What you need

- **Claude Pro or Max**, with Claude Code logged in (`claude login`). Harvey uses your subscription, so there's **no API bill**. (A ChatGPT plan with Codex works too.)
- **Python 3.11 or newer**
- **A mailbox to send from.** Google Workspace is about $7/month. Use a separate domain, not your main one.
- **A warm-up service** on that mailbox (the README recommends TrulyInbox) so your emails don't land in spam.

---

## Setup (easiest way)

```
git clone https://github.com/ethanplusai/harvey.git
cd harvey
claude
```
Then type: **set up Harvey for me**

The repo comes with instructions for Claude Code, so it checks what you have, installs what's missing, asks you a few questions and learns your product from your website.

**Then:**
```
harvey signals --confirm free   # choose what makes a good prospect (the free ones)
harvey discover                 # find businesses
harvey dashboard                # open your dashboard
harvey run                      # start the loop
```

---

## Good to know

- **You choose what it looks for.** Harvey knows 29 signals about a business and collects none of them until you confirm. 26 are free.
- **Free source, thin coverage:** OpenStreetMap maps storefronts, so some trades (roofers, plumbers) barely show up. Cheap paid sources are listed in the README if you need more.
- **Cold email has rules.** Follow the anti-spam laws where you and your prospects are (e.g. CAN-SPAM, GDPR). Read the README's "Legal and deliverability" section before sending.
- It uses part of your Claude usage, but it watches your quota and leaves room for your own work.

---

Facts checked on November 4, 2026 against the Harvey README. Star counts change daily (4.4k on that day). The dashboard screenshots in the video are the README's own demo, with made-up data.
