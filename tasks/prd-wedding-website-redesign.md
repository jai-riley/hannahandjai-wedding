# PRD: Wedding Website Redesign — Hannah Schlamp & Jai Riley

## 1. Introduction / Overview

The existing wedding website (originally built for a different couple) needs to be fully repurposed for Hannah Schlamp and Jai Riley's summer-camp-themed wedding weekend at Mulhurst Camp, Pigeon Lake, Alberta — June 11–13, 2027 (wedding ceremony June 12). The goal is to replace all content, imagery, and branding; redesign the visual style to feel rustic and camp-inspired; restructure the events section into a day-tabbed itinerary with a wedding party view vs. general guest view driven by RSVP invite codes; add a "Pack Your Bags" prep guide and a weekend menu section; and deploy via GitHub Pages.

---

## 2. Goals

- Replace all names, dates, images, and contact info with Hannah & Jai's confirmed details
- Establish a consistent summer camp visual identity (colors, typography, textures, icons)
- Replace the static two-column events layout with a tabbed, day-by-day itinerary
- Show a richer wedding party itinerary vs. a standard guest itinerary, gated by invite code
- Add a "Pack Your Bags" section (what to bring, dress code, camp expectations)
- Add a collapsible weekend menu section populated with confirmed catering details
- Remove the Instagram section entirely
- Deploy the site on GitHub Pages from the couple's own repository

---

## 3. User Stories

- **As a wedding guest**, I want to open the site and immediately feel the camp weekend vibe so I know what kind of event this is.
- **As a guest**, I want to browse the full weekend schedule by day so I can plan my travel and participation.
- **As a wedding party member**, I want to see my additional itinerary items (rehearsal, getting ready, etc.) that aren't shown to general guests.
- **As a guest**, I want to know what to pack and what the dress code is so I arrive prepared.
- **As a guest**, I want to see what meals are included so I can plan around dietary needs or preferences.
- **As a guest**, I want to RSVP easily from the site, indicating when I'm arriving and whether I'm staying overnight.
- **As a guest on mobile**, I want the site to be fully readable and usable on my phone.

---

## 4. Functional Requirements

### Content & Branding
1. All instances of the original couple's names must be replaced with **Hannah Schlamp & Jai Riley**.
2. Wedding date must be updated to **June 12, 2027**; weekend dates to **June 11–13, 2027**.
3. Venue must be updated to **Mulhurst Camp, Pigeon Lake, Alberta** with correct map embed.
4. All original placeholder images must be replaced with uploaded photos from Hannah and Jai (images to be provided later).
5. The site logo/header must reflect the new couple's names and camp aesthetic.
6. The Instagram section (`#instagram`) must be removed entirely from the HTML and CSS.
7. Social sharing buttons (Twitter, Facebook, Google+) in the invitation section must be removed.

### Visual / Theme
8. The color palette must be updated to a summer camp scheme: forest green, warm tan, terracotta, cream, and off-white.
9. Typography must be updated to a rustic/camp pairing: a hand-lettered or slab-serif display font for headings, and a clean readable font for body text (Google Fonts preferred for free licensing).
10. Section backgrounds must use subtle wood-grain or kraft-paper textures to reinforce the camp aesthetic.
11. Icons throughout the site must be swapped to camp-themed equivalents (e.g., tent, campfire, compass, canoe, pine tree) using Font Awesome or inline SVGs.
12. All UI changes must follow the CRAP design principles (Contrast, Repetition, Alignment, Proximity).

### Itinerary / Events Section
13. The events section must be replaced with a **tabbed day view**: three tabs labelled **"Friday June 11"**, **"Saturday June 12"**, **"Sunday June 13"**.
14. Within each day tab, events must be displayed as a vertical timeline of cards, ordered chronologically.
15. Each event card must show: time, event title, a camp-themed icon, and a short description.
16. Each event card must be **expandable on click** to reveal additional details (location, notes, dress code if applicable).
17. The itinerary must support **two tiers of content**:
    - **General guest view** — visible to all; shows shared events (meals, ceremony, reception, etc.)
    - **Wedding party view** — same as general, plus one additional Friday card for the **rehearsal dinner** (time and details TBD), unlocked when a wedding party invite code is entered at RSVP
18. The rehearsal dinner card must be visually distinguished (e.g., terracotta left-border or small "Wedding Party" badge) so party members can identify it at a glance.
19. The itinerary must be easy to update — new events should require only adding a new card block in HTML or a JS data entry.
20. The itinerary must be fully functional and readable on mobile.

### "Pack Your Bags" Section
21. A new section titled **"Pack Your Bags"** (or similar camp-themed title) must be added to the page.
22. This section must include at minimum: a packing list, dress code guidance, and general camp expectations/tips.
23. Content for this section will be provided by the couple; the developer should scaffold the layout with placeholder text.
24. The section should use a visually distinct layout (e.g., checklist-style with icons) to make it scannable.

### Menu Section
25. A **weekend menu section** must be added to the page as a collapsible accordion component.
26. The accordion must have one panel per meal, using the confirmed catering schedule:

| Meal | Date | Key Items |
|---|---|---|
| Friday Dinner | June 11 | Taco Bar: chicken yucatan (halal), ground beef (halal), soft corn tortillas (GF), hard shells, lettuce/onion/tomato, salsa, sour cream, shredded cheese, rice & beans, sweet corn niblets |
| Saturday Breakfast | June 12 | Assorted bagels, cream cheese, jams, assorted muffins (GF option), cinnamon buns, pastries, fresh fruit, yogurt, turkey sausage (GF), hard boiled eggs, coffee/tea/chai |
| Saturday Lunch | June 12 | Boxed Lunches: assorted sandwiches (turkey halal), fresh fruit, salad or chips, dessert squares |
| Saturday Cocktail Hour | June 12 | Large fruit platter, veggie & dip platter, spinach dip + second dip (TBD) |
| Saturday Dinner | June 12 | Dinner buns, seasonal vegetables (GF), strawberry spring salad (GF), potato salad no egg (GF), mashed potatoes (GF), grilled chicken breast with mushroom cream sauce (halal, GF), AAA roast beef with gravy & horseradish (GF, halal), coffee/tea/chai |
| Sunday Breakfast | June 13 | Pancakes with butter & syrup (GF option), scrambled eggs, turkey sausage (GF), fresh fruit, hashbrowns, coffee/tea/chai |

27. Each accordion panel must display the meal name and date as the header, and the item list when expanded.
28. Dietary labels (GF, Halal) must be shown inline with each item so guests with restrictions can quickly scan.
29. The section must stay within the single-page layout — no separate page required.

### RSVP — Attendance, Stay Options & Invite Codes
30. The RSVP form must include an **attendance tier selection** field (radio buttons) with three options:
    - **Full weekend** — arriving Friday June 11, staying Friday and Saturday night
    - **Saturday with overnight** — arriving Saturday June 12 for the wedding, staying Saturday night
    - **Wedding only** — attending the Saturday June 12 ceremony/reception, no overnight stay
31. Each option must include a short descriptor so guests understand what is included.
32. The form must include a **dietary restrictions / allergies** free-text field.
33. The RSVP form must accept **two distinct invite codes**:
    - A **general guest code** — standard access; records attendance tier, guest count, dietary info
    - A **wedding party code** — same as above, plus flags the guest as wedding party in the Google Sheet and unlocks the wedding party itinerary view on the site
34. When a wedding party code is entered and the RSVP is submitted, the site should store a flag client-side (e.g., `localStorage`) so the guest's itinerary view remains unlocked on return visits from the same browser.
35. The invite code field must remain on the form — it serves as both a spam gate and a tier selector.
36. The selected attendance tier, dietary field, and wedding party flag must all be submitted to the Google Sheet.

### Admin RSVP Dashboard
37. A separate `admin.html` page must be added to the site, accessible only by navigating directly to the URL (not linked from the main nav).
38. On load, `admin.html` must prompt for a password. If the password is incorrect, the dashboard content remains hidden.
39. The correct password must be stored as a hashed value in the JS (not plaintext) — use a simple SHA-256 hash check via the Web Crypto API.
40. Once unlocked, the dashboard must display:
    - Total RSVP count and headcount (number of guests including +1s)
    - Breakdown by attendance tier: Full Weekend / Saturday Overnight / Wedding Only
    - Count of wedding party RSVPs
    - A sortable/searchable guest table with columns: Name, Email, Attendance Tier, Guest Count, Dietary Restrictions, Wedding Party (Y/N)
    - A dietary restrictions summary — list all non-empty dietary entries so they're easy to scan
41. The dashboard must fetch RSVP data from the Google Sheet published as a public CSV endpoint (via File → Share → Publish to web → CSV format in Google Sheets).
42. The dashboard must show a "Last updated" timestamp based on when the data was fetched.
43. The admin page must not be linked from the main site nav — access is by direct URL only.
44. The dashboard must be mobile-readable (basic responsive layout).

### GitHub Hosting
45. The repository must be connected to **GitHub Pages** and configured to deploy from the `main` branch.
46. A `.nojekyll` file must be added to the repo root.
47. A `README.md` must document: how to run locally, how to deploy, and how to update content.
48. The site must be accessible at the GitHub Pages URL (custom domain setup is out of scope but must not be blocked by the implementation).

---

## 5. Non-Goals (Out of Scope)

- Custom domain setup (can be done later via GitHub Pages settings)
- Server-side authentication for wedding party code (client-side localStorage is acceptable for this use case)
- Dynamic CMS or database-driven content
- Instagram feed or any social media API integration
- Animations or interactive features beyond tab/accordion/expand interactions
- Custom illustrations (can be added later)
- Multi-language support
- "How We Met" story section (removed — not replaced)

---

## 6. Design Considerations

- **Typography suggestion:** [Amatic SC](https://fonts.google.com/specimen/Amatic+SC) or [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) for display headings; [Lato](https://fonts.google.com/specimen/Lato) or [Source Sans 3](https://fonts.google.com/specimen/Source+Sans+3) for body.
- **Color palette:**
  - Forest Green: `#2D4A2D`
  - Warm Tan: `#C8A96E`
  - Terracotta: `#C4623A`
  - Cream: `#F5EFE0`
  - Off-white: `#FAF7F2`
- **Texture:** Subtle SVG or CSS background patterns (avoid heavy image textures that slow load times).
- **Icons:** Font Awesome 6 free tier or Heroicons SVG set for camp-themed icons.
- **Responsive:** Bootstrap 3 is already in place — use its grid for itinerary cards and new sections.
- **Wedding party card styling:** Use a terracotta left-border or a small "Wedding Party" badge to distinguish those cards without cluttering the layout.

---

## 7. Technical Considerations

- The site is a **static single-page HTML site** — no build step beyond Gulp for Sass. Junior devs edit HTML and run `gulp` to recompile.
- The tab/itinerary component can use Bootstrap 3's `nav-tabs` + `tab-content` — no new JS dependencies needed.
- The accordion menu can use Bootstrap 3's `panel-group` / `collapse`.
- Wedding party itinerary unlock: store a flag in `localStorage` on successful RSVP with party code. On page load, JS checks for this flag and shows/hides party-only cards accordingly. Cards can have a `data-party="true"` attribute to make this easy to target.
- Images should be optimized before adding to `/img/` (aim for < 300KB per image).
- The Google Analytics UA ID in `index.html` should be updated or removed.
- The calendar event in `scripts.js` must be updated: title → "Hannah & Jai's Wedding", dates → June 12–13, 2027.
- Venue map embed: Mulhurst Camp is located on Pigeon Lake, AB — update Google Maps embed URL accordingly.

---

## 8. Success Metrics

- All original couple references (names, images, cultural ceremony descriptions) are gone from the live site.
- The site loads on GitHub Pages without errors.
- A guest can navigate all three days of the itinerary and read event details on both desktop and mobile.
- A wedding party member who enters the party code sees additional itinerary cards that a regular guest does not.
- The "Pack Your Bags" and menu sections are present, readable, and show correct catering items with dietary labels.
- The Instagram section is completely absent from the rendered page.
- The RSVP form submits successfully with all fields (including attendance tier and dietary info) appearing in the Google Sheet.
- The admin dashboard at `admin.html` is password-protected, loads RSVP data from the Sheet, and displays the guest list and attendance summary correctly.

---

## 9. Open Questions

1. What is the RSVP deadline? *(Placeholder: May 1, 2027)*
2. What contact name/number (if any) should appear on the site? *(Placeholder: "Questions? Email us at hannahandjai2027@gmail.com")*
3. Should the "Invitation" hero copy be written fresh by the couple, or should a placeholder be drafted? *(Placeholder copy drafted — to be replaced)*
4. Will there be a custom domain (e.g., `hannahandjai.com`)? Can configure in GitHub Pages settings post-launch.
5. What are the two invite codes? *(Placeholder: general → `CAMP2027`, wedding party → `PARTY2027` — must be changed before launch)*
6. Should the gallery section keep engagement photos, or be replaced with camp venue / inspiration photos? *(Placeholder: engagement photos until real images provided)*
7. What are the rehearsal dinner time and details? *(Placeholder card on Friday with "Time & details TBD")*
