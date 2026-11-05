# BILL: the cost-proof checklist for your AI-built app

From the video *"What if one night of traffic sent you a bill for thousands of dollars?"*

Seven ways an AI-built app quietly costs you money, and how to stop each one. There's a prompt at the bottom so Claude checks your code for you.

## The 7 money leaks

| # | Leak | What to do |
|---|---|---|
| 1 | **Exposed secret keys** | Never put private API keys in browser code. Keep them in server environment variables. If one was ever exposed, **rotate it now**. |
| 2 | **Unlimited requests** | Add rate limits per user and per IP to every route that calls a paid API (especially AI). Add CAPTCHA or login before expensive actions. |
| 3 | **No spending caps** | Turn on billing alerts and usage/budget limits in every dashboard you pay: your AI provider, cloud host, database, email, maps. |
| 4 | **The wrong AI model** | Use smaller, cheaper models for simple tasks (labels, short summaries, routing). Save the biggest model for hard jobs. Cap max output length. |
| 5 | **No caching** | Cache answers to repeated questions and results of expensive calls, so you don't pay twice for the same thing. |
| 6 | **Loops** | Give every retry a limit and a backoff (wait longer each time). Add timeouts. Make sure scheduled jobs can't run on top of each other. |
| 7 | **Free-tier traps** | Write down the free limit for each service (database size, bandwidth, function calls, emails) and set an alert before you hit it. |

## The prompt (paste into Claude Code in your project)

```
Audit this codebase for money leaks. For each item, say OK, LEAK or NOT USED,
point to files and lines, and estimate the risk in one plain sentence:
1. Secret keys reachable from browser code or committed to the repo.
2. Routes calling paid APIs with no rate limit or auth.
3. Which paid services we use (so I can set billing alerts and caps on each).
4. AI calls using a large model for simple tasks, or with no max output limit.
5. Repeated expensive calls that could be cached.
6. Retries with no limit/backoff, missing timeouts, jobs that could overlap.
7. Services we use that have a free tier, and what usage would push us to paid.
End with a table sorted by how much money each could cost. Don't change code yet.
```

## Good to know

- Check your provider dashboards yourself. Caps and alerts live there, not in your code.
- Prices and free tiers change. Always check the current pricing page.

Part two: [DOORS](../DOORS/), the 7 security doors to check before launch.
