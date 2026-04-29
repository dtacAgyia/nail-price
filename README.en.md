[中文](README.md) | **English**

# Nail Price Calculator

A lightweight, mobile-friendly nail service price calculator. Runs from a single HTML file — no install, no build step, just open it in a browser.

## Features

- **Removal service options**: in-shop / from-other-shop, removal-only, removal + new set, removal + prep care
- **Art design pricing**: single color, cat's eye, mirror / gradient / French, minimalist, advanced, complex
- **Add-ons**
  - Repair ($50 per finger, stackable)
  - Upgrade single color to cat's eye (+$100, requires a base service)
- **Live total** displayed in New Taiwan Dollar (TWD)
- **One-tap copy** of a formatted quote, ready to paste into LINE / messaging apps
- **One-tap reset**
- **Mobile web-app feel**: iOS Add to Home Screen support (apple-touch-icon, custom app name)

## Price List

### Removal
| Item | Price |
| --- | --- |
| No removal needed | Free |
| In-shop removal + new set | $100 |
| Other-shop removal + new set | $200 |
| In-shop removal only (no prep) | $300 |
| Other-shop removal only (no prep) | $400 |
| In-shop removal + prep care | $500 |

### Art Design
| Style | Price | Notes |
| --- | --- | --- |
| Single color | $600 | Includes prep, build, care |
| Cat's eye | $700 | Includes prep, build, care |
| Mirror / Gradient / French | $900 | Includes prep, build, care |
| Minimalist | $900 | Simple lines, accent charms |
| Advanced | $1000 | Blending, mirror powder, light 3D |
| Complex | $1200 | Hand-painted, large charms, mixed 3D |

### Add-ons
| Item | Price |
| --- | --- |
| Repair | $50 / finger |
| Upgrade single color to cat's eye | +$100 |

> Removal-only and removal + prep care are standalone services. Selecting them disables the art design section automatically.

## Quick Start

Open `index.html` directly in your browser:

```bash
git clone https://github.com/dtacAgyia/nail-price.git
cd nail-price
open index.html        # macOS
# Or double-click index.html on Windows
```

Or serve it with any static server:

```bash
python3 -m http.server 8000
# Then visit http://localhost:8000
```

## Tech Stack

- **React 18** (loaded via CDN UMD bundle)
- **Tailwind CSS** (CDN)
- **Babel Standalone** (in-browser JSX compilation)
- Inline Lucide-style SVG icons (no external icon library)

The entire project is a **single `index.html`** — no build step, no `node_modules`. Easy to host on any static service (GitHub Pages, Netlify, Vercel, Cloudflare Pages, etc.).

## Project Structure

```
nail-price/
├── index.html              # Main app (React)
├── apple-touch-icon.png    # iOS home-screen icon
└── apple-touch-icon.svg    # Vector icon
```

## Deploy to GitHub Pages

1. Go to the repo's **Settings → Pages**
2. Source: `Deploy from a branch`
3. Branch: `main`, folder: `/ (root)`
4. Save and wait a few seconds — your site will be live at `https://dtacagyia.github.io/nail-price/`

## Customizing Prices

All prices live in the `services` and `removalOptions` arrays inside `index.html`:

```js
const services = [
  { id: 'single', name: '單色', price: 600, desc: '含前置、建構、保養' },
  // ...
];
```

Edit, save, refresh the browser — no rebuild needed.

## Copy-Quote Example

Tapping "Copy" produces output like:

```
【美甲服務報價單】
------------------
■ 本店卸甲續作: $100
■ 單色: $600
■ 加購-單色換貓眼: $100
■ 加購-補甲 (2指): $100
------------------
總金額: $900
```

## License

No license specified yet. Please contact the author before reusing.
