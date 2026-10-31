# 🧱 BUILD: 10 free GitHub repos you can build a product on (and their licenses)

You commented **BUILD**. Here are all 10 open-source projects from the video, what each one does, and the license I found when I checked each repo.

**The short version:** 8 are **MIT** or **Apache 2.0**, so you can use them in a product you sell. 2 are **AGPL**: if you run your changed version online for other people, you have to share your code.

---

## The 10 repos

| # | Repo | What it does | License |
|---|---|---|---|
| 1 | [**Morphic**](https://github.com/miurla/morphic) | Your own AI search engine: it searches the web and writes the answer | ✅ Apache 2.0 |
| 2 | [**Moonshine**](https://github.com/moonshine-ai/moonshine) | Fast speech-to-text that runs on the device, no internet needed | ✅ MIT* |
| 3 | [**Unstract**](https://github.com/Zipstack/unstract) | Pulls the data out of invoices, receipts and PDFs into clean fields | ⚠️ AGPL-3.0 |
| 4 | [**Puck**](https://github.com/puckeditor/puck) | A drag-and-drop page editor for React apps | ✅ MIT |
| 5 | [**pdfme**](https://github.com/pdfme/pdfme) | Design a PDF template once, then fill it with code | ✅ MIT |
| 6 | [**DocETL**](https://github.com/ucbepic/docetl) | Lets AI work through large piles of documents and pull out what matters | ✅ MIT |
| 7 | [**assistant-ui**](https://github.com/assistant-ui/assistant-ui) | A ready-made chat window for your AI app (React) | ✅ MIT |
| 8 | [**OpnForm**](https://github.com/OpnForm/OpnForm) | Your own form builder | ⚠️ AGPL-3.0** |
| 9 | [**LitServe**](https://github.com/Lightning-AI/LitServe) | Turns your AI model into an API that other apps can call | ✅ Apache 2.0 |
| 10 | [**next-forge**](https://github.com/vercel/next-forge) | A full SaaS starter by Vercel, with login, payments and a database already wired in | ✅ MIT |

\* **Moonshine:** the code and the main models are MIT. A few older non-English models are under a non-commercial license, and the text-to-speech files have their own licenses. The repo's LICENSE file lists them.
\*\* **OpnForm:** most of it is AGPL-3.0. One "Enterprise" folder has its own separate license.

Licenses checked on October 31, 2026. Projects can change their license, so look at the `LICENSE` file again before you launch.

---

## What the licenses mean (in plain words)

- **MIT / Apache 2.0:** you can use, change and sell what you build. Keep the original copyright and license notice in your project.
- **AGPL-3.0:** you can use it and charge for your product, but if people use your changed version **over the internet**, you must make your source code available to them under the same license.

This isn't legal advice. If you're building a real business on one of these, read the license or ask a lawyer.

---

## Check a license yourself with Claude Code

Paste this into Claude Code (swap in the repo you want):

```
Clone github.com/miurla/morphic, read its LICENSE file, and tell me in plain English
whether I can use it in a product I sell, and what I have to do if I do.
```

Then ask it to help you build:

```
Look through this repo and suggest 3 simple products I could build on top of it,
for one specific niche. Keep each idea to a few sentences.
```

---

## Good to know

- **Start with one.** Pick the repo closest to an idea you already have, and get it running first.
- **Setups differ.** Each repo's README has its own install steps. Some need accounts with other services (next-forge uses things like Clerk and Stripe, for example).
- **Credit the authors.** These are other people's projects. If one helps you, give it a ⭐ on GitHub.
- The examples in the video (the search answer, the invoice, the form) are sample data I made up to show what each tool does.

---

*Follow Girmetheus for more AI tools.*
