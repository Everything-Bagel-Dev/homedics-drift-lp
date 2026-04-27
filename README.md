# Homedics Drift × Mental Health Awareness Month 2026
## Landing Page: "Your Good Day Starts Here"

Built by Everything Bagel Partners / Jarvis  
Campaign flight: May 1–31, 2026  
Store: [homedics.com](https://www.homedics.com)

---

## What Was Built

A complete Shopify Online Store 2.0 landing page — 7 custom sections + template + CSS.

| File | Section | Purpose |
|------|---------|---------|
| `sections/drift-hero.liquid` | 1 — Hero | Full-bleed dark hero, MHA badge, RGBIC glow animation, primary + secondary CTAs |
| `sections/drift-insight.liquid` | 2 — Insight | Emotional hook, pull quote, MHA connection body copy |
| `sections/drift-product-grid.liquid` | 3 — Product Grid | 3-column product cards with live Shopify pricing, tag pills, feature lists |
| `sections/drift-endorsements.liquid` | 4 — Endorsements | Doctor quote cards (2×2 grid), press logo bar — all dark background |
| `sections/drift-app-experience.liquid` | 5 — App Experience | Split-screen phone mockup + copy, ambient glow, feature bullets |
| `sections/drift-gifting.liquid` | 6 — Gifting | Mother's Day section with **date-based auto-hide** (hides May 12+) |
| `sections/drift-final-cta.liquid` | 7 — Final CTA | Closing section, ambient glow, strong CTA |
| `assets/drift-mham.css` | — | All custom CSS in one consolidated file (~650 lines) |
| `templates/page.drift-mham.json` | — | OS 2.0 JSON template wiring all sections with default copy values |

---

## ⚠️ Required Before Publishing

These placeholders **must** be filled before the page goes live:

### Doctor Quotes (Section 4 — Endorsements)
All 4 quotes are placeholder text. Pull verbatim approved quotes from Homedics asset library:

| Setting in Admin | Doctor | Topic |
|-----------------|--------|-------|
| `quote_1_text` | Dr. Schwartz | Stress relief / mindfulness |
| `quote_2_text` | Dr. Rosenstock | Sleep / ambient light |
| `quote_3_text` | Dr. Gonzalez | Anxiety reduction |
| `quote_4_text` | Dr. Nieves | Mindfulness ritual |

> ⚠️ Do NOT fabricate or paraphrase. These are claimed endorsements. Pull exact quotes.

### Product Images (Sections 1, 3, 6)
Upload lifestyle photography through Shopify Admin (Customize → each section's image picker):

| Location | What's Needed |
|----------|--------------|
| Hero image | Drift 10" on nightstand in dimly lit bedroom — lifestyle, not studio |
| Product card 1 | Drift 10" on bedside table or desk |
| Product card 2 | Drift 16" in living room or shared bedroom |
| Product card 3 | Drift 21" as statement piece in living/dining room |
| Gifting section | Woman 38–48, natural light, Drift in situ — warm, calm |
| App section | Real Drift app UI in clean phone mockup frame |

### Press Logos (Section 4)
Upload press logos from Homedics press kit. Use white/light versions for dark background.  
You can also use text fallbacks by setting "Press outlet N (text fallback)" fields.

### App CTA URL (Section 5)
Set the "Download the App" URL to the Homedics Drift app page (App Store / Google Play link).

### Sale Pricing (Section 3)
The Drift 16" and 21" cards show "On Sale" with compare-at prices from the brief.  
Confirm sale pricing is live in Shopify before publishing. The section pulls live `compare_at_price_max` automatically if set on the product.

---

## How to Preview (Local)

This is Shopify OS 2.0 code — it must be previewed inside a Shopify theme. There is no static HTML preview.

### Option A — Shopify CLI (Recommended)

```bash
# Install Shopify CLI if not already installed
npm install -g @shopify/cli @shopify/theme

# Navigate to your Shopify theme directory
cd /path/to/your/shopify/theme

# Copy the built files into the theme
cp ~/Desktop/homedics-drift-lp/sections/drift-*.liquid sections/
cp ~/Desktop/homedics-drift-lp/assets/drift-mham.css assets/
cp ~/Desktop/homedics-drift-lp/templates/page.drift-mham.json templates/

# Start dev server (connects to Homedics store)
shopify theme dev --store=homedics.myshopify.com
```

### Option B — Theme Upload via Admin

1. Download the active Homedics theme as a ZIP from Shopify Admin → Online Store → Themes → Actions → Download
2. Unzip the theme
3. Copy files from this repo into the theme folder (same paths as above)
4. Re-zip and upload as a new theme
5. Preview before publishing

---

## How to Deploy to Shopify

### Step 1 — Prepare the Theme

Copy these files into the active Homedics theme:

```
sections/drift-hero.liquid          → theme/sections/
sections/drift-insight.liquid       → theme/sections/
sections/drift-product-grid.liquid  → theme/sections/
sections/drift-endorsements.liquid  → theme/sections/
sections/drift-app-experience.liquid → theme/sections/
sections/drift-gifting.liquid       → theme/sections/
sections/drift-final-cta.liquid     → theme/sections/
assets/drift-mham.css               → theme/assets/
templates/page.drift-mham.json      → theme/templates/
```

### Step 2 — Create the Shopify Page

1. In Shopify Admin → Online Store → Pages → Add page
2. Title: `Your Good Day Starts Here` (or as preferred)
3. Handle: `drift-mham` (important — controls URL)
4. Template: `page.drift-mham`
5. Save

### Step 3 — Customize in Theme Editor

1. Shopify Admin → Online Store → Themes → Customize
2. Navigate to the new Drift MHAM page
3. Upload all images (see "Required Before Publishing" above)
4. Fill in doctor quotes
5. Set CTA URLs (product pages, app download link)
6. Publish when ready

### Step 4 — QA Checklist Before Launch

- [ ] All doctor quotes are verbatim approved text (no placeholders visible)
- [ ] All product images uploaded and displaying
- [ ] Sale pricing is accurate and live on products
- [ ] All CTAs resolve to correct URLs (no 404s)
- [ ] Mobile responsive — tested on 375px, 390px, 414px viewport
- [ ] Gifting section visible (it's before May 12 during May flight)
- [ ] RGBIC glow animation running in hero (CSS, no JS required)
- [ ] No exclamation marks anywhere in copy
- [ ] page.drift-mham template selected on the page

---

## Design System Reference

| Token | Hex | Usage |
|-------|-----|-------|
| Midnight | `#0D0D12` | Hero, endorsements, final CTA |
| Deep Navy | `#0C1B2E` | App section background |
| Linen | `#FAF8F4` | Insight, products, gifting sections |
| Charcoal | `#1A1A1A` | Primary body text |
| Mid Gray | `#4A4A4A` | Secondary body text |
| MHA Green | `#1D8A4C` | Badge, credentials, feature dots |
| Sale Red | `#D93025` | Sale pricing, on-sale tags |
| Card Dark | `#1C1C24` | Doctor quote cards |

---

## Campaign Notes

- **Flight:** May 1–31, 2026
- **Gifting section** automatically hides on May 12, 2026 (UTC) via Liquid date logic. Can also be force-hidden early via admin toggle.
- **MHA integration:** Organic/awareness only — no partnership claim. Brief explicitly states: no "we donate to MHA" claims unless formal partnership confirmed.
- **No autoplay video** — animations are CSS-only (`@keyframes driftGlowCycle`)
- **No JS required** — entire page functions with CSS + Liquid only

---

## Questions / Support

Jarvis (Everything Bagel AI) — jarvis@everythingbagel.com  
Built: April 27, 2026
