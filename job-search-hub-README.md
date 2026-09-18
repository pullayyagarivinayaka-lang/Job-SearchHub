# Job in One Click — Live Search Hub 🔎

Search real jobs, everywhere, from one box.

A lightweight companion site to Job in One Click. Type a role and location once, and it opens correctly-filtered, **live** searches on real job platforms (LinkedIn, Indeed, Naukri, Glassdoor, Internshala, Shine) in new tabs — plus a short list of verified openings found via web search. Nothing here is sample data, and no application is ever submitted from this page; every button just navigates you to that platform's own real search or listing.

## Why it works this way (and not as a live aggregator)
Browsers correctly block a webpage from silently fetching another site's job data on your behalf — that's what stops large-scale scraping/abuse, and it's not something this hub tries to work around. So instead of faking a unified results feed, it builds the exact search URL each platform already supports and lets you open it yourself, one click per platform. You always end up applying on the real, official site.

## Run it
No build tools needed.
```
git clone <this-repo>
cd job-search-hub
# open index.html directly, or serve locally:
python3 -m http.server 8000
```
Then visit `http://localhost:8000`.

## Deploy free (GitHub Pages)
1. Push `index.html` to a GitHub repo.
2. Repo → **Settings → Pages → Source: main branch, / (root)**.
3. Your live URL appears at `https://<username>.github.io/<repo>/`.

## Deploy free (Vercel)
```
npm install -g vercel
cd job-search-hub
vercel
```
No build command or output directory needed — it's a static file.

## Files
- `index.html` — the entire hub: markup, styles, and the URL-building script, all in one self-contained file

## How the search URLs are built
Each platform button reads your keyword + location and constructs that platform's own known search-URL pattern (e.g. `naukri.com/{keyword}-jobs-in-{city}`, `linkedin.com/jobs/search/?keywords=...&location=...`). These patterns are inferred from each site's public URL structure, not an official API — if a platform changes its URL format, that one button may need updating; the "Browse by platform" and "Verified openings" sections below it will still work regardless, since those are plain static links.

## Honest limitations
- **No live job data is fetched or displayed from this page** — it only launches searches on other sites. Anyone claiming to show you "all jobs in one place" without doing this is either connected to a real paid job-data API, or not being straight with you about where the listings come from.
- **The "Verified openings" list is a snapshot** from the day this was built, not a live feed — links may go stale as those postings close. Re-run a web search (or ask an AI assistant with search access) for fresh ones periodically.
- **Not affiliated** with LinkedIn, Naukri, Indeed, Glassdoor, Internshala, Shine, IBM, ServiceNow, or SSC — all trademarks belong to their respective owners; this is just a personal search-launcher pointing at their public sites.

## License
MIT — do anything you like with it.

---
Made with ❤️ by **Pullayyagari Vinayaka**
