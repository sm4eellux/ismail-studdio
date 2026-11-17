# APEX FITNESS — demo website (ISMAIL.STUDIO portfolio)

A fictional premium gym website: 6 pages, vanilla HTML/CSS/JS, optional GSAP. **All content (brand, prices, trainers, contact details) is fictional demo content.** No payment is processed.

## Structure
```
projects/fitness/
├── index.html · membership.html · programs.html · trainers.html · about.html · contact.html
├── css/   style.css (tokens + components) · animations.css · responsive.css
├── js/    config.js (contact, hours, plans, EmailJS) · main.js (header/footer, modal, reveal)
│          programs.js · trainers.js · membership.js · contact.js
└── assets/ images/fallback.svg · icons/favicon.svg
```
Header and footer are injected by `main.js` (edit links in one place). All paths are relative, so it works on GitHub Pages in a sub-folder.

## Edit the branding
Colours are CSS variables at the top of `css/style.css` (`--accent`, `--bg`, …). Fonts (Bebas Neue, Manrope, Inter) are loaded from Google Fonts in each page `<head>`. The logo text is in `js/main.js` (`.logo`).

## Replace images
Photos are Unsplash URLs. In `programs.js` and `trainers.js` the `img` field is an Unsplash photo ID; in the HTML pages the `src` is a full URL. To use your own files, put them in `assets/images/` and change the `src` (or change `window.U` in `main.js` to return `assets/images/<name>`). If any image fails to load, `assets/images/fallback.svg` is shown automatically.

## Add or edit programs
Copy an object in `PROGRAMS` (`js/programs.js`). `cat` creates the filter button automatically.

## Edit membership plans and prices
`plans` in `js/config.js` (name, price, features). Cards on the home and membership pages update automatically. The comparison table rows are in `js/membership.js` (`feats` / `has`).

## Edit trainer profiles
`TRAINERS` in `js/trainers.js`. Keep profiles clearly fictional.

## Contact info and WhatsApp
`js/config.js`: `contact`, `hours`, and `whatsappNumber` (international format, digits only, e.g. `212600000000`). Footer, contact page and WhatsApp links update everywhere.

## EmailJS
1. Create an EmailJS account, an email service and a template using the variables `name`, `email`, `phone`, `subject`, `message`.
2. Fill `emailjs.publicKey`, `serviceId`, `templateId` in `js/config.js`.
Until all three are set, the form does **not** claim to send: it validates, shows a summary and offers email and WhatsApp buttons instead.

## Deploy to GitHub Pages
Commit the folder inside the ISMAIL.STUDIO repo and push; with Pages enabled the demo is at `/projects/fitness/index.html`. The portfolio entry `fitness` in `js/projects.js` already points there via `liveUrl`.
