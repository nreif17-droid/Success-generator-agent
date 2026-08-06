# Apparel Brand — 12-Month Financial Model

Built 2026-08-05, per direct request for a 12-month projection starting
from launch. **This is a planning framework with labeled assumptions,
not a promised outcome** — per the guardrails this agent operates under,
financial projections get informational framing, never a guaranteed
result. Every number below is either a stated assumption (confirm/adjust)
or a range from real industry benchmarks (cited) — swap in real numbers
as vendor quotes and ad performance data come in.

## Open reconciliation — resolve before trusting this model

Nolan's stated launch cost: ~$8,000 for the two Phase 1 items (50 hoodie
+ 50 pump cover). This session's desk-research unit-cost estimate for
that same 100 units was ~$1,250–$2,300. **This gap is unresolved** —
could be a different unit-cost assumption, or the $8k bundling in
non-product costs (samples, decoration setup, packaging, site, initial ad
budget). Confirm which before treating either number as real. The model
below uses labeled placeholder assumptions either way.

## Assumptions used in this model (label: confirm/adjust each)

| Assumption | Value used here | Source / confidence |
|---|---|---|
| Phase 1 unit cost (blended, hoodie+pump cover) | **$20/unit placeholder** (low end of desk estimate) — *or* **$80/unit** if Nolan's $8k figure is pure product cost | Unconfirmed — pick one or supply real vendor quote |
| Phase 1 retail price (blended, hoodie+pump cover) | **$55/unit placeholder** | Reference: Gymshark hoodies ~$60-75, YoungLA hoodies ~$50-65, joggers/pump-cover-adjacent pieces ~$45-60 |
| Cold-traffic CAC (zero existing audience) | **$90-180/new customer** | [Eightx CAC by vertical](https://eightx.co/blog/average-cac-ecommerce-vertical), [Let's Talk Shop DTC CAC benchmarks](https://www.letstalkshop.com/blog/dtc-customer-acquisition-cost-benchmarks) |
| Cold prospecting ROAS (Meta) | **1.5x-3x** | [Hawky.ai ROAS benchmarks 2026](https://hawky.ai/blog/roas-benchmarks-by-industry), [Adamigo Fashion Meta ROAS 2026](https://www.adamigo.ai/blog/fashion-ecommerce-meta-ads-roas-benchmarks-2026) |
| Units per order | 1.1 (light multi-item assumption) | Estimate, not benchmarked |
| Phase 2 items | Shorts + sweatpants + compression shirt, 75 units each (225 units) | Nolan's stated plan, 2026-08-05 |
| Phase 2 trigger | Phase 1 sell-through funds it ("straight back into producing the next line") | Nolan's stated plan |

## The math worth seeing before committing ad budget

At **$55 AOV** and **$90-180 CAC**, acquiring a customer costs as much
as or more than the entire order value — this is a normal DTC pattern
(you often lose money or barely break even on a customer's *first*
purchase; the actual profit comes from repeat purchases and rising
average order value over time), but it means **Phase 1 alone is not
likely to be profitable on paper**, even in a reasonably-good-execution
scenario. That's not a reason not to do it — it's the real cost of
building a customer base with zero existing audience, and worth going in
with eyes open rather than expecting Phase 1 itself to fund Phase 2 on
its own.

**Break-even ROAS** = 1 ÷ gross margin. At $55 retail / $20 cost (73%
margin): break-even ROAS ≈ 1.4x — achievable within the 1.5-3x cold
range. At $55 retail / $80 cost (loss before ad spend): the unit
economics don't work at all — this is exactly why the $8k reconciliation
above has to happen before any of the rest of this is trustworthy.

## Three scenarios for Phase 1 (100 units: 50 hoodie + 50 pump cover)

Using the $20/unit cost, $55 AOV placeholder (the version where the math
can work) — **not** the $80/unit version, which doesn't clear break-even
regardless of ad performance:

| Scenario | CAC | Ad spend to sell 100 units (~90 orders) | Product cost | Total cash out | Revenue (100 units × $55) | Net (this phase only) |
|---|---|---|---|---|---|---|
| **Conservative** | $180 (high end, unproven creative) | ~$16,200 | ~$2,000 | ~$18,200 | $5,500 | **-$12,700** |
| **Moderate** | $135 (mid-range) | ~$12,150 | ~$2,000 | ~$14,150 | $5,500 | **-$8,650** |
| **Optimistic** | $90 (low end, good creative/offer) | ~$8,100 | ~$2,000 | ~$10,100 | $5,500 | **-$4,600** |

**Reading this honestly:** at these AOV/CAC ranges, Phase 1 likely costs
more in ad spend than it returns in revenue, in all three scenarios —
consistent with the general DTC pattern above. The "sell out in a month"
goal is about proving the product and starting to build a real audience/
retargeting base, not about Phase 1 turning a profit on its own. If the
plan depends on Phase 1's *revenue* funding Phase 2, that assumption
needs to be revisited against the numbers above — Phase 2 funding likely
needs to come from the same place Phase 1's capital did (agency capital,
per `master-plan.md`'s dependency chain), not from Phase 1 sell-through.

## 12-month phased timeline (assuming things go according to plan, not best case)

| Month | Phase | What's happening | Capital needed |
|---|---|---|---|
| 1 | Phase 1 launch | 100 units (hoodie + pump cover) live, ad spend testing begins | ~$10-18k (product + ads, see scenarios above) |
| 2-3 | Phase 1 continued | Iterating on ad creative/targeting as data comes in; sell-through likely slower than 1 month in a realistic (not optimistic) case | Ongoing ad spend, ideally CAC improving as creative is proven |
| 4 | Phase 1 sold through (realistic case) | Real data now exists: actual CAC, actual conversion rate, actual repeat-purchase rate — replace every placeholder above with real numbers | — |
| 5-6 | Phase 2 prep | Vendor order placed for shorts/sweatpants/compression shirt at 75 units each (225 units) — funded per `master-plan.md`'s capital chain, not assumed from Phase 1 revenue | Phase 2 product cost at 75-unit pricing (likely better per-unit than 50-unit Phase 1, worth confirming with vendor) |
| 7-9 | Phase 2 launch | Full 5-garment line live; retargeting audience now exists from Phase 1 customers, which should meaningfully lower blended CAC vs. Phase 1's all-cold numbers | Ad spend, informed by real Phase 1 data instead of placeholder benchmarks |
| 10-12 | Steady state / reassess | Full line established; review actual unit economics against this model's placeholders and revise the next 12 months from there | — |

## What actually needs to happen before this model means anything

1. Resolve the $8k vs. desk-estimate cost gap.
2. Get real vendor quotes from the outreach already in progress
   (`domains/apparel-brand-vendor-outreach-template.md`).
3. Decide an actual retail price (this model used a placeholder).
4. Run a small, real ad test before committing the full Phase 1 budget —
   the CAC range above is a benchmark, not a guarantee for this specific
   brand/creative/audience.
