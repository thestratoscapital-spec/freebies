# JARVIS: build your own AI assistant, step by step

From the video *"Imagine having your own Jarvis."*

An AI assistant that remembers what you tell it, handles daily tasks and works while you sleep. Here's the whole setup in 9 steps, plus the 3 safety rules you should never skip.

> Plain-words version. Exact install commands change often, so each step points to the official docs.

## The 9 steps

| # | Step | What to do |
|---|---|---|
| 1 | **A home** | Pick where it runs: your own computer (free, but only works while it's on) or a cheap cloud server (VPS) that stays online 24/7. |
| 2 | **Hermes Agent** | Install [Hermes Agent](https://hermes-agent.org/) from Nous Research. It's free and open source (MIT) and acts as the control center. On Windows, use WSL2 (native Windows support is experimental). |
| 3 | **A brain** | Connect an AI model: Claude, OpenAI, or an open-source model. You add your API key in the setup. |
| 4 | **The interview** | Tell it about your business, your goals and how you work. The more context, the better it helps. |
| 5 | **Memory** | Turn on memory so it remembers what matters between chats. For heavy use, many people add an extra memory layer on top. |
| 6 | **Skills** | Teach it a skill for every job you repeat (reply to emails, weekly report, plan content). Hermes can also write skills after it finishes a task. |
| 7 | **Tools** | Connect email, calendar, to-do list, whatever you need. Only connect what it actually uses. |
| 8 | **Chat app** | Connect Telegram or WhatsApp (Discord, Slack and Signal work too), so you just text it: *"What's on my schedule today? Check my emails and prepare the replies."* |
| 9 | **Dashboard** | Add a dashboard or log so you can see what it's doing. |

## The 3 safety rules

1. **Never give it unrestricted access.** Give it its own accounts, or limited access to only what it needs. Never your main passwords.
2. **Set spending limits.** Turn on usage caps and billing alerts with your AI provider, so a loop can't burn through your credits overnight.
3. **Make it ask first.** Require your approval before it sends emails, spends money or deletes anything.

## A prompt to plan your setup (paste into Claude)

```
I want to set up a personal AI assistant with Hermes Agent.
Ask me 8 short questions about my business, goals, daily tasks and tools.
Then give me:
1. Where to run it (my computer or a cloud server) and why.
2. Which AI model to start with for my budget.
3. The first 3 skills to create, written out.
4. Which tools to connect first, with the minimum permissions each needs.
5. The approval rules: what it must always ask me before doing.
6. A monthly spending cap and where to set billing alerts.
Keep it simple, I'm not a developer.
```

## Next

- Want it cheap to run? See the [BILL](../BILL/) checklist (7 money leaks).
- Building apps too? See [DOORS](../DOORS/) (7 security checks).

Sources: [hermes-agent.org](https://hermes-agent.org/) · [Hermes Agent overview](https://landscape.jimmysong.io/projects/hermes-agent/)
