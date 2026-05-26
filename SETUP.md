# DealPlate — Setup Guide

DealPlate is a fully static website. There is no backend, no API keys for grocery data,
and no server to maintain. You just need:

1. A free GitHub account (for hosting)
2. A free Spoonacular API key (for recipe search)

---

## How it works

```
You upload a weekly-ad PDF or photo
        │
        ▼
Browser extracts text (PDF.js) or runs OCR (Tesseract.js)
        │
        ▼
Items are parsed and displayed as chips
        │
        ▼
You click items + set recipe filters (cuisine, diet, type, time)
        │
        ▼
Browser calls Spoonacular → recipe cards appear
```

Everything runs client-side. Your grocery ad never leaves your device.

---

## Step 1 — Publish to GitHub Pages

1. Go to **github.com → New repository**, name it (e.g. `dealplate`), set it **Public**
2. Upload `index.html` to the repo (drag it into the GitHub file browser, or push via git)
3. Go to **Settings → Pages → Source → Deploy from branch → main / root → Save**
4. Your site will be live at `https://YOUR_USERNAME.github.io/dealplate` within ~60 seconds

That's it for hosting. You can delete the `scripts/`, `data/`, and `.github/` folders — they were
for the old Kroger API approach and are no longer needed.

---

## Step 2 — Get a Spoonacular API key (free)

1. Create a free account at **https://spoonacular.com/food-api**
2. Go to **Console → Dashboard** and copy your API key
3. On your live DealPlate site, click **⚙️ API Settings** and paste the key

The key is stored only in your browser (localStorage). It's never sent anywhere except
directly to Spoonacular's servers.

**Free tier:** 150 points/day — each recipe search costs 1 point, so this is plenty for personal use.

---

## Using the site

### Upload a grocery ad
Click the upload zone or drag a file onto it. Supported formats:
- **PDF** — works best with digital ads (the kind you download from a store's website)
- **JPG / PNG / WEBP** — screenshots or photos of paper ads

If you upload a scanned PDF (image-based, no text layer), the site will ask if you want
to run OCR on it. OCR takes ~30–60 seconds per page but works well on clear images.

### Adjust items
After upload, review the extracted items. You can:
- **Click** a chip to toggle it for recipe search
- **✕** a chip to remove it from the list entirely
- **Add items manually** using the text field at the bottom

### Set recipe filters
Use the filter pills to narrow results by:
| Filter | Options |
|---|---|
| **Cuisine** | Italian, Mexican, Asian, Mediterranean, Indian, American, French, Greek |
| **Diet** | Vegetarian, Vegan, Gluten-Free, Keto, Paleo, Pescetarian |
| **Meal Type** | Main Course, Breakfast, Soup, Salad, Appetizer, Snack |
| **Cook Time** | ≤ 15, 30, 45, or 60 minutes |

### Find recipes
Select at least one item, then click **Find Recipes →**. Results show:
- Cook time and servings
- Which sale items the recipe uses (green tags)
- What extra pantry items you'd need (yellow tags)
- Link to the full recipe

---

## Troubleshooting

**No items detected after upload**
→ Try a clearer image or a digital PDF from the store's website. You can always add items manually.

**Scanned PDF takes a long time**
→ OCR downloads ~5 MB of language data the first time. Subsequent runs on the same page session are faster.

**"Invalid API key" on recipes**
→ Re-enter your key via ⚙️ API Settings. Make sure there are no leading/trailing spaces.

**"Daily quota exceeded"**
→ Spoonacular free tier allows 150 requests/day. Try again tomorrow or upgrade at spoonacular.com.
