# DealPlate 🛒🍳

**Upload your grocery store's weekly ad. Get recipe ideas based on what's on sale.**

DealPlate is a fully static, single-file web app — no backend, no server, no build step. Drop it on GitHub Pages and it's live in under a minute.

---

## Features

- **Upload any grocery ad** — drag in a PDF or photo; the app extracts sale items automatically using PDF.js (for digital PDFs) or Tesseract.js OCR (for images and scanned PDFs)
- **Review & edit items** — remove false positives or add items the parser missed
- **Recipe filters** — narrow results by cuisine, diet, meal type, and cook time
- **Powered by Spoonacular** — recipe cards show cook time, servings, which sale items are used, and what pantry staples you'd still need
- **Your data stays local** — grocery ads are processed entirely in your browser and never uploaded anywhere

## Quick start

1. Push `index.html` to a public GitHub repo
2. Enable **GitHub Pages** (Settings → Pages → deploy from `main`)
3. Get a free API key at [spoonacular.com/food-api](https://spoonacular.com/food-api)
4. Open the live site, click **⚙️ API Settings**, and paste your key

Full walkthrough in [SETUP.md](./SETUP.md).

## Tech

| Piece | What it does |
|---|---|
| [PDF.js](https://mozilla.github.io/pdf.js/) | Extracts text from digital PDFs client-side |
| [Tesseract.js](https://tesseract.projectnaptha.com/) | OCR for images and scanned PDFs (lazy-loaded) |
| [Spoonacular API](https://spoonacular.com/food-api) | Recipe search by ingredient with filters |

No frameworks, no bundler, no dependencies to install — just one HTML file.

## License

MIT
