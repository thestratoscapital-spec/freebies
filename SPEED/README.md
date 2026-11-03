# ⚡ SPEED: make your vibe-coded app fast on real phones

You commented **SPEED**. Your app can feel instant on your laptop and still crawl on your customers' phones, because a powerful laptop, fast Wi-Fi and cached files hide the slow parts. Here's the full checklist from the video, with a prompt for each step that you can paste into Claude (Claude Code, or the Claude app with your code attached).

**Work in this order:** measure → fix → measure again. Change one thing at a time so you know what helped.

---

## 1 · Test it like a real user

```
Test my app as if it were running on a slow phone and network.
Find what makes the first screen take too long to appear.
List the biggest causes first, with the file and line for each.
```

**Do it yourself too:** in Chrome DevTools, open the Network tab and pick a slow network preset, set the CPU to a slower setting in the Performance tab, and turn on "Disable cache". Then reload and watch the first screen. Lighthouse (in DevTools) gives you a score and a list of what to fix.

## 2 · Make the first screen fast

```
Make my app's first screen appear faster:
1. Add skeleton loading screens where content is still loading.
2. Convert images to WebP or AVIF and size them for the screen they're shown on.
3. Lazy-load images and sections the user can't see yet.
Show me the before and after file sizes for the images.
```

- **Skeleton screens:** grey placeholder shapes, so the page looks ready while data loads.
- **WebP / AVIF:** modern image formats that are usually much smaller than PNG or JPEG.
- **Lazy-load:** only load what's below the fold when the user scrolls to it.

## 3 · Stop wasted requests

```
Find wasted network requests in my app:
1. The same API call made more than once for the same data.
2. Search or filter inputs that send a request on every keystroke (add debouncing).
3. Requests that wait for each other but don't need to (run them at the same time).
Fix them and tell me how many requests the first screen makes before and after.
```

## 4 · Paginate big lists

```
Find any place where my app downloads a large list all at once.
Add pagination or infinite scroll so it loads one page at a time.
```

## 5 · Fix the backend

```
Inspect my backend for:
1. Slow database queries (show me the slowest ones).
2. Missing indexes on columns I filter or sort by.
3. N+1 problems (one query per item in a list).
4. Data that rarely changes and should be cached.
Explain each fix in plain English before you make it.
```

## 6 · Measure every change

```
Before you change anything, measure how long my first screen takes on a slow phone
and network. After each fix, measure again and keep a small table of the results.
```

---

## Good to know

- **Your laptop isn't your user.** Always test on a slow network and, if you can, a cheap real phone.
- **Check the fixes.** Read what Claude changes, run the app, and keep a backup (commit before each change).
- The numbers in the video (like 4.8 s → 1.2 s) are sample numbers to show the idea, not a measured result.

---

*Follow Girmetheus for more AI tools.*
