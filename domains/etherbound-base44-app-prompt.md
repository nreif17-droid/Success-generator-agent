# Etherbound — Base44 App Build Prompt

Built 2026-08-05. First use of the name "Etherbound" in this repo —
captured here as the confirmed brand name for what's been tracked
generically as "the apparel brand" across `domains/apparel-brand*.md`.
This file compiles everything accumulated in this thread into a single
prompt, ready to paste into Base44. Resolves the previously-open "AI
store-builder tool" item in `domains/apparel-brand-system.md` — Base44 is
that tool.

---

## Ready-to-paste prompt for Base44

> **Purpose directive — read this first:**
> You are building the official web app for **Etherbound**, a
> small-batch, direct-to-consumer fitness apparel brand. The app's core
> purpose right now is **not** "launch a full storefront on day one" —
> it's a **two-stage build**: (1) a waitlist-first landing experience to
> capture and grow an email/SMS list during a 6-month audience-building
> phase, starting from under 300 followers and near-zero ad budget, and
> (2) a product/cart layer that activates once Phase 1 inventory is
> ready to ship. Build for that reality, not a generic pre-built
> e-commerce template that assumes a full catalog and paid traffic from
> day one.
>
> **Brand identity:**
> - Name: Etherbound
> - Aesthetic: dark, painterly, atmospheric fantasy/epic — cracked,
>   glowing crescent moons, lightning, a robed figure ascending a grand
>   staircase toward a castle, starfields, smoke/cloud atmosphere.
>   Closer to gaming-culture streetwear (Elden Ring/Dark Souls box-art
>   energy) than clean athletic-brand minimalism.
> - Garment color for Phase 1: black, with the graphics deliberately
>   fading into the black fabric at the edges — echo this on the site
>   itself: dark background, high-contrast glowing accents (amber/gold,
>   icy blue) matching the actual garment art, not a generic light
>   e-commerce theme.
> - Positioning: explicitly not a quick cash-grab — framed throughout
>   this project as a legitimate long-term business, a product the
>   founder genuinely cares about, building a culture around it.
>
> **Product line:**
>
> Phase 1 (launching first):
> - Hoodie — heavyweight cotton or 80/20 cotton-poly fleece (~350–500
>   GSM), black, DTG print (wizard/staircase graphic, back)
> - Pump cover (oversized tee) — 100% cotton jersey or 75/25
>   cotton-nylon (~180–300 GSM), black, DTG print (cracked-moon graphic,
>   back)
> - 50 units produced per garment; 20 units total (10 each) go to
>   influencer seeding, 2 kept for the founder's own wear — 78 units
>   actually sellable
> - Retail price: not finalized — use a placeholder around $55 and make
>   it easy to change
>
> Phase 2 (added later — funded by separate business capital once
> available, not by Phase 1 revenue; build the product/catalog structure
> to accommodate this without a rebuild, but don't launch it yet):
> - Compression shirt — 85–90% polyester (or nylon) / 10–15% elastane
> - Shorts — ~85% polyester / 15% elastane
> - Sweatpants — heavyweight cotton or 85/15 cotton-poly terry
> - ~75 units planned per garment
>
> **Functional requirements, in priority order:**
> 1. **Waitlist capture** — email/SMS signup, prominent on every page.
>    This is the priority feature right now, not an afterthought — the
>    entire pre-launch strategy runs through this list.
> 2. **Brand/story landing page** — reflects the aesthetic and
>    positioning above, not generic apparel-template copy.
> 3. **Product pages for the 2 Phase 1 garments**, ready to go live once
>    inventory exists, price editable.
> 4. **Simple cart/checkout** — low SKU count (2 garments × sizes),
>    doesn't need complex catalog/inventory management.
> 5. **Mobile-first** — most traffic will come from social content, not
>    desktop.
> 6. **Referral/discount-code capability** for early buyers — part of
>    the low/no-ad-budget go-to-market plan; turns customer 1 into part
>    of the acquisition channel for customer 2.
> 7. **Room to add Phase 2 garments later** without a full rebuild.
>
> **Explicit constraints:**
> - Near-zero ad budget — do not assume paid traffic. Traffic comes from
>   organic content, influencer seeding (product, not cash), and a
>   starting audience of under 300 followers being built over 6 months.
> - Founder is not experienced with app-building tools — prefer sensible
>   defaults over surfacing many technical decisions.
> - This is a small, 2–5 SKU operation for the foreseeable future, not a
>   large-catalog storefront — don't over-build for scale that doesn't
>   exist yet.

---

## Source material this prompt was compiled from

- `domains/apparel-brand.md` — status, phased plan, priority context
- `domains/apparel-brand-system.md` — garment/material specs, DTG/black
  decision, fulfillment model
- `domains/apparel-brand-financial-model.md` — audience-first strategy,
  seeding allocation (20 units), sellable-inventory math (78 units),
  $55 price placeholder
- `domains/apparel-brand-vendor-outreach-worksheet-printable.pdf` —
  confirmed garment/material/color/print decisions
- Design images reviewed 2026-08-05 — wizard/staircase (hoodie back),
  cracked moon (pump cover back), dark painterly aesthetic

## Open items not resolved by this prompt

- Final retail price (placeholder $55 used throughout)
- Whether Base44 replaces Shopify entirely or the two get compared —
  `domains/apparel-brand-system.md` previously flagged this as
  undecided; treat this prompt as resolving it in Base44's favor unless
  told otherwise
- Etherbound as the brand name — confirmed here for the first time;
  update `domains/apparel-brand*.md` file titles/references if this is
  final
