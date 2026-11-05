# DOORS: the 7-door security check for your AI-built app

From the video *"Someone changes one number in your URL… and sees another customer's invoice."*

Your app has seven doors. Paste the prompt below into **Claude Code** (opened in your project folder) and it will check each one, tell you what's open, and help you lock it.

## The prompt

```
You are a careful security reviewer. Check this codebase for the 7 doors below.
For each door: say OPEN, LOCKED or NOT USED, point to the exact files and lines,
and explain the risk in one plain sentence. Don't change any code yet.

1. URLs / IDs: can a logged-in user load another user's record by changing an ID
   in the URL or request (e.g. /invoice/41 -> /invoice/42)? Every lookup must
   check that the record belongs to the current user (or their team).
2. Admin pages: are admin routes and actions checked ON THE SERVER, not just
   hidden in the UI? Try to find any admin endpoint with no role check.
3. Password resets: do reset tokens expire (15-60 min), work only once, get
   invalidated after use, and come from a secure random generator?
4. File uploads: are type (by content, not just extension), size and count
   checked on the server? Are files stored outside the app's code folder and
   never executed or served with a dangerous content type?
5. API: does every API route that returns private data require login AND check
   permissions? List any route that answers without a session.
6. Packages: run `npm audit` (or the equivalent for this stack) and list high
   and critical issues with the safe version to update to.
7. Login cookies: are session cookies HttpOnly, Secure, and SameSite=Lax or
   Strict? Do sessions expire and get cleared on logout?

End with a table: door, status, risk (high/medium/low), fix in one line.
Then ask me which ones to fix first.
```

## Then

- Fix one door at a time, highest risk first. Ask Claude to **write a test** for each fix (for example, "user A requests user B's invoice and gets 404").
- Re-run the prompt after the fixes.
- Using **Supabase**? Also check that **Row Level Security** is on for every table.

## Good to know

- This is a first pass, not a full security audit. For apps handling payments, health or other sensitive data, get a professional review too.
- Only test apps you own.

Missed part one? The 6-point pre-launch checklist is at [SHIP](../SHIP/).
