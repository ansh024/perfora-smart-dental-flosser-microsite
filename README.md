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
- **Palette:** deep purple / lavender editorial tones derived from the Pinterest design reference, lime accent for pills, high-contrast CTAs
- **Layout:** mobile-first, 1100px max content width, vanilla JS only (no frameworks)
- **Sections:** sticky header → hero → problem/solution → features → mid CTA → how-to-use → UGC placeholder → reviews → FAQ → final CTA

## Hero image

The hero is AI-composed: the **real product image from the PDP** (embedded unaltered) lifted onto an editorial purple campaign scene matching the design reference. Source files in [`assets/`](assets/):

- `flosser-hero.jpg` — final web-optimised hero (also inlined in the HTML)
- `product-cutout.png` — the product flat-lay with its background removed (transparent PNG)
- `hero-stage.html` — the CSS composition stage used to render the scene

To swap in a final campaign photo, replace the `<img class="hero-img">` source in the HTML (look for the `<!-- HERO IMAGE -->` comment).

## Deploy on Shopify

1. Shopify Admin → Online Store → Themes → Edit Code
2. Create `templates/page.microsite-smart-dental-flosser.liquid`
3. Add `{% layout none %}` at the top
4. Paste the full contents of `index.html` below that line
5. Assign the template to the relevant Page in Pages settings

## Dev notes

- Section 7 is an Instavid UGC placeholder — embed the carousel widget where marked.
- The page is intentionally header-nav / footer free; the Shopify theme provides those.
