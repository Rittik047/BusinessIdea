# The Metrology Dividend — Venture & Immigration Brief

## [Published Page](https://rittik047.github.io/BusinessIdea/)


A single-file, dependency-free static site. No build step, no framework, no npm install.
All charts are hand-written SVG + vanilla JS inside `index.html`.

---

## ⚠️ Read this before you push

**GitHub Pages sites are publicly readable — including sites published from a private repository
on the Free plan.** Private Pages requires GitHub Pro / Team / Enterprise.

This document currently contains:

| Item | Where |
|---|---|
| Your full name | Masthead, page title, footer |
| Cumulative GPA (3.804) | § 1 profile table |
| Nationality and visa posture | § 1, § 2 — including E-2 ineligibility |
| Capital available (“Under $5,000”) | § 1 profile table |
| A candid assessment of your O-1A file | § 7 Red Team |

None of that is catastrophic on its own. But an immigration strategy plus a frank
self-assessment is not something most people want indexed and permanently archived
against their name. Three options:

1. **Ship as-is.** `noindex, nofollow, noarchive` is already set in `<head>` and in
   `robots.txt`. Compliant crawlers will skip it; the URL is still reachable by anyone
   who has it. Fine for sharing a link with advisors, mentors, or an attorney.
2. **Publish at an unguessable path.** Put it in a repo with a random name
   (`git init metrology-9f3a2c`), so the URL is effectively a secret link.
3. **Ask me for a redacted build.** I can strip the name, GPA, nationality and capital
   figures and republish it as an anonymous market brief — which is the version you
   would actually want in a portfolio.

---

## Deploy — the two-minute path

```bash
# 1. Create the repo locally
cd venture-brief-site
git init -b main
git add -A
git commit -m "Venture and immigration brief"

# 2. Create an empty repo on GitHub, then:
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then on GitHub: **Settings → Pages → Build and deployment → Source: `Deploy from a branch`
→ Branch: `main` / `(root)` → Save.**

Live in 30–90 seconds at:

```
https://<your-username>.github.io/<repo-name>/
```

If you name the repo exactly `<your-username>.github.io`, it serves from the bare domain
`https://<your-username>.github.io/` instead.

---

## Deploy — the Actions path (optional)

`.github/workflows/deploy.yml` is included if you prefer the Actions runner over branch
deployment. It does the same thing with more logging. To use it, set
**Settings → Pages → Source: `GitHub Actions`** instead of `Deploy from a branch`.
You do not need both. Delete the workflow file if you use branch deployment.

---

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire report. Self-contained — SVG charts, CSS and JS all inline. |
| `.nojekyll` | Stops GitHub's Jekyll processor from touching the files. Harmless but correct. |
| `robots.txt` | Asks crawlers not to index. Advisory only, not access control. |
| `404.html` | Styled not-found page matching the report. |
| `.github/workflows/deploy.yml` | Optional Actions-based deployment. |

---

## Custom domain

Add a `CNAME` file containing one line (`brief.yourdomain.com`), point a DNS `CNAME`
record at `<your-username>.github.io`, then set the domain under Settings → Pages and
tick **Enforce HTTPS** once the certificate provisions.

---

## Editing

Open `index.html` and search for the data arrays near the bottom — `TL`, `PATHS`, `HEAT`,
`DONUTS`, `SEG`, `SCAT`, `NAICS`, `MKT`, `BIZ`, `ADJ`, `HOR`, `PHASES`, `SCEN`, `SRC`.
Every chart and table renders from those; nothing is hard-coded in markup. Change a
number in `BIZ` and the tier table, the weighted ranking bars and the sort order all
update together.

The colour system lives in `:root` at the top:
`--paper #F3EFE3` · `--ink #0A1D2C` · `--lime #C8F23F` · `--coral #E16641` ·
`--teal #1B5E78` · `--amber #F3B82A` · `--plum #4A2950`.

---

## External dependencies

Exactly one: Google Fonts (Instrument Serif, IBM Plex Mono, Inter), loaded async with a
`noscript` fallback. If it fails or you are offline, the page falls back to Georgia,
system monospace and system sans — the layout does not break. To make the site fully
self-contained, self-host the woff2 files and swap the `<link>` for an `@font-face` block.

## Browser support

Safari 15+, Chrome 105+, Firefox 110+ — the layout uses `clamp()`, `min()`/`max()`,
`repeat(auto-fit, minmax())` and `width: fit-content`. Prints and exports to PDF cleanly
via a dedicated `@media print` block.

---

*Not legal, tax, or investment advice. Verify every regulatory claim with licensed counsel.*
