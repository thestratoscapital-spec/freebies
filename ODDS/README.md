# 📈 ODDS: the free Day Trader skill for Claude (practice with paper money first)

You commented **ODDS**. Here's the **Day Trader skill**: 11 free Claude skills that scan stocks, find setups, plan your stop and target, and **replay a trade 10,000 times before you risk a dollar**. It's by **Jake Schincariol**, the same developer behind the packs from my GROW and TEAM videos.

👉 **The link:** https://github.com/Jakeschincariol/day-trader-skill

Free (MIT licence). No signup, no API key. It reads free public data (Yahoo Finance charts, Nasdaq's stock lists, SEC filings).

> ⚠️ **Read this first.** This is software, not financial advice. In the author's own words: *"Most people who day trade lose money."* Start with paper (fake) money and treat everything it shows as practice.

---

## Install it (pick one)

**Easiest: paste this into Claude Code**

```
https://github.com/Jakeschincariol/day-trader-skill

install skill
```

**As a plugin (Claude Code):**

```
/plugin marketplace add Jakeschincariol/day-trader-skill
/plugin install day-trader-skill@day-trader-skill
```

As a plugin the commands show up as `/day-trader-skill:trader-scanner` and so on.

**By hand (Claude Code):**

```bash
git clone https://github.com/Jakeschincariol/day-trader-skill.git
cp -r day-trader-skill/trader-* ~/.claude/skills/
```

It needs **Python 3.8+** (nothing else to install). The SEC tools ask you to identify yourself: put your name and email in `trader/config.json` as `"sec_user_agent": "Your Name you@example.com"`.

---

## The 11 skills

| Type this | What it does |
|---|---|
| `/trader-scanner` | Scans thousands of US stocks for setups (opening-range breakouts, flags, oversold bounces) |
| `/trader-news` | Tracks breaking news on the stocks you watch |
| `/trader-entry` | Watches a setup bar by bar and tells you when it triggers |
| `/trader-exit` | Sets your stop and target **before** you get in |
| `/trader-timemachine` | Replays the rest of the day 10,000 times from the stock's own recent moves, plus every past day the setup fired, and shows the odds |
| `/trader-budget` | Sizes the trade to your budget and your max loss |
| `/trader-risk` | Checks every order against your limits: PASS or BLOCK |
| `/trader-broker` | Sends an approved order to your broker, **paper trading by default**, never without your "yes" |
| `/trader-alerts` | Rings on your stop, your target and before the close |
| `/trader-analyst` | Reads earnings reports and sums up what changed |
| `/trader-pelosi` | Reads Congress's public stock-trade disclosures |

**One trade, start to finish:**
```
scanner → news → entry → exit → timemachine → budget → risk → broker
```

---

## The example from the video (real data, from the repo)

Tesla, Monday Oct 19 2026, 10:15 AM: it broke above its first-15-minute range (entry 364.18, stop 358.32, target 370.04). The Time Machine replayed the rest of the day 10,000 times:

- **target first: 29.4%**
- **stop first: 25.5%**
- **neither by the close: 45.1%**

Its verdict: close to a coin flip. That's the point: you see the odds **before** your money does.

---

## Practice safely

1. **Stay on paper money.** `"paper": true` is the default. If you connect a broker (the repo uses Alpaca's MCP server), it starts on a paper account.
2. **Keep Claude's approval on.** Set your broker connector to **"Needs approval"**, never "Always allow". Then every order needs your "yes" in the chat **and** a click on Claude's own "Allow once" card.
3. **Set your limits** (max loss per trade, daily loss limit) so `/trader-risk` can block anything over them.

---

## Good to know

- **Not financial advice.** It reads public data and does maths. It can't see the future and doesn't know your situation.
- **The Time Machine is a simulation, not a prediction.** It's built from the last ~60 days of that stock. Earnings, halts and big news can do things those days never did.
- **A stop isn't a guarantee.** In a fast market or a gap, a stop can fill well past its price.
- **The free data is unofficial.** Yahoo's chart feed can lag or change. Check anything important against your broker.
- **Taxes:** day-trading gains are short-term gains. Nothing here is tax advice.
- If it helps you, give the repo a ⭐.

---

*Follow Girmetheus for more AI tools.*
