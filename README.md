# Ranelagh Village Dental — website redesign concept

A redesign proposal for [ranelaghvillagedental.ie](https://www.ranelaghvillagedental.ie), built with the practice's existing content, treatments, fees and opening hours.

> This is a design concept, not the official website. It is excluded from search engines (`noindex` + `robots.txt`).

## What's improved

- **Mobile first** — the current site is not mobile-friendly (no viewport, WordPress 4.6). This one has a sticky Call / Book / Directions bar, a full-screen menu and large tap targets.
- **Opening hours up front** — "open until 8pm on weekdays" is the practice's biggest advantage, so it's on the home page, with today's hours highlighted and a live "Open now / Closed now" status (Irish time).
- **Social proof** — the 4.8★ Google rating (122 reviews) is shown next to the main call to action.
- **Five clear pages** — Home, About Us, Treatments, Fees and Contact, matching the current site's structure.
- **Treatments with guide prices** — each treatment links to its fees; the home page cards deep-link to each treatment.
- **Searchable fee guide** with category filters, plus a "Ways to save" panel (free PRSI/medical card check-up, 20% back with Med 2).
- **Appointment request form** — opens the patient's email app with a ready-to-send request (name, phone, reason, preferred time). No server needed.
- **A more personal first impression** — the home page introduces the dentists with their existing team photo, shorter copy and a compact, expandable opening-hours panel.
- **Clear appointment steps** — “Open email draft” explains what happens next, with a validated “Copy request” fallback and an explicit reminder that reception confirms the appointment.
- **A lighter mobile layout** — compact benefit rows, a labelled menu, readable small-screen branding and improved primary-button contrast.
- **Getting here** — map, copy-address button, directions and the nearest Luas stop.
- **Accessible** — semantic HTML, skip link, keyboard-friendly menu (Esc to close), visible focus, reduced-motion support.

## Stack

Plain HTML, CSS and JavaScript (ES modules). No build step, no dependencies.

```
index.html        page shell
css/styles.css    design system and layout
js/data.js        all content: treatments, fees, hours, team, contact details
js/app.js         router (#/, #/about, #/treatments, #/fees, #/contact), pages and interactions
js/icons.js       inline SVG icons and logo mark
assets/           favicon and team photo
```

To change a price, an opening time or any text, edit `js/data.js` — every page reads from it.

## Run locally

```bash
npx http-server . -p 5173
```

Then open http://127.0.0.1:5173. (ES modules don't load from `file://`, so use a local server.)

## Deploy

Any static host works (Hostinger, GitHub Pages, Netlify): upload the files as they are. Routing uses `#/` URLs, so no server rewrite rules are needed.

Before going live as the official site, remove the `noindex` meta tag from `index.html`, replace `robots.txt`, and remove the "design concept" note in the footer (`js/app.js`).

## Content to confirm with the practice

- Fees come from the practice's current "Fees 2016" list and may need updating.
- The team photo is reused from the practice's existing About Us page: https://ranelaghvillagedental.ie/wp-content/uploads/2016/09/dentists.jpg. It is 350 × 225 pixels; request a current, higher-resolution original before an official launch. Individual profile cards still use initials.
