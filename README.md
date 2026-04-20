# Hannah & Jai's Wedding Website

Wedding weekend June 11–13, 2027 · Mulhurst Camp, Pigeon Lake, Alberta

Live site: https://jai-riley.github.io/hannahandjai-wedding/

---

## Running Locally

```bash
npm install
gulp
```

Then open `index.html` in your browser.

## Deploying

Push to the `main` branch — GitHub Pages deploys automatically from the repo root.

```bash
git add .
git commit -m "your message"
git push origin main
```

## Updating Content

| What | Where |
|---|---|
| Names, dates, copy | `index.html` |
| Itinerary events | `index.html` — `#events` section; add a new card block per event |
| Menu items | `index.html` — `#menu` accordion panels |
| Pack Your Bags content | `index.html` — `#pack-your-bags` section |
| Styles / theme | `sass/styles.scss` — run `gulp` after changes |
| RSVP logic & invite codes | `js/scripts.js` |
| Photos | `img/` (hero) and `img/eng_pics/` (gallery) |
| Admin dashboard | `admin.html` — update the published Google Sheet CSV URL if the sheet changes |

## Invite Codes

Two codes are accepted at RSVP:
- **General guests** — set in `js/scripts.js` (placeholder: `CAMP2027`)
- **Wedding party** — set in `js/scripts.js` (placeholder: `PARTY2027`) — unlocks rehearsal dinner on the itinerary

**Change both codes before the site goes live.**

## Admin Dashboard

Navigate directly to `/admin.html` — not linked from the main site. Password is stored as a SHA-256 hash in `admin.html`. Placeholder password: `WeddingAdmin2027` — change before launch.
