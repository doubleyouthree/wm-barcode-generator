# WM Barcode Generator

A single-file client-side web app to generate barcodes from 16-digit bonus codes. It prepends the prefix `79936686504000` and renders a CODE128 barcode using JsBarcode. Generated barcodes can be downloaded as PNG. Submitted codes are saved in localStorage with status controls (partially used, archive) and an option to show archived.

# Demo

[Click here to view on Github Pages]([https://www.genome.gov/](https://doubleyouthree.github.io/wm-barcode-generator/))

## Features
- 16-digit code validation (digits only)
- Full barcode text = `79936686504000` + your 16-digit code
- Client-side barcode rendering (CODE128) via JsBarcode
- Download barcode as PNG (from a `<canvas>`)
- Persist codes in `localStorage`
- Mark code as "Partially used" or (Un)Archive
- Toggle to show archived codes

## Usage
1. Open `index.html` in any modern browser (no server or build needed).
2. Enter a 16-digit bonus code and click Generate.
3. Click "Download PNG" to save the barcode image.
4. Manage previously saved codes in the list (Show barcode, Mark partially used, Archive/Unarchive). Use the toggle to show archived entries.

## File Structure
- `index.html` — contains all HTML, CSS, and JS inline. JsBarcode is loaded from a CDN.

## Offline Use
The app works fully offline after first load. If you want zero external dependencies (so it works on first load without internet), you can inline JsBarcode directly into `index.html`. If you want that version, ask and we can embed the minified library inline.

## Data Persistence
- Codes are stored under the key `wm_barcodes_v1` in `localStorage`.
- Each entry includes: the 16-digit code, the full barcode text, status (`new` | `partial` | `archived`), and a timestamp.
- Clearing browser storage will remove saved codes.

## Troubleshooting
- If the barcode does not render, ensure your input is exactly 16 digits.
- If the PNG download does nothing, confirm your browser allows automatic downloads and that the page is served via a file URL or HTTP.
- If you previously opened an older version, try a hard refresh to clear cached assets.

## License
MIT
