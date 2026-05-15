# td.gemax.online

Marketing site + legal pages for **GeMax TD** (cyberpunk netrunner tower defense). Hosted as a static site on GitHub Pages at `td.gemax.online`.

## Layout

```
.
├── index.html         landing page (hero, features, gameplay, screenshots, monetization, FAQ)
├── privacy.html       privacy policy (GDPR / CCPA / COPPA covered)
├── terms.html         terms of service (license, IAP, subscriptions, refunds, dispute resolution)
├── support.html       support page (contact, common issues, refund pointers)
├── 404.html           branded 404
├── styles.css         shared styles
├── robots.txt
├── sitemap.xml
├── CNAME              custom-domain config for GitHub Pages
├── .nojekyll          disable Jekyll processing
└── assets/            brand assets copied from the game repo
```

## Deploy

1. Commit and push to the `main` branch of `renanborgez/td.gemax.online`.
2. In repo settings → Pages, set source = `main` branch, root.
3. The `CNAME` file pins the domain. Configure DNS (CNAME `td` → `renanborgez.github.io`) on the registrar of `gemax.online`.
4. Enable "Enforce HTTPS" once the cert is issued.

No build step. Edit files, push, done.

## Brand assets

Source SVGs live in the game repo (`tower-gemax/assets/logo-mark.svg`, `logo.svg`). When the SVG changes, re-run `npm run gen:icons` in that repo, then copy the updated PNGs into this repo's `assets/`.

## Screenshots

`index.html` has placeholder frames for six screenshots. Drop captures into `assets/screenshots/`, then in `index.html` swap each `<div class="shot-frame" data-label="...">` for `<img src="assets/screenshots/01-title.png" alt="..." />`. Recommended portrait aspect ratio is 9:19.5 (matches the existing frame). The CSS auto-hides the placeholder label once the `<img>` is present.

## Email alias referenced

- `contact@gemax.online` — all enquiries (support, privacy, legal)

Set this up on the `gemax.online` domain (or alias to a real inbox) before linking the site from app-store listings.

## App store reviewer notes

The privacy policy and terms cover:

- Ads (rewarded video opt-in, interstitial; ATT prompt on iOS, ad-ID controls on Android)
- IAP (generic — specific items disclosed in-app at point of purchase)
- Subscriptions (generic auto-renew terms, cancellation paths, free-trial conversion)
- Children (general audience, not directed at <13)
- GDPR / CCPA rights and contact channel
- Refund routing (Apple / Google) plus EU right-of-withdrawal escape hatch

The contact email and the company / governing-law placeholders may need to be tightened before submission depending on the legal entity used.
