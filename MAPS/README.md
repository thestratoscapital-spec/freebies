# 📍 MAPS: turn any Google Maps search into a spreadsheet (free and open source)

You commented **MAPS**. Here's **Google Maps Scraper**: a free, open-source tool that searches Google Maps for any kind of business in any city and saves the results to a spreadsheet. You get the name, phone, address, website, rating, reviews and opening hours, plus emails if you want them. It's by **gosom** on GitHub.

👉 **The link:** https://github.com/gosom/google-maps-scraper

Free (MIT licence). It runs on your own computer, with no account and no API key.

---

## Option 1: the web page (easiest)

1. Install **Docker Desktop** (free) and open it.
2. Paste this into your terminal:

```bash
mkdir -p gmapsdata
docker run -v "$PWD/gmapsdata:/gmapsdata" -p 8080:8080 gosom/google-maps-scraper -data-folder /gmapsdata
```

3. Open **http://localhost:8080** in your browser.
4. Type what you want, like `coffee shops in Austin`, and start the job.
5. When it's done, download the results as a CSV and open it in Excel or Google Sheets.

> ⏳ Results take at least **3 minutes** to show up, so don't close it early.

No Docker? The repo's **Releases** page also has a ready-made app for Windows, Mac and Linux.

---

## Option 2: let Claude Code run it

If you use Claude Code, install the skill (it needs **Docker** and **Node.js**):

```bash
npx skills add gosom/google-maps-scraper
```

Then just ask, for example:

```
Find gyms in Miami and include their websites and email addresses.
```

---

## Option 3: the command line (for lots of searches)

Put one search per line in a file called `queries.txt`:

```
car dealers in Houston
hair salons in Atlanta
gyms in Miami
```

Then run:

```bash
mkdir -p gmaps-output
docker run -v gmaps-playwright-cache:/opt -v "$PWD/queries.txt:/queries.txt:ro" -v "$PWD/gmaps-output:/out" gosom/google-maps-scraper -input /queries.txt -results /out/results.csv -depth 1 -email -exit-on-inactivity 3m
```

Your spreadsheet lands in `gmaps-output/results.csv`.

---

## Getting emails

Add **`-email`** on the command line (or ask for emails when you use Claude). It visits each business's website to look for a contact email.

- It only finds emails that the business **lists on its own website**, so some rows will be empty.
- It makes the job **a lot slower**.

---

## Good to know

- **Start small.** One niche in one city first. Big jobs can get blocked by Google; the README suggests proxies for large runs.
- **36 data points** per place are possible (name, category, address, phone, website, rating, review count, hours, coordinates and more). Not every business has every field filled in.
- **Use it responsibly.** In the author's words: *"use this scraper responsibly and in accordance with applicable laws and regulations."* Check Google's terms, and if you email people from your list, follow your local email rules (in the US that's CAN-SPAM).
- The README lists sponsors, mostly paid scraping and proxy services. You don't need any of them to use the tool.
- If it helps you, give the repo a ⭐.

---

*Follow Girmetheus for more AI tools.*
