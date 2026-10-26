# David Iradukunda — Portfolio

Personal site for **David Iradukunda**, systems and network administrator (Microsoft AZ-104) working across Kigali and Kampala.

- **Live (Cloudflare Pages):** https://portofolio-6f2.pages.dev/
- **Mirror (GitHub Pages):** https://irad-david.github.io/portofolio/

Both deploy automatically from the `main` branch: Cloudflare Pages pulls the repo on every push, and `.github/workflows/static.yml` publishes the same files to GitHub Pages. There is no build step.

## What's on the page

| Section | What it shows |
| --- | --- |
| Hero | Name, summary, CV download, and a 20-port patch panel. Each port is a tool, and hovering, focusing or tapping it shows where it was used. |
| Stack | Six infrastructure layers (people → network) that spread apart as you scroll. The active layer follows the text. |
| Experience | UBOS and LOLC Unguka Bank, with a cable run that draws as you read. |
| Selected work | Seven case studies, each with an animated diagram (PAM, VoIP, firewall testing, monitoring, virtualisation and DR, survey data, n8n lab). |
| Credentials | Certifications and education, set out like an asset register. |
| How I work, Contact | Working principles, contact links and a form that opens a pre-filled email. Nothing is sent through a server. |

## Files

```
index.html                  the whole site: HTML, CSS and JS in one file
David-Iradukunda-CV.pdf     CV linked from the page
images/                     optimised photos (WebP + JPEG fallbacks) and the social share image
assets/motion-12.43.0.js    Motion animation library (MIT), self-hosted so the page has no script CDN dependency
DESIGN.md                   colours, type and component rules for future edits
```

## Editing

- **Update the CV:** replace `David-Iradukunda-CV.pdf` with a file of the same name.
- **Change a port on the patch panel:** edit its `data-label` and `data-proof` attributes in `index.html`. The `data-c` colour must be one of `blue`, `green`, `orange`, `violet`, `white`, `grey` or `yellow` (see DESIGN.md).
- **Preview locally:** open `index.html` in a browser, or run `python -m http.server` in this folder and visit http://localhost:8000.

Use relative paths such as `images/...`, never `/images/...`. GitHub Pages serves the site from `/portofolio/`, so root-relative paths break there.

## Tech

Plain HTML, CSS and vanilla JavaScript. [Archivo](https://fonts.google.com/specimen/Archivo) and [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) come from Google Fonts, icons are inline [Lucide](https://lucide.dev) SVGs, and animation uses [Motion](https://motion.dev) for the entrance sequence, scroll-linked effects and in-view reveals. Everything respects `prefers-reduced-motion`, and the colours follow the visitor's light or dark system setting.

© 2026 David Iradukunda
