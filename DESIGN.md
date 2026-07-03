<!-- SEED: re-run /impeccable document once there's code to capture the actual tokens and components. -->
---
name: Alees Wine
description: Wine e-catalog with brand presence — earthy, confident, inviting.
---

# Design System: Alees Wine

## 1. Overview

**Creative North Star: "The Cellar-Door Menu"**

Alees is a wine brand with a physical presence first — purchases happen through conversation on Line@, not anonymous checkout flows. The website is the catalog companion: the thing a customer opens to browse while they're deciding what to ask about. The design must communicate quality through restraint and confidence, not decoration. Every element should feel like it belongs on a well-printed menu card from a serious wine house: clean, weighted, purposeful.

The palette is committed — oxblood carries the brand identity through hero sections, primary buttons, and section anchors on a pure-white ground. Color is not decoration here; it is identity. The white ground keeps the catalog legible and product-led; the oxblood makes clear this is not a generic e-shop. Warm gold plays a secondary role, reserved for price, highlights, and moments of reward — the visual equivalent of a gold-foil label.

This system explicitly rejects: the generic Shopify catalog aesthetic (feature-per-row, white background, blue add-to-cart button); the vineyard-cliché palette (cream, sage green, grape-purple); and the cold luxury mode (silver, iceberg white, glacial spacing with nothing to say). Alees is warm and specific, not aspirational-generic.

**Key Characteristics:**
- The homepage ground is a single scroll-driven pour: white at the top, gradating to oxblood and finishing deep wine-red exactly as the LINE CTA band (already solid oxblood) begins — see *The Pour Ground* below.
- Serif display + clean sans body — weight contrast carries hierarchy
- Scroll-linked motion on the homepage (the pour), plus responsive motion elsewhere: hover feedback, cart drawer, smooth transitions
- Gold reserved for price and reward moments; never decorative
- Catalog-first layout: product imagery leads, copy supports

## 2. Colors

An oxblood-on-white strategy: the white ground gives the catalog room to breathe; the oxblood claims identity.

### Primary
- **Brand Red** `oklch(0.400 0.079 23.4)` (#6C3533 — sampled from official Alees catalog): The brand's primary voice. More muted and earthy than pure oxblood — a dark brownish-burgundy wine red. Used for hero backgrounds, primary CTA buttons, nav, footer, and section anchors. On brand fills, text is warm white. Never used for body text on white.

### Secondary
- **Warm Gold / Amber** `[to be resolved — OKLCH reference: oklch(0.68 0.115 78)]`: Reserved for price display, promotion badges, hover accents on product cards, and star/quality indicators. Not decorative — earns its place. One gold element per screen cluster.

### Neutral
- **Near-Black Ink** `oklch(0.140 0.008 23)`: All body text, headings — the pour ground stays light-mode end to end (see *The Pour Ground*), so this never needs to switch. Slightly warm-tinted toward brand hue, never pure cold black.
- **White (pour start)** `oklch(1.000 0.000 0)`: The ground's literal starting value at the top of the homepage — no warmth tint of its own. Warmth is introduced progressively by the pour, capped low enough to stay light-mode throughout.
- **Warm Surface** `oklch(0.972 0.005 23)`: Product card backgrounds, sidebar panels — always opaque and always light, independent of the ambient pour ground behind them. Cards stay legible islands throughout the scroll.
- **Muted Ink** `oklch(0.420 0.008 23)`: Secondary text anywhere on the pour ground. Must pass ≥4.5:1 — this is exactly why the pour is capped at low opacity rather than run to full oxblood saturation.

### Named Rules

**The Gold Rationing Rule.** Gold appears on ≤10% of any given screen. It is the price, the reward, the quality signal. When gold is everywhere, nothing is premium.

**The Pour Ground.** *(Supersedes the former "Warm Ground Prohibition" — the site now deliberately does the opposite by design decision, see Revision Note below.)* The homepage background is not a static color; it is a soft scroll-driven pour — white at the top of the Hero, building a light oxblood wash as the visitor scrolls, landing right as the LINE CTA band (already solid oxblood) begins, so the transition has no visible seam. It's one fixed full-bleed layer (`--c-primary`) whose opacity is scrubbed to scroll position, capped at `0.18` — deliberately far short of the Hero's own saturated pour. That cap is the whole point: the page stays light-mode end to end, near-black ink and muted text never need to switch palette, and product cards (always their own opaque light surface) never inherit any darkening. Keep it soft; if it starts reading as dark or "hero-like," the opacity cap is too high, not the mechanism.

> **Revision note:** the original system prohibited any warm/cream ground, reserving warmth for oxblood and gold alone. That rule was deliberately overridden per explicit product direction: the homepage should read as one continuous, gentle "wine being poured" gesture across the full scroll, not a fixed white canvas — but only as a soft wash, not a full dark takeover. Do not silently re-apply the old prohibition, and do not silently push the intensity back up to Hero-level, without checking with the product owner.

## 3. Typography

**Display Font:** `[Serif — to be chosen at implementation; direction: historical weight, not delicate — think wine-estate label lettering, not editorial magazine]`
**Body Font:** `[Humanist or geometric sans — to be chosen at implementation; clean, works at 14–16px for catalog reading, warm not clinical]`

**Character:** Display serif brings the gravity and craft of an estate that has been making wine for decades. The sans body is clean and confident — never sterile. The pairing is a contrast of eras: the label and the catalog, the tradition and the shop.

Font selection must avoid the reflex-reject list: no Fraunces, Newsreader, Cormorant, Playfair, Crimson, or Lora. Seek fonts with genuine weight range, optically comfortable at display sizes on oxblood backgrounds.

### Hierarchy
- **Display** (light or regular weight, clamp range to be set — max ≤ 6rem, letter-spacing ≥ −0.03em): Hero headlines, brand story section headers. `text-wrap: balance`. White on oxblood or near-black on white.
- **Headline** (medium–semibold, ~2rem–2.8rem): Page-level section headings (Catalog, Our Story, Contact).
- **Title** (medium, ~1.25rem–1.5rem): Product card titles, wine names.
- **Body** (regular, 1rem–1.0625rem, line-height ~1.65, max 65–75ch): Product descriptions, brand copy, news articles. `text-wrap: pretty`.
- **Label** (medium, 0.75rem–0.875rem, light letter-spacing): Category tags, price labels (gold), metadata sub-labels, cart totals.

### Named Rules

**The Weight-Contrast Rule.** Hierarchy lives in weight and size, not color. Don't underline or color-code headings to create emphasis — use scale and weight. Color is for brand identity, not typographic emphasis.

## 4. Elevation

This system is flat by default. Surfaces are on one plane; depth is expressed through color contrast (oxblood section vs. white section) and edge definition, not shadows. Motion energy is responsive — hover states and transitions reveal elevation contextually, not structurally.

Product cards at rest: no shadow. On hover: a single controlled ambient shadow lifts the card slightly to signal interactivity. The shadow is the action, not the default state.

**The Flat-By-Default Rule.** Shadows exist only as a response to state (hover, open drawer, active modal). A page full of shadowed cards is a page that trusts shadows over content. Commit to the content.

## 5. Components

*Omitted in seed mode. Component specifications will be written during implementation when real markup and token values are available.*

## 6. Do's and Don'ts

### Do:
- **Do** use oxblood as section background for hero, footer, and key CTA zones — the committed strategy demands real commitment; a single oxblood button on a beige page is not commitment.
- **Do** use warm white (`oklch(0.94 0.008 60)`) for text that sits on oxblood fills. Cold white reads disconnected on a warm-hued background.
- **Do** reserve gold exclusively for price display, reward moments, and one accent rule per section. Gold earns its place by being rare.
- **Do** let the homepage ground carry a soft oxblood wash across the full scroll (see *The Pour Ground*) — start it white, cap it low (light-mode throughout, well short of the Hero's own saturated pour), end it exactly at `.line-band`, and keep product cards opaque and light so they never inherit the tint.
- **Do** use product photography as the primary driver of catalog sections — large, clean, decisive shots. The image is the product.
- **Do** ensure body text contrast ≥4.5:1 and secondary/muted text ≥4.5:1 on white. "Muted" means lighter, not unreadable.
- **Do** provide a `@media (prefers-reduced-motion: reduce)` fallback for every transition and animation.

### Don't:
- **Don't** use a *static* cream, beige, or sand page background — that generic AI-default flat tint is still prohibited. The homepage ground is only ever in gentle motion (the scroll-driven pour); it is never a fixed warm color sitting still on the page.
- **Don't** push the pour's opacity cap high enough that it stops being light-mode — if near-black ink or muted text ever needs a "dusk" palette switch to stay readable, the pour has gotten too dark; turn the cap back down instead of adding a text-color workaround.
- **Don't** reproduce the generic Shopify / WooCommerce catalog layout — equal-width grid, blue CTA buttons, flat typography. Alees must have its own identity.
- **Don't** use the vineyard-cliché palette: cream + sage green + grape purple. This has no relationship to Alees's brand.
- **Don't** design for cold luxury (silver, iceberg white, wide-tracked all-caps on everything, zero warmth). Alees is inviting, not unapproachable.
- **Don't** use gradient text (`background-clip: text` + gradient). Ever.
- **Don't** add a side-stripe border (`border-left` > 1px as a colored accent) on cards, list items, or callouts.
- **Don't** put a tiny uppercase tracked eyebrow ("CATALOG" / "ABOUT" / "NEWS") above every section heading. One deliberate brand kicker is voice; an eyebrow on every section is AI grammar.
- **Don't** fill empty wine card slots with colored placeholder rectangles. If images are missing, use a branded product-silhouette SVG or a single-color brand-fill panel — never a generic grey box.
- **Don't** choose Fraunces, Newsreader, Cormorant Garamond, Playfair Display, Lora, Crimson, or any font from the reflex-reject list. Browse further.
