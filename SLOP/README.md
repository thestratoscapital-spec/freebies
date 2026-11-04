# 🎨 SLOP: stop your AI-built site from looking AI-built

You commented **SLOP**. Here are the two free design skills from the video, the exact install commands, and how to use each one.

**The AI look:** a purple-to-blue gradient, the same font as everyone else, cards inside cards, a little icon above every heading. Both tools are built to catch exactly that.

---

## 1 · Hallmark (by Together AI)

**Link:** https://github.com/Nutlope/hallmark · site: https://usehallmark.com
**License:** MIT (free to use, fork and ship)

**What it does**
- Deals you **3 themes from a catalog of 50** (each one a full material: paper, type, colour, components).
- Builds the page around **what the visitor came to do** (a booking page books, a shop sells).
- Checks the result **in a real browser at 8 widths** for the tells that read as machine-made.
- A **fresh reviewer** (a new subagent) gets the final word before it ships.

**Install** (needs Node 18+)
```
npx skills add nutlope/hallmark -g
```
Or inside Claude Code: `/plugin marketplace add nutlope/hallmark` then `/plugin install hallmark@hallmark`.

**Use it**
```
/hallmark a landing page for my habit tracker app
/hallmark redesign ./src/app
/hallmark audit ./index.html
```
Tip: the browser checks also need `npm i -g puppeteer-core` and Chrome. Without them, the static checks still run.

---

## 2 · Impeccable (by Paul Bakaus)

**Link:** https://github.com/pbakaus/impeccable · docs: https://impeccable.style/docs
**License:** Apache-2.0

**What it does**
- Gives your agent **design words**: `bolder`, `quieter`, `polish`, `distill`, `typeset`, `layout`, `animate`… 24 commands in total.
- `critique` scores a design and ranks what to fix first; `audit` checks accessibility, performance and responsive layout.
- A **slop detector with 62 rules**. No LLM and **no API key** needed for it.

**Install** (from your project folder)
```
npx impeccable install
```
Reload your coding tool, then run `/impeccable init` once per project.

**Use it** (narrow targets work best)
```
/impeccable critique the pricing cards
/impeccable bolder the hero section
/impeccable polish settings
```

---

## Which one when?

| You want… | Use |
|---|---|
| A brand-new page that doesn't look AI-made | **Hallmark** |
| To fix or level up a page you already have | **Impeccable** |
| A second opinion before you ship | Both: `/hallmark audit` + `/impeccable critique` |

Both work in **Claude Code, Cursor and Codex** (and more).

---

Facts checked on November 3, 2026 against each project's GitHub README. The example screenshots in the video come from those READMEs. Star counts change daily.
