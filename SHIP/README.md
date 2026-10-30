# 🔒 SHIP: the 6 checks before you launch a vibe-coded app

You commented **SHIP**. Here's the full checklist from the video. Each check comes with **a prompt you can paste into Claude Code** (or any coding AI) so it checks your app for you.

> Run these **before** real users (or strangers) find your app. Fix what it finds, then run them again.

---

## 1. 🔑 API keys stay on the server

If a secret key is in your app's front-end code, anyone can open the browser's dev tools and copy it.

- Secret keys (OpenAI, Anthropic, Stripe **secret** key, database passwords) live **only on the server**, in environment variables.
- Watch the "public" prefixes: anything named `NEXT_PUBLIC_…` or `VITE_…` **gets shipped to the browser**. Never put a secret there.
- Keep `.env` out of git (it should be in `.gitignore`). If a key was ever pushed or shipped, **rotate it** (make a new one, delete the old one).

**Paste this:**
```
Search this whole project for secret keys, tokens and passwords. List every one that is hard-coded, sent to the browser
(front-end code, NEXT_PUBLIC_ or VITE_ variables), or committed to git. For each, show me how to move it to a server-side
environment variable and call it from the server instead. Don't print the key values themselves.
```

---

## 2. 🗄️ Turn on row level security (Supabase)

Your Supabase "anon" key is **meant** to be public: it's in your app. What protects your data is **Row Level Security (RLS)**. With RLS off, anyone with that key can read (or change) every row.

- Turn RLS on for **every** table in the `public` schema. Tables you make with SQL don't get it automatically.
- Add policies so users only see their own rows (for example `auth.uid() = user_id`).
- Supabase's **Security Advisor** (in the dashboard) flags tables with RLS off.

**Paste this:**
```
Look at my Supabase setup (migrations, SQL files and how the app queries the database). List every table and whether row
level security is on. For each table, write the SQL to enable RLS and policies so a signed-in user can only read and change
their own rows. Point out any table that should not be readable by the public at all.
```

---

## 3. 🚪 The server checks every request

Hiding a button isn't security. Anyone can call your API directly, without your app.

- On the **server**, every request checks **who is asking** (are they signed in?) and **if they're allowed** (is this their data? are they an admin?).
- Never trust an ID the browser sends, like `userId=123`. Take the user from their session on the server.

**Paste this:**
```
Go through every API route and server action in this project. For each one, tell me: does it check the user is signed in,
and does it check they're allowed to touch this specific data? Flag any route that trusts a user ID or role sent from the
browser, and any admin feature that is only hidden in the UI. Show me the fix for each.
```

---

## 4. 💳 Payments: confirm with Stripe, not the browser

The browser saying "paid" proves nothing. Someone can fake it in the console.

- Unlock the order **only** when your server gets Stripe's **webhook** (for example `checkout.session.completed`).
- **Verify the webhook signature** with your webhook signing secret, so nobody can send you a fake one.
- Set prices on the server. Never take the price from the browser.

**Paste this:**
```
Check how this app handles payments. Does anything unlock a purchase based on what the browser says (a success page, a
"paid" flag, a price sent from the client)? Make sure orders are only fulfilled from a Stripe webhook whose signature is
verified with the webhook signing secret, and that prices come from the server. Show me what to change.
```

---

## 5. 🚦 Rate-limit logins and anything that costs money

Without limits, one bot can guess passwords all night, or call your AI feature thousands of times and **you pay the bill**.

- Rate-limit: login, sign-up, password reset, and **every route that calls a paid API** (AI, email, SMS).
- Set a **spending limit / budget alert** in your AI provider's dashboard too.

**Paste this:**
```
List every route in this app that handles logins, sign-ups or password resets, or that calls a paid service (AI models,
email, SMS, image generation). Add rate limiting to each one (per user and per IP), using what fits my stack. Tell me which
routes could run up a big bill if a bot hit them in a loop.
```

---

## 6. 🕵️ Make Claude attack it

In **Claude Code**, type:

```
/security-review
```

It's built into Claude Code. It reviews **the changes on your current branch** and reports security holes with fixes.

To check the **whole app**, not just recent changes, paste this:
```
Act as an attacker trying to break into this app. Review the whole codebase for security holes: exposed secrets, missing
auth checks, database access without row level security, injection (SQL, prompt, XSS), unsafe file uploads, payment
bypasses and missing rate limits. Rank what you find by how bad it is, and give me the fix for each one.
```

---

## Good to know

- **AI review is a great first pass, not a guarantee.** It can miss things. For apps with payments or sensitive data, get a human to look too.
- **Fix, then re-run.** Ask Claude to check again after each fix.
- The **$2,400 AI bill** in the video is an **example** to show what can happen, not a real case.
- Don't paste real keys or customer data into a chat. The prompts above never need them.

---

*Follow Girmetheus for more AI tools.*
