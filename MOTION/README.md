# 🎬 MOTION: make motion graphics with AI (HyperFrames setup guide)

You commented **MOTION**. Here's the official link, how to install it in Claude Code, and 5 starter prompts.

---

## The official link

👉 **[github.com/heygen-com/hyperframes](https://github.com/heygen-com/hyperframes)**

HyperFrames is a free, open-source framework from HeyGen that turns HTML, CSS and animations into MP4 videos. Your AI coding agent writes each scene as code; a hidden (headless) Chrome browser captures it frame by frame, and FFmpeg turns it into a video. Same input, same video, every time.

- **License:** Apache 2.0, with no per-render fees or commercial-use thresholds
- **Works with:** Claude Code, Cursor, Codex, Gemini CLI and other coding agents that support skills

---

## What you need first

- **Node.js 22 or newer:** [nodejs.org](https://nodejs.org)
- **FFmpeg:** [ffmpeg.org](https://ffmpeg.org/download.html) (on Windows: `winget install ffmpeg`; on Mac: `brew install ffmpeg`)
- An AI coding agent, for example **Claude Code**

---

## Install it in Claude Code (2 commands)

```
claude plugin marketplace add heygen-com/hyperframes
claude plugin install hyperframes@hyperframes
```

Restart Claude Code afterwards so it picks up the new skills.

**Not using Claude Code?** Start a project directly:

```
npx hyperframes init my-video
cd my-video
npx hyperframes preview
npx hyperframes render
```

---

## 5 starter prompts (copy, paste, tweak)

1. **Kinetic title:** *"Make a 5-second vertical video: the words 'SHIP IT TODAY' fly in one word at a time on a dark background, with a bold font and one accent color."*
2. **Captions for your clip:** *"Add word-by-word captions to my video `talk.mp4`. Each word lights up as it's spoken. Big, bold, centered in the lower third."*
3. **Chart from a spreadsheet:** *"Turn `views.csv` into a 10-second animated bar chart. Bars grow one after another, with the numbers counting up."*
4. **Product intro:** *"Look at my website [your link], pick out the product name, the main features and the call to action, plan the scenes first, then build a 20-second intro video."*
5. **Logo reveal:** *"Animate my logo `logo.png` with a clean 3-second reveal: scale in, a soft glow, and my tagline underneath."*

Tip: ask it to **show you a few still frames before rendering**. It's much faster to fix the look first.

---

*Follow Girmetheus for more AI tools.*
