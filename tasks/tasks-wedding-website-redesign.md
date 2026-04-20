# Tasks: Wedding Website Redesign — Hannah Schlamp & Jai Riley

## Relevant Files

- `wedding-website/index.html` - Main single-page site; all content, structure, and sections live here
- `wedding-website/sass/styles.scss` - Source stylesheet; all theme changes go here
- `wedding-website/css/styles.min.css` - Compiled output from Sass (regenerated via `gulp`)
- `wedding-website/js/scripts.js` - Main JS; calendar event, RSVP logic, social sharing, party unlock logic
- `wedding-website/js/scripts.min.js` - Minified JS output (regenerated via `gulp`)
- `wedding-website/img/` - All site images (hero, story, gallery, etc.)
- `wedding-website/img/eng_pics/` - Couple photo gallery
- `wedding-website/gulpfile.js` - Build config for Sass + JS compilation
- `wedding-website/package.json` - Node dependencies
- `wedding-website/admin.html` - Password-protected RSVP dashboard for Hannah & Jai (to be created)
- `README.md` - GitHub Pages setup documentation (to be created)
- `.nojekyll` - Required for GitHub Pages to serve the site correctly (to be created)

### Notes

- Run `npm install` then `gulp` from `/wedding-website/` to recompile Sass and JS after changes.
- All Sass changes must be made in `styles.scss` — do not edit `styles.min.css` directly.
- Google Fonts can be added via a `<link>` tag in the `<head>` of `index.html`.
- The Google Apps Script RSVP endpoint URL is already wired in `scripts.js` — only form fields and Sheet column mappings need to change.
- Wedding party itinerary unlock works via `localStorage`: when a party code RSVP is submitted, set a flag like `localStorage.setItem('weddingParty', 'true')`. On page load, JS reads this flag and shows cards with `data-party="true"`.

---

## Instructions for Completing Tasks

**IMPORTANT:** As you complete each task, check it off by changing `- [ ]` to `- [x]`. Update after each sub-task, not just each parent task.

---

## Tasks

- [ ] 0.0 Set up GitHub repository and Pages hosting
  - [ ] 0.1 Create a new GitHub repository under Jai's account (e.g., `hannahandjai-wedding`)
  - [ ] 0.2 Push the existing local codebase to the new repo's `main` branch
  - [ ] 0.3 Add a `.nojekyll` file to the repo root so GitHub Pages serves static assets correctly
  - [ ] 0.4 Enable GitHub Pages in repo Settings → Pages → Source: `main` branch, root folder
  - [ ] 0.5 Confirm the site loads at `https://<username>.github.io/hannahandjai-wedding/`
  - [ ] 0.6 Create a `README.md` documenting: how to run locally, how to deploy, and how to update itinerary content

- [ ] 1.0 Replace all content (names, dates, copy, contact info)
  - [ ] 1.1 Find and replace all instances of the original couple's names in `index.html` with "Hannah Schlamp & Jai Riley"
  - [ ] 1.2 Update `<title>` and all meta tags (description, og:title, og:description)
  - [ ] 1.3 Update hero section heading and subheading: names + "June 12, 2027 · Mulhurst Camp, Pigeon Lake, AB"
  - [ ] 1.4 Update invitation section copy (use placeholder if final copy not yet written)
  - [ ] 1.5 Remove the "How We Met" / story section (`#intro`) from `index.html` entirely
  - [ ] 1.6 Remove the Instagram section (`#instagram`) from `index.html` entirely
  - [ ] 1.7 Remove social sharing buttons (Twitter, Facebook, Google+) from invitation section in `index.html` and `scripts.js`
  - [ ] 1.8 Update venue section: name → "Mulhurst Camp", location → "Pigeon Lake, Alberta"; update Google Maps embed URL
  - [ ] 1.9 Update contact info in the venue/map section (placeholder: "Questions? Email hannahandjai2027@gmail.com")
  - [ ] 1.10 Update calendar event in `scripts.js`: title → "Hannah & Jai's Wedding", start → June 12 2027, end → June 13 2027
  - [ ] 1.11 Update or remove the Google Analytics UA ID in `index.html`
  - [ ] 1.12 Update RSVP deadline text in the RSVP section (placeholder: "Please RSVP by May 1, 2027")

- [ ] 2.0 Apply summer camp visual theme (colors, fonts, textures, icons)
  - [ ] 2.1 Add Google Fonts `<link>` to `index.html` `<head>` — load display font (Amatic SC or Playfair Display) and body font (Lato)
  - [ ] 2.2 In `styles.scss`, define Sass variables for the camp palette: Forest Green `#2D4A2D`, Warm Tan `#C8A96E`, Terracotta `#C4623A`, Cream `#F5EFE0`, Off-white `#FAF7F2`
  - [ ] 2.3 Apply new color variables to replace original accent colors, backgrounds, and button styles throughout `styles.scss`
  - [ ] 2.4 Update heading font-family to the new display font in `styles.scss`
  - [ ] 2.5 Update body font-family to the new body font in `styles.scss`
  - [ ] 2.6 Add subtle texture to section backgrounds (CSS pattern or lightweight SVG) on alternating sections in `styles.scss`
  - [ ] 2.7 Replace existing section icons in `index.html` with camp-themed Font Awesome icons (e.g., `fa-tree`, `fa-fire`, `fa-map-marker`, `fa-cutlery`)
  - [ ] 2.8 Update site logo/header text styling in `styles.scss` to use display font and camp color
  - [ ] 2.9 Run `gulp` to recompile Sass and verify no compilation errors
  - [ ] 2.10 Review site in browser — check Contrast, Repetition, Alignment, Proximity (CRAP) across all visible sections

- [ ] 3.0 Rebuild events section as tabbed day-by-day itinerary
  - [ ] 3.1 Remove the existing two-column static events HTML from `index.html` (`#events` section)
  - [ ] 3.2 Add Bootstrap 3 tab markup (`nav-tabs` + `tab-content`) with three tabs: "Friday June 11", "Saturday June 12", "Sunday June 13"
  - [ ] 3.3 Within each tab panel, create a vertical timeline of event cards (`<div>` list ordered by time)
  - [ ] 3.4 Each event card must include: time slot, event title, a camp-themed icon, and a short description paragraph
  - [ ] 3.5 Make each event card expandable on click using Bootstrap 3 `collapse` (toggle description on click)
  - [ ] 3.6 Add a single wedding party-only card to the Friday tab for the rehearsal dinner — add `data-party="true"` attribute; hide it by default with CSS (`display: none`); placeholder text: "Rehearsal Dinner · Time & details TBD"
  - [ ] 3.7 In `scripts.js`, add page-load logic: if `localStorage.getItem('weddingParty') === 'true'`, add class `party-unlocked` to `<body>`, which shows `[data-party="true"]` cards via CSS
  - [ ] 3.8 Style the rehearsal dinner card with a terracotta left-border and small "Wedding Party" badge in `styles.scss`
  - [ ] 3.9 Populate Friday tab: arrival window (placeholder: "3:00 PM — Arrive & check in"), taco bar dinner (placeholder: "6:30 PM — Taco Bar Dinner"), rehearsal dinner party card (hidden by default)
  - [ ] 3.10 Populate Saturday tab: breakfast ("8:30 AM"), boxed lunch ("12:00 PM"), cocktail hour ("4:00 PM"), ceremony (placeholder: "5:00 PM — Ceremony · time TBD"), dinner reception ("6:30 PM")
  - [ ] 3.11 Populate Sunday tab: pancake breakfast ("9:00 AM"), checkout/farewell (placeholder: "11:00 AM — Check out & farewell")
  - [ ] 3.12 Style the tab nav and event cards in `styles.scss` to match the camp theme — earthy colors, readable on mobile
  - [ ] 3.13 Test tab switching and card expand/collapse on both desktop and mobile viewport sizes

- [ ] 4.0 Add "Pack Your Bags" and Menu sections
  - [ ] 4.1 Add a new `#pack-your-bags` section to `index.html` after the itinerary section
  - [ ] 4.2 Add section heading ("Pack Your Bags") and a short intro paragraph (placeholder copy)
  - [ ] 4.3 Add checklist-style packing list with icons — placeholder items: bug spray, sunscreen, layers, rain jacket, comfortable shoes, swimsuit, reusable water bottle
  - [ ] 4.4 Add dress code subsection with placeholder guidance (e.g., "Camp casual — think flannel, denim, and your dancing boots")
  - [ ] 4.5 Add "Good to Know" tips subsection with 3–5 placeholder camp expectation notes
  - [ ] 4.6 Style the section in `styles.scss` — distinct background, scannable layout with icons and clear grouping
  - [ ] 4.7 Add a new `#menu` section to `index.html` after Pack Your Bags
  - [ ] 4.8 Add section heading ("Weekend Menu") and short intro line
  - [ ] 4.9 Build menu as Bootstrap 3 accordion (`panel-group` + `collapse`) with six panels:
        - Friday Dinner (June 11) — Taco Bar
        - Saturday Breakfast (June 12)
        - Saturday Lunch (June 12) — Boxed Lunches
        - Saturday Cocktail Hour (June 12)
        - Saturday Dinner (June 12)
        - Sunday Breakfast (June 13)
  - [ ] 4.10 Populate each accordion panel with catering items from the confirmed quote, displaying GF and Halal labels inline (e.g., "Chicken Yucatan · Halal", "Soft Corn Tortillas · GF")
  - [ ] 4.11 Style the accordion in `styles.scss` to match the camp theme
  - [ ] 4.12 Add both `#pack-your-bags` and `#menu` links to the site nav `<nav>`

- [ ] 5.0 Update RSVP form (attendance tiers, dietary field, invite codes, Google Sheet)
  - [ ] 5.1 Add styled radio button group to the RSVP form with three attendance options:
        - "Full weekend (Friday June 11 arrival — staying Fri & Sat night)"
        - "Saturday with overnight (arriving June 12 — staying Sat night)"
        - "Wedding only (Saturday June 12 ceremony & reception — no overnight)"
  - [ ] 5.2 Add a textarea field labelled "Dietary restrictions or allergies" to the RSVP form
  - [ ] 5.3 Update all form field labels and placeholder text to remove original couple references
  - [ ] 5.4 Keep the invite code field; update validation in `scripts.js` to accept two valid codes: general guest `CAMP2027` and wedding party `PARTY2027` (placeholders — must be changed before launch)
  - [ ] 5.5 In `scripts.js`, when the wedding party code is submitted successfully, set `localStorage.setItem('weddingParty', 'true')` so the itinerary unlock persists across page loads
  - [ ] 5.6 Update the Google Apps Script spreadsheet to add columns: "Attendance Tier", "Dietary Restrictions", "Wedding Party" (Y/N)
  - [ ] 5.7 Update the form POST payload in `scripts.js` to include the three new fields
  - [ ] 5.8 Test the RSVP form end-to-end with both codes — confirm all fields appear correctly in the Google Sheet and the wedding party flag triggers the itinerary unlock
  - [ ] 5.9 Style the new form fields in `styles.scss` to match the camp theme and existing form layout

- [ ] 6.0 Swap in couple's photos and remove placeholder imagery
- [ ] 7.0 Build password-protected admin RSVP dashboard
  - [ ] 6.1 Delete all original couple images from `wedding-website/img/` and `wedding-website/img/eng_pics/`
  - [ ] 6.2 Optimize and add Hannah & Jai's hero image to `img/` — target < 300KB, name it `hero.jpg`
  - [ ] 6.3 Update hero background image reference in `index.html` or `styles.scss` to point to the new hero image
  - [ ] 6.4 Add couple photos for the gallery to `img/eng_pics/` — provide both `-sm` (thumbnail) and `-lg` (full) versions for each
  - [ ] 6.5 Update gallery `<a>` and `<img>` tags in `index.html` to reference new photo filenames
  - [ ] 6.6 Remove `img/iphone_instagram.jpg` (Instagram section is deleted)
  - [ ] 6.7 Update the site logo/favicon if a custom one is provided; otherwise update the text-based logo in the nav
  - [ ] 6.8 Final browser pass — confirm no broken image links, no original couple references remain, full page renders correctly on mobile and desktop

- [ ] 7.0 Build password-protected admin RSVP dashboard
  - [ ] 7.1 Create `wedding-website/admin.html` — standalone page, not linked from the main site nav
  - [ ] 7.2 Add a password prompt overlay that covers the page content on load; hide the dashboard until correct password is entered
  - [ ] 7.3 Store the admin password as a SHA-256 hash in the page JS (use the Web Crypto API for hashing — no plaintext passwords in source code); placeholder password: `WeddingAdmin2027` (change before launch)
  - [ ] 7.4 In Google Sheets, publish the RSVP sheet as a public CSV: File → Share → Publish to web → select the RSVP sheet → CSV format → copy the URL
  - [ ] 7.5 In `admin.html`, use `fetch()` to load the published CSV URL on unlock, then parse it into a JS array of guest objects
  - [ ] 7.6 Display a summary stats bar at the top: total RSVPs, total headcount, breakdown by attendance tier (Full Weekend / Saturday Overnight / Wedding Only), wedding party count
  - [ ] 7.7 Display a dietary restrictions summary section — list all non-empty dietary entries as a simple bulleted list for easy catering reference
  - [ ] 7.8 Display a full guest table with columns: Name, Email, Attendance Tier, Guest Count, Dietary Restrictions, Wedding Party (Y/N)
  - [ ] 7.9 Add a basic text filter input above the table so the list can be searched by name
  - [ ] 7.10 Show a "Last fetched" timestamp below the summary stats
  - [ ] 7.11 Add a "Refresh" button that re-fetches the CSV and updates the view without a full page reload
  - [ ] 7.12 Style `admin.html` to match the camp theme (reuse the same Google Fonts and color palette) — keep it clean and functional
  - [ ] 7.13 Test with a few dummy RSVP entries in the Sheet — verify all fields display correctly and the dietary summary populates
  - [ ] 7.14 Confirm the page is inaccessible (content hidden) without the correct password, and that the URL is not discoverable from the main site
