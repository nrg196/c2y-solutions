# C2Y Solutions Product Website

Static product catalog site (HTML, CSS, JavaScript). No build step. Works on GitHub Pages.

## Files

- `index.html`: page layout (header, hero, products, ETP videos, about, contact)
- `css/style.css`: brand styling (Forest Green #025C38 from the logo, leaf green accent)
- `js/products.js`: all product data. **Generated from `C2Y-Products.xlsx`, do not edit by hand.**
- `tools/excel_to_products.py`: converts the Excel file into `js/products.js`
- `js/app.js`: filters, search, product pop-up, video player, WhatsApp enquiry
- `images/`: logo, hero photo and product photos
- `videos/`: ETP equipment videos. Each `name.mp4` has a poster photo `name.jpg` with the same name.

## Product photos

Most chemical product photos are currently loaded from the old site123 catalogue's image server.
If that site is closed, those photos will stop loading and the C2Y logo shows in their place.
To make them permanent: save each photo into `images/products/`, then change the Image 1 column
in the Excel file to `images/products/<file>.jpg` and regenerate.

## Editing products

Product data lives in **C2Y-Products.xlsx** (kept in the C2Y solutions folder, not in this repo). Its "Read Me" sheet explains every column.

1. Edit the Excel file. Put new photos in `images/products/` (or videos in `videos/`) and enter their address in the Image columns.
2. Send the saved Excel file to Claude to regenerate `js/products.js`, or run it yourself:
   `python tools/excel_to_products.py "path\to\C2Y-Products.xlsx" js/products.js`
3. Commit and push in GitHub Desktop.

## Review mode

Open the site with `?review` at the end of the URL (for example `index.html?review`) to see an orange "check" flag on products that need verification, plus the note explaining what to check. Normal visitors do not see these notes.

## Publish on GitHub Pages

1. Upload everything in this folder to the `c2y-solutions` repository (keep the folder structure).
2. Go to **Settings > Pages**, set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, then Save.
3. The site will be live at `https://nrg196.github.io/c2y-solutions/` in a minute or two.

## Preview locally

Double-click `index.html`, or run `python -m http.server` in this folder and open http://localhost:8000.
