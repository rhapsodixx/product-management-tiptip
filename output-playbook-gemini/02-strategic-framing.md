# 02 — Strategic Framing: Explore vs. Exploit

> **Sequential Thinking MCP**: Used to classify all initiatives into Explore/Exploit quadrants and reconcile cross-source conflicts.

---

## The Theory: March's (1991) Organizational Learning Model

James March's seminal model frames all organizational activity as a balance between two modes:

| Mode        | Definition                   | Characteristics                                                                    | Risk                                                                                  |
| ----------- | ---------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Exploit** | Optimizing known territory   | Proven patterns, competitors already do it, low uncertainty, fixes existing funnel | Over-exploit → stagnation. Product becomes a "fast follower" with no differentiation. |
| **Explore** | Venturing into new territory | Uncertain ROI, building new capabilities, market expansion, unproven mechanics     | Over-explore → resource scatter. Team chases novelty before validating the base.      |

> **March's Key Warning**: Organizations systematically over-exploit at the expense of long-run adaptive fitness. But for SatuSatu — post-launch with domestic traction but **zero proven foreign visitor acquisition** — the risk runs in both directions.

### The SatuSatu Dilemma

- **Over-exploit risk**: Polishing the domestic booking flow without building foreign trust infrastructure = optimizing a product that foreigners never see
- **Over-explore risk**: Launching Korean localization, loyalty programs, and WhatsApp booking before fixing the checkout flow = pouring new users into a leaky funnel

> **The Answer**: Staged rebalancing. **Fix-to-convert now, then explore-to-grow.** A 5% improvement in checkout conversion from foreign visitors creates more GBV than a new language market with the same broken checkout flow.

---

## Explore/Exploit Quadrant — All SatuSatu Initiatives

> Every initiative from both K2 (product roadmap) and K4 (product pipeline CSV) classified by uncertainty and strategic intent.

### EXPLOIT — High Certainty (Proven Patterns)

Competitors have already validated these. Absence is a competitive liability, not a feature decision.

| Initiative                          | Source  | Squad  | Pillar     | Kano        | Status                |
| ----------------------------------- | ------- | ------ | ---------- | ----------- | --------------------- |
| Free cancellation badge on listings | K2      | —      | Trust      | Basic       | NOW                   |
| Platform social proof counter       | K2 + K4 | PAYCOM | Trust      | Basic       | Product Requirement   |
| Guest checkout + Google/Apple SSO   | K2 + K4 | PAYCOM | Conversion | Basic       | Testing (SSO phase 1) |
| Google Pay + Apple Pay integration  | K2      | —      | Conversion | Basic       | NOW                   |
| Locally Curated badge enhancement   | K2      | —      | Trust      | Performance | NOW                   |
| Pre-activity automated emails       | K2      | —      | Conversion | Performance | NOW                   |
| Review nationality display          | K2      | —      | Trust      | Performance | NEXT                  |
| Product Detail Improvements         | K4      | CONTEX | Conversion | Performance | Released              |
| External Review                     | K4      | CONTEX | Trust      | Performance | On Dev                |
| CS Widget                           | K4      | CONTEX | Conversion | Performance | Released              |
| WhatsApp Notifications              | K4      | CONTEX | Conversion | Performance | Released              |
| Package Options                     | K4      | CONTEX | Conversion | Performance | Next Pickup           |
| My Booking                          | K4      | CONTEX | Conversion | Performance | To Prioritize         |

### EXPLOIT — Quick Wins (Small Effort, Known Value)

| Initiative                           | Source | Squad  | Pillar      | Status              |
| ------------------------------------ | ------ | ------ | ----------- | ------------------- |
| Home Page Curated Exp Update         | K4     | PAYCOM | Discovery   | Released            |
| Multiple Image Banners               | K4     | PAYCOM | Discovery   | Released            |
| Custom Sections                      | K4     | PAYCOM | Discovery   | Released            |
| Voucher in Home Page                 | K4     | PAYCOM | Conversion  | Product Requirement |
| Pop Up without Param                 | K4     | PAYCOM | Conversion  | Product Requirement |
| Move Sign up/in CTA to top           | K4     | PAYCOM | Conversion  | —                   |
| Move from email pass to OTP based    | K4     | PAYCOM | Conversion  | —                   |
| Improve UX from booking to signup    | K4     | PAYCOM | Conversion  | —                   |
| One card per row results             | K4     | PAYCOM | Discovery   | —                   |
| Sort by biggest discount             | K4     | PAYCOM | Discovery   | —                   |
| Standardize locale naming convention | K4     | PAYCOM | Infra       | On Dev              |
| Inform CS when new catalog created   | K4     | CONTEX | Ops         | Released            |
| Predefined Form for Visitor          | K4     | CONTEX | Ops         | Released            |
| Variant multi merchant               | K4     | CONTEX | Ops         | On Dev              |
| Retool Rating & Total Sold           | K4     | CONTEX | Ops         | On Dev              |
| Product Setup Improvements           | K4     | CONTEX | Ops         | Next Pickup         |
| Analytics in CH                      | K4     | CONTEX | Measurement | Next Pickup         |
| Blog Tracker                         | K4     | PAYCOM | Content     | Released            |
| Wordpress Improvements - In line CTA | K4     | CONTEX | Content     | Released            |

### EXPLORE — High Uncertainty (New Capabilities)

Unproven for SatuSatu. Uncertain ROI. Require validation before full commitment.

| Initiative                             | Source  | Squad  | Pillar       | Kano        | Status        | Risk                                                           |
| -------------------------------------- | ------- | ------ | ------------ | ----------- | ------------- | -------------------------------------------------------------- |
| I8n Translations                       | K4 + K2 | PAYCOM | Localization | Delight     | On Dev        | High effort (L), unproven conversion lift for foreign visitors |
| I8n Payment (incl. 2C2P integration)   | K4      | PAYCOM | Localization | Delight     | On Dev        | New payment gateway, uncertain adoption                        |
| Korean + Hindi UI localization         | K2      | —      | Localization | Delight     | LATER         | Full i18n is expensive; language may not be the barrier        |
| Mandarin UI localization               | K2      | —      | Localization | Delight     | LATER         | Chinese market dominated by Trip.com                           |
| SEO destination landing pages          | K2 + K4 | CONTEX | Discovery    | Performance | Design        | Keyword competition from Klook/GYG/Viator                      |
| Implement locale dan hreflang di blog  | K4      | CONTEX | Discovery    | —           | To Prioritize | i18n infra required                                            |
| Destination page                       | K4      | CONTEX | Discovery    | Performance | Design        | SEO effectiveness unproven                                     |
| Autocomplete + advanced search filters | K2 + K4 | CONTEX | Discovery    | Performance | On Dev        | Engineering complexity (M)                                     |
| Discover Filter & Sort                 | K4      | CONTEX | Discovery    | Performance | On Dev        | Same as above                                                  |

### EXPLORE — Strategic Bets (Large Investment, Potential Differentiation)

High-risk, high-reward. Only pursue once Exploit base is stable.

| Initiative                             | Source | Pillar     | Kano        | Status        | Risk                                                    |
| -------------------------------------- | ------ | ---------- | ----------- | ------------- | ------------------------------------------------------- |
| Loyalty / credits program              | K2     | Retention  | Delight     | LATER         | XL effort; needs transaction volume to design correctly |
| Referral program                       | K2     | Retention  | Delight     | NEXT          | Uncertain LTV from referred users                       |
| WhatsApp-native booking flow           | K2     | Conversion | Delight     | LATER         | Experimental channel; L effort                          |
| Curated editorial Bali guides          | K2     | Discovery  | Delight     | NEXT          | Ongoing content ops cost                                |
| Implement llms.txt (one off)           | K4     | Discovery  | —           | Released      | Novel AI/SEO experiment                                 |
| Implement llms.txt (dynamic)           | K4     | Discovery  | —           | —             | Ongoing AI infrastructure                               |
| Post-experience email + review request | K2     | Retention  | Performance | NEXT          | New retention mechanic                                  |
| Product Detail Recommended Products    | K4     | Conversion | —           | To Prioritize | Recommendation engine is new capability                 |
| Upsell other recommended attractions   | K4     | Conversion | —           | —             | New revenue mechanic, uncertain value                   |
| Guest Purchase + My Booking for Guest  | K4     | Conversion | —           | To Prioritize | XL effort; complex auth architecture                    |

---

## Explore/Exploit Quadrant Visualization

```mermaid
quadrantChart
    title Explore vs. Exploit — SatuSatu Initiative Map
    x-axis "EXPLOIT (Proven)" --> "EXPLORE (Uncertain)"
    y-axis "Low Impact" --> "High Impact"
    quadrant-1 "Strategic Bets"
    quadrant-2 "High-Certainty Wins"
    quadrant-3 "Exploit Quick Wins"
    quadrant-4 "Uncertain Experiments"
    "Free Cancel Badge": [0.1, 0.92]
    "Guest Checkout SSO": [0.15, 0.88]
    "Google/Apple Pay": [0.15, 0.85]
    "Social Proof Counter": [0.12, 0.8]
    "Curated Badge Enhance": [0.2, 0.78]
    "Pre-activity Emails": [0.18, 0.72]
    "External Review": [0.22, 0.7]
    "SEO Landing Pages": [0.65, 0.85]
    "Korean/Hindi i18n": [0.75, 0.82]
    "Loyalty Credits": [0.85, 0.88]
    "Referral Program": [0.7, 0.75]
    "Autocomplete/Filters": [0.55, 0.7]
    "Editorial Guides": [0.65, 0.65]
    "Mandarin i18n": [0.8, 0.72]
    "WhatsApp Booking": [0.82, 0.5]
    "Homepage Improvements": [0.1, 0.4]
    "Blog Infra": [0.15, 0.35]
    "Ops Tooling": [0.08, 0.3]
    "llms.txt": [0.72, 0.3]
```

---

## Current vs. Recommended Ratio

### How We Measured

| Layer                          | Explore            | Exploit            | Ratio     | Assessment                                        |
| ------------------------------ | ------------------ | ------------------ | --------- | ------------------------------------------------- |
| K2 — Strategic Roadmap         | 10 items (58%)     | 7 items (42%)      | 58/42     | ⚠ Over-exploring at the strategic level           |
| K4 — Tactical Backlog          | 10 items (28%)     | 25 items (72%)     | 28/72     | ✅ Healthy — team instinctively builds Exploit     |
| **Combined (All Active Work)** | **20 items (36%)** | **32 items (64%)** | **36/64** | ⚠ Close to target, but explore is still above 30% |

> **Key Insight**: The tactical backlog (K4) is **naturally correcting** the strategic over-exploration in K2. The team instinctively builds Exploit features (homepage, auth, booking flow, ops) while the roadmap document emphasizes Explore (localization, loyalty). This is actually good — the team should **formalize this instinct into policy**.

### Recommended Ratio (Next 6 Months)

```mermaid
pie title "Target Sprint Allocation (Next 6 Months)"
    "Exploit (70%)" : 70
    "Explore (30%)" : 30
```

| Allocation      | What It Means                                                                                                                                          | Examples                                                                                       |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------- |
| **70% Exploit** | Fix the funnel: trust signals, payment methods, search quality, auth friction. Table-stakes features where competitors have proved the pattern. | Free cancel badge, SSO, Google/Apple Pay, Locally Curated badge enhancement, pre-activity emails |
| **30% Explore** | Run **one** high-conviction new-market bet as a contained spike. Do not scatter exploration across three markets simultaneously.                       | SEO landing pages OR Korean/Hindi localization — not both in the same quarter                  |

### Startup Stage Ratios — Where SatuSatu Sits

| Stage                                    | Typical Ratio                 | Reasoning                                             |
| ---------------------------------------- | ----------------------------- | ----------------------------------------------------- |
| Pre-product/market fit                   | 80% Explore / 20% Exploit     | Need to find what works                               |
| **Post-launch, pre-traction** ← SatuSatu | **70% Exploit / 30% Explore** | Product exists; need to fix conversion before scaling |
| Growth stage                             | 50% Exploit / 50% Explore     | Base is proven; time to differentiate                 |
| Mature product                           | 70% Exploit / 30% Explore     | Optimize core; run incremental experiments            |

---

## How to Track Explore/Exploit Ratio

1. **Tag every backlog item** with `Explore` or `Exploit` in the backlog tracker (Page 08, add column: `Explore/Exploit`)
2. **Track trend over time**: Plot Explore % per sprint on a simple line chart. Ensure the average stays within 25–35% Explore.

---

## The Central Sequencing Principle

> **Achieve parity first, differentiate second.**
>
> Every rupiah and every sprint hour spent on localization (Later) is a sprint not spent closing the trust and conversion gaps (Now) that make any new traffic — localized or not — convert. A Korean-speaking user landing on a page with missing trust signals and no cancellation policy will bounce at the same rate as an English-speaking user.
>
> Fix the funnel leaks before opening new pipes.

### The Opportunity Cost Argument

For a **~10 engineer team**, the opportunity cost of exploration is disproportionately high:

| Scenario                            | Sprint Investment                    | Expected Impact                                                                              |
| ----------------------------------- | ------------------------------------ | -------------------------------------------------------------------------------------------- |
| Fix checkout conversion (Exploit)   | 2 sprints                            | +15–25% foreign checkout conversion → compound effect on ALL future foreign sessions         |
| Build Korean localization (Explore) | 4–5 sprints                          | Korean users arrive → hit same broken checkout flow → same low conversion → 4 sprints wasted |
| **Correct sequence**                | Fix checkout THEN build localization | Korean users arrive → hit functional checkout → convert → localization ROI is realized       |

> **The math is clear**: Exploit first, Explore second. The funnel multiplies the value of every subsequent investment.

