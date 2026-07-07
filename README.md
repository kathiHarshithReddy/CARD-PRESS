# Card Press — Digital Business Card Studio

A single-file, no-build web app for designing a digital business card and exporting it as a PNG or PDF. Enter your details once and preview them across four distinct card templates in real time.

![template](https://img.shields.io/badge/templates-4-c1121f) ![stack](https://img.shields.io/badge/stack-vanilla%20HTML%2FCSS%2FJS-1c1b1a) ![export](https://img.shields.io/badge/export-PNG%20%7C%20PDF-b08d57)

## Features

- **Name & profile photo** — upload a headshot, or fall back to an auto-generated monogram made from your initials
- **Contact details** — job title, company, email, phone, and website
- **Social links** — LinkedIn, X (Twitter), Instagram, and GitHub handles shown as badges on the card
- **Four templates** — structurally different layouts, not just recolors:
  - **Minimal Ink** — centered serif name, thin rule, contact row
  - **Studio Grid** — asymmetric photo panel + info column
  - **Bold Block** — solid color block with reversed-out photo
  - **Classic Letterpress** — bordered card with centered monogram
- **Live proof preview** — updates as you type, styled like a print shop proof sheet with registration marks
- **Export** — download a high-resolution PNG (3x scale) or a print-ready PDF sized to a standard 3.5×2in business card

## Getting started

No build step, no dependencies to install, no server required.

1. Clone the repo
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
   ```
2. Open the app directly in your browser (double-click `index.html` or `card-press.html`, or use a local server):
   ```bash
   python3 -m http.server 8000
   # then visit http://localhost:8000/
   ```

## Usage

1. Fill in your name, title, company, and contact details in the left panel.
2. Upload a profile photo (optional — initials are used if you skip this).
3. Add your social handles.
4. Pick a template from the swatches.
5. Click **Download PNG** or **Download PDF** to save your card.

## Tech stack

- Vanilla HTML, CSS, and JavaScript — everything lives in one file
- [html2canvas](https://html2canvas.hertzen.com/) for rasterizing the card to an image
- [jsPDF](https://github.com/parallax/jsPDF) for generating the PDF export
- Google Fonts: Fraunces, Inter, IBM Plex Mono
- Both libraries are loaded from the [cdnjs](https://cdnjs.com/) CDN, so an internet connection is needed on first load

## Project structure

```
.
├── .github/workflows/deploy.yml  # GitHub Pages deployment workflow
├── card-press.html   # the entire app (markup, styles, logic)
├── index.html        # redirect entrypoint for root hosting
└── README.md
```

## Deploy

Push to `main` to trigger the included GitHub Pages workflow (`.github/workflows/deploy.yml`).
After enabling GitHub Pages in repository settings, the app is served from the site root and redirects to `card-press.html`.

## License

MIT — use it, fork it, ship it.
