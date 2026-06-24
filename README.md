# Perfora — Smart Dental Flosser (Black Gold) Microsite

A single, self-contained product microsite landing page for the **Perfora Smart Dental Flosser – Black Gold**.

One of a series of microsite landing pages A/B-tested against Perfora's standard PDPs to drive higher engagement and direct-to-cart conversions from ad traffic.

## Live file

- [`index.html`](index.html) — the complete page, served at the site root. Fully self-contained (hero image inlined as a data URI); the only external request is Google Fonts. Named `index.html` so static hosts (Vercel, Netlify, GitHub Pages) serve it at `/`.

## Product

| | |
|---|---|
| **Product** | Smart Dental Flosser – Black Gold |
| **Source PDP** | https://perforacare.com/products/water-flosser |
| **Shopify Variant ID** | `PER2855` |
| **Add-to-cart URL** | `/cart?items[]=PER2855:1` |
| **Price** | ₹3,039 (MRP ₹3,599 · 16% off) |

### Key USPs
- **29% more effective** at removing plaque vs. traditional string floss
- **5 flossing modes** — Soft, Normal, Pause, Neo Peo (7 pressure levels), DIY
- **IPX7 waterproof** · use it in the shower
- **USB-C rechargeable** — one charge lasts 30–45 days
- **2-year warranty** · 300ml tank · 360° rotating nozzle · 5 colour-coded nozzles

## Design

- **Type:** Spectral (headings) + Inter (body) — loaded in one Google Fonts request
- **Style:** graphic-led and scannable — deep-purple/lavender palette with a lime accent, floating product cutouts, circular lifestyle imagery, icon tiles, pill badges and color-blocked sections (inspired by the reference, in Perfora's brand)
- **Layout:** mobile-first, 1100px max content width, vanilla JS only (no frameworks), inline SVG icon sprite
- **16 sections:** header → hero → buy/listing (variant selector + offer chips + Add to Cart / Buy It Now) → trust strip → benefit tiles → vs-string-floss comparison → modes & nozzles → mid CTA → how-to-use → what's-inside → who-it's-for → expert/trust → UGC placeholder → reviews → FAQ → final CTA

## Visuals

The hero is a **layered HTML/CSS composition** — a circular lifestyle shot of the product in use, the floating product cutout, and animated pill/callout cards on a purple graphic background. All imagery is built from the **real PDP photography**, re-cut and recoloured to the brand palette. Assets in [`assets/`](assets/):

- `model-lifestyle.jpg` — PDP model shot, background recoloured to brand lavender (hero + expert section)
- `flosser-standing.png` — the assembled flosser, background removed (transparent, floating in the hero)
- `nozzles.png` — the 5 nozzle tips, background removed (modes & nozzles section)
- `cable.png` — USB-C cable, background removed (how-to-use step)
- `whats-inside-wide.jpg` / `whats-inside-square.jpg` — finished "What's inside the box" banners (desktop / mobile), swapped responsively via `<picture>`

The **how-to-use** steps use real product photos (device, nozzles, model-in-use, cable) on lavender tiles rather than icons. To swap in custom step illustrations, replace the four `<img>` sources in the `#how-to-use` section (square ~600×600 works best).

Product images are **referenced from `assets/`** (relative paths) so the page stays lean and fast on a static host. For Shopify, upload these to the theme/Files and swap the `src` paths for the Shopify CDN URLs.

## Deploy on Shopify

1. Shopify Admin → Online Store → Themes → Edit Code
2. Create `templates/page.microsite-smart-dental-flosser.liquid`
3. Add `{% layout none %}` at the top
4. Paste the full contents of `index.html` below that line
5. Assign the template to the relevant Page in Pages settings

## Dev notes

- Section 7 is an Instavid UGC placeholder — embed the carousel widget where marked.
- The page is intentionally header-nav / footer free; the Shopify theme provides those.
