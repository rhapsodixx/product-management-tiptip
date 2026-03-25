# SatuSatu — Product Roadmap & Prioritization Framework

**Product Management · March 2026**

Translating competitive intelligence and customer journey findings into a structured, framework-driven product roadmap for the foreign visitor growth initiative.

| | |
|---|---|
| **Input** | UX Competitive Analysis (Mar 2026) |
| **Team Size** | ~10 engineers |
| **Stage** | Post-launch, pre-traction |
| **Primary Framework** | ICE + Kano |
| **Horizon Model** | Now / Next / Later |

---

## Phase 1 — Strategic Framing: Explore vs. Exploit

March's (1991) organizational learning model applied to SatuSatu's current product portfolio. Classifying bets by uncertainty and reversibility to set the right allocation.

> **Note:** March's model warns that organizations systematically over-exploit (optimizing known territory) at the expense of long-run adaptive fitness. For SatuSatu — post-launch with domestic traction but zero proven foreign visitor acquisition — the risk runs in both directions: exploiting the domestic base without building the foreign trust infrastructure, OR exploring new markets before fixing the baseline conversion that makes those new users stick. The answer is a staged rebalancing: fix-to-convert now, then explore-to-grow.

### Explore vs. Exploit Quadrant — Current SatuSatu Initiatives

| Quadrant | Items |
|---|---|
| **EXPLOIT — High Certainty** | All-inclusive pricing (proven conversion fix), Free cancellation label (industry standard) |
| **EXPLOIT — Quick Wins** | Platform social proof / booking counter display, Pre-activity automated emails, Guest / social login (remove account friction) |
| **EXPLOIT — Quick Wins (cont.)** | Search filters (price / duration / category), Google / Apple Pay (foreign payment parity) |
| **EXPLORE — High Uncertainty** | Operator verification system (new trust infrastructure), SEO / content hub (unproven for SatuSatu) |
| **EXPLORE — High Uncertainty (cont.)** | Mandarin / Hindi / Korean i18n (high impact, unproven ROI) |
| **EXPLORE — Strategic Bets** | Loyalty / credits program (new retention mechanic), Referral program (peer growth / uncertain LTV), WhatsApp-native booking (experimental channel) |

### Current Implicit Ratio (Problem)

- **Explore 65%** / **Exploit 35%**

SatuSatu is implicitly over-indexing on exploration (localization, loyalty, WhatsApp channels) before establishing the baseline trust and conversion infrastructure that makes exploration viable. New users acquired into a leaky funnel produce zero compounding value.

### Recommended Ratio (Next 6 Months)

- **Exploit 70%** / **Explore 30%**

**70% Exploit** — Fix the funnel: pricing transparency, trust signals, payment methods, search quality. These are table-stakes features where competitors have proved the pattern. Risk is low, certainty is high. **30% Explore** — Run one high-conviction new-market bet (Indian or Korean localization) in parallel as a contained spike. Do not scatter exploration across three markets simultaneously.

> **⚠ Note:** March observed that exploitation produces reliable, proximate returns while exploration produces uncertain, distant returns. For SatuSatu at ~10 engineers, the **opportunity cost of exploration is disproportionately high**: every sprint spent building a loyalty system is a sprint not spent fixing the checkout flow that currently loses foreign visitors at the payment step. The sequencing principle is: **achieve parity first, differentiate second**. Fix the funnel leaks before opening new pipes.

---

## Phase 2 — Prioritization Framework Benchmarking

Evaluating 6 frameworks against SatuSatu's constraints: ~10 engineers, limited historical data, early-stage cold-start problem, foreign visitor growth focus.

### RICE — Partially Suitable

**Formula:** (Reach × Impact × Confidence) ÷ Effort. Forces quantification across four levers; produces a single comparable score per initiative.

| Dimension | Rating |
|---|---|
| Early-stage fit | Medium |
| Data requirements | High (needs DAU/MAU for Reach) |
| Speed of execution | Slow (calibration overhead) |
| Cold-start problem | Poor (Reach needs traffic data) |
| Bias risk | Gaming via inflated Reach estimates |

**Verdict:** Powerful once SatuSatu has 90+ days of foreign visitor analytics. Premature now — Reach estimates would be fictitious without baseline foreign traffic data.

### ICE (Impact × Confidence × Ease) — Recommended Primary

**Formula:** Impact (1–10) × Confidence (1–10) × Ease (1–10). All factors scoreable without historical data — relies on team judgment and competitive benchmarks.

| Dimension | Rating |
|---|---|
| Early-stage fit | Excellent |
| Data requirements | Low (judgment + analogies) |
| Speed of execution | Fast (30-min scoring session) |
| Cold-start problem | Handles well |
| Bias risk | Recency / HiPPO bias in scoring; mitigate with diverse scorers |

**Verdict:** Best fit for SatuSatu now. Confidence dimension allows the team to discount speculative bets (localization ROI unknown) vs. proven patterns (upfront pricing = conversion lift). Calibrate using competitor benchmarks as proxies.

### WSJF (Weighted Shortest Job First) — Not Suitable

**Formula:** Cost of Delay ÷ Job Duration. Optimizes for time-value of features. Originated in SAFe enterprise PI planning contexts.

| Dimension | Rating |
|---|---|
| Early-stage fit | Poor |
| Data requirements | Very high (team velocity, CoD quantification) |
| Speed of execution | Slow (PI planning overhead) |
| Cold-start problem | Very poor |
| Bias risk | Urgency inflation; "everything is critical" |

**Verdict:** Designed for 50+ person scaled agile teams with established velocity and release trains. Overkill for a 10-person startup. Not recommended.

### Kano Model — Recommended Secondary

Classifies features as: **Basic** (expected, absence causes dissatisfaction), **Performance** (more = better), or **Delight** (unexpected, creates loyalty). Applied qualitatively using competitor benchmarks as proxies for customer surveys.

| Dimension | Rating |
|---|---|
| Early-stage fit | Good (qualitative mode) |
| Data requirements | Medium (can use competitor analysis as proxy) |
| Speed of execution | Medium |
| Cold-start problem | Manageable via competitive benchmarks |
| Bias risk | What delights early adopters may not delight mainstream |

**Verdict:** Invaluable as a _classification layer_ before ICE scoring. Prevents the team from delighting users with loyalty features while basic trust signals are absent. Forces conversation: "Is this Basic or Delight?" before scoring impact.

### MoSCoW — Communication Tool Only

Categorizes features as Must Have, Should Have, Could Have, Won't Have. Fast and stakeholder-friendly but binary — doesn't produce a ranked sequence within categories.

| Dimension | Rating |
|---|---|
| Early-stage fit | Good for communication |
| Data requirements | None |
| Speed of execution | Very fast |
| Cold-start problem | Handles well |
| Bias risk | Everything becomes "Must Have" under stakeholder pressure |

**Verdict:** Useful for board/investor communication and sprint planning buy-in. Should be derived _from_ ICE scores, not generated independently. Not a primary prioritization tool.

### Value vs. Effort Matrix — Useful Workshop Tool

Simple 2×2 quadrant: Quick Wins (high value, low effort), Major Projects, Fill-Ins, Time Wasters. Excellent for team workshops but too coarse for sequencing within quadrants.

| Dimension | Rating |
|---|---|
| Early-stage fit | Good for workshops |
| Data requirements | None |
| Speed of execution | Fastest of all |
| Cold-start problem | Excellent |
| Bias risk | "Value" undefined; defaults to intuition |

**Verdict:** Good for initial backlog triage and team alignment sessions. Too blunt for sprint-level sequencing. Use as a pre-filter before ICE scoring.

> 📊 **[Chart: Framework Suitability Radar — SatuSatu Context]** — _Visual not available in Markdown. See .html file._
>
> Scored 1–10 per dimension for a 10-person early-stage team with limited data, cold-start problem, and foreign visitor growth focus. Frameworks plotted: ICE, Kano, RICE, MoSCoW, WSJF, Value/Effort.

> **Recommendation: ICE primary + Kano classification layer**
>
> **Step 1 — Kano classification:** Before scoring, classify each initiative as Basic (must have to be competitive), Performance (more = better), or Delight (unexpected differentiator). Any Basic feature not yet built automatically enters the NOW bucket regardless of ICE score — it is a competitive liability, not a discretionary feature.
>
> **Step 2 — ICE scoring:** Score remaining Performance and Delight features on Impact × Confidence × Ease. Use competitor evidence as Confidence proxies (e.g., "Klook's free cancellation badge demonstrably reduces abandonment → Confidence: 8"). Run scoring async with Product, Engineering, and one commercial lead, then average. Flag items where scores diverge by >3 points for explicit debate.
>
> **Step 3 — Sanity check:** Apply the Explore/Exploit lens from Phase 1. If >40% of the NOW sprint is Explore, rebalance.

---

## Phase 3 — Product Roadmap Construction

ICE-scored, Kano-classified, dependency-sequenced roadmap for the foreign visitor growth initiative. Effort sized relative to a 10-person engineering team.

### Kano Classification

| Category | Description |
|---|---|
| **Basic (Table Stakes)** | Absence causes dissatisfaction and loss to competitors. Must build regardless of ICE score. These are conversion-blocking gaps where all 4 competitors have already set user expectations. |
| **Performance (More = Better)** | Users value more of these. Scored by ICE — higher scores ship first. Includes catalog depth, review density, payment methods. |
| **Delight (Differentiators)** | Unexpected features that create loyalty and word-of-mouth if present, but don't cause dissatisfaction if absent. Examples: loyalty credits, curated local guides, multilingual operator chat. |

### Sizing Definitions

#### Effort Size — Engineering Time

| Badge | Size | Definition | Examples |
|---|---|---|---|
| `XS · 1d` | Extra Small — 1 day | Config tweak, copy change, simple label/badge addition | — |
| `S · ≤1w` | Small — up to 1 week | Single feature with clear spec; minimal backend changes | — |
| `M · 2–3w` | Medium — 2 to 3 weeks | Multi-component feature; some API or data model work | — |
| `L · 4–5w` | Large — 4 to 5 weeks | Cross-functional; significant backend + frontend; third-party integration | — |
| `XL · ≥6w` | Extra Large — 6+ weeks | New platform capability; major infra or system-level change | — |

#### Priority Level — Business Necessity

| Badge | Level | Definition |
|---|---|---|
| `P1` | Must Have | Absence causes user failure or competitive disqualification. Ships regardless of ICE score. Blocks the North Star directly. |
| `P2` | Could Have | Meaningfully improves conversion, trust, or discoverability but the product works without it. Sequenced by ICE score. |
| `P3` | Nice to Have | Creates delight or opens new markets. Valuable but only scheduled after P1 and P2 are stable and proven. |

#### Effort × Priority — Decision Matrix

| Combination | Decision |
|---|---|
| `P1` + `XS · 1d` | **SHIP IMMEDIATELY** — No debate needed |
| `P1` + `S · ≤1w` | **PLAN IN SPRINT** — Highest ICE, next slot |
| `P2` + `M · 2–3w` | **SCHEDULE CAREFULLY** — Validate before committing |
| `P3` + `XL · ≥6w` | **CHALLENGE THE BET** — Spike first, commit later |

> 📊 **[Chart: Effort Scale — Engineering Days Reference]** — _Visual not available in Markdown. See .html file._
>
> Relative engineering days per T-shirt size for a single engineer. XS = 1d, S = 5d, M = 12d, L = 22d, XL = 32d.

### ICE Scoring Table — All Initiatives

| Initiative | Pillar | Kano | Impact | Confidence | Ease | ICE Score | Priority | Effort | Horizon |
|---|---|---|---|---|---|---|---|---|---|
| **All-inclusive upfront pricing** — Remove drip pricing; show total on listing card | `Trust` | Basic | 9 | 9 | 8 | **648** | `P1` | `XS · 1d` | `NOW` |
| **Free cancellation badge on listings** — Display eligible listings with clear badge | `Trust` | Basic | 8 | 9 | 9 | **648** | `P1` | `XS · 1d` | `NOW` |
| **Platform social proof counter** — "10,000+ experiences booked" on homepage | `Trust` | Basic | 7 | 9 | 9 | **567** | `P1` | `XS · 1d` | `NOW` |
| **SatuSatu Verified operator badge** — Ops vetting process + UI badge + tooltip | `Trust` | Performance | 8 | 7 | 7 | **392** | `P1` | `S · ≤1w` | `NOW` |
| **Guest checkout + Google/Apple SSO** — Remove mandatory account creation gate | `Conversion` | Basic | 9 | 8 | 6 | **432** | `P1` | `S · ≤1w` | `NOW` |
| **Google Pay + Apple Pay integration** — Foreign payment method parity | `Conversion` | Basic | 8 | 8 | 6 | **384** | `P1` | `S · ≤1w` | `NOW` |
| **Pre-activity automated emails** — T-24h and T-2h: map, checklist, operator contact | `Conversion` | Performance | 7 | 8 | 7 | **392** | `P1` | `S · ≤1w` | `NOW` |
| **Review nationality display** — Show reviewer country flags on review cards | `Trust` | Performance | 7 | 7 | 8 | **392** | `P2` | `XS · 1d` | `NEXT` |
| **SEO destination landing pages** — Bali hub + sub-pages: Nusa Penida, Ubud, etc. | `Discovery` | Performance | 9 | 6 | 5 | **270** | `P1` | `M · 2–3w` | `NEXT` |
| **Autocomplete + advanced search filters** — Price range, duration, category, instant suggestions | `Discovery` | Performance | 7 | 7 | 5 | **245** | `P2` | `M · 2–3w` | `NEXT` |
| **Post-experience email + review request** — "You might love…" + review prompt + credits tease | `Retention` | Performance | 7 | 7 | 7 | **343** | `P2` | `S · ≤1w` | `NEXT` |
| **Curated editorial Bali guides** — Top 10 lists, itineraries, activity category pages | `Discovery` | Delight | 8 | 6 | 5 | **240** | `P2` | `M · 2–3w` | `NEXT` |
| **Referral program** — "Share and both get IDR 50K credit" | `Retention` | Delight | 8 | 6 | 5 | **240** | `P2` | `M · 2–3w` | `NEXT` |
| **Korean + Hindi UI localization** — i18n: UI strings, currency (KRW/INR), UPI/Kakao Pay | `Localization` | Delight | 8 | 6 | 4 | **192** | `P2` | `L · 4–5w` | `LATER` |
| **Mandarin UI localization** — i18n: Simplified Chinese, CNY, Alipay/WeChat Pay | `Localization` | Delight | 9 | 5 | 3 | **135** | `P3` | `L · 4–5w` | `LATER` |
| **Loyalty / credits program** — Earn points on booking + review; redeem on next trip | `Retention` | Delight | 9 | 5 | 2 | **90** | `P3` | `XL · ≥6w` | `LATER` |
| **WhatsApp-native booking flow** — End-to-end booking via WhatsApp Business API | `Conversion` | Delight | 6 | 5 | 4 | **120** | `P3` | `L · 4–5w` | `LATER` |

> 📊 **[Chart: ICE Score Waterfall — Ranked Prioritization]** — _Visual not available in Markdown. See .html file._
>
> Top 13 initiatives by ICE composite score. Color bands indicate Now (green) / Next (blue) / Later (purple) horizon assignment.

### Now / Next / Later Roadmap

Horizon model chosen over quarterly planning because SatuSatu lacks reliable velocity data for time-boxing. `NOW` = 0–3 months, `NEXT` = 3–6 months, `LATER` = 6–12 months. Each horizon is reassessed and refined as learnings accumulate.

#### `NOW` — 0–3 months · Fix the funnel

| Initiative | Description | Pillar | Priority | Effort | Kano |
|---|---|---|---|---|---|
| All-inclusive upfront pricing | Remove drip pricing. Show total on listing card before checkout. | `Trust` | `P1` | `XS · 1d` | Basic |
| Free cancellation badge | Audit policies, standardize, badge all eligible listings. | `Trust` | `P1` | `XS · 1d` | Basic |
| Platform social proof counter | "X experiences booked" hero stat on homepage. | `Trust` | `P1` | `XS · 1d` | Basic |
| Guest checkout + SSO | Google/Apple login, remove mandatory account gate. | `Conversion` | `P1` | `S · ≤1w` | Basic |
| Google Pay + Apple Pay | Foreign payment method parity via Stripe/Midtrans. | `Conversion` | `P1` | `S · ≤1w` | Basic |
| SatuSatu Verified badge | Ops vetting criteria + badge UI + tooltip explanation. | `Trust` | `P1` | `S · ≤1w` | Performance |
| Pre-activity automated emails | T-24h reminder: meeting point map, checklist, operator contact. | `Conversion` | `P1` | `S · ≤1w` | Performance |

#### `NEXT` — 3–6 months · Grow and differentiate

| Initiative | Description | Pillar | Priority | Effort | Kano |
|---|---|---|---|---|---|
| Review nationality display | Show country flags on review cards to build cross-cultural proof. | `Trust` | `P2` | `XS · 1d` | Performance |
| Post-experience email + review ask | T+2h after activity: review prompt + "next experience" recommendations. | `Retention` | `P2` | `S · ≤1w` | Performance |
| SEO destination landing pages | Bali hub + 8 sub-destination pages (Ubud, Nusa Penida, etc.) with structured data. | `Discovery` | `P2` | `M · 2–3w` | Performance |
| Autocomplete + advanced search filters | Instant suggestions, price range, duration, category chips. | `Discovery` | `P2` | `M · 2–3w` | Performance |
| Curated editorial Bali guides | "Top 10 things to do in Bali" editorial pages linking to bookable experiences. | `Discovery` | `P2` | `M · 2–3w` | Delight |
| Referral program | "Invite a friend, both get IDR 50K credit." Peer-growth mechanic. | `Retention` | `P2` | `M · 2–3w` | Delight |

#### `LATER` — 6–12 months · Market expansion

| Initiative | Description | Pillar | Priority | Effort | Kano |
|---|---|---|---|---|---|
| Korean + Hindi localization | i18n: UI strings, currency display (KRW/INR), UPI + Kakao Pay integration. | `Localization` | `P2` | `L · 4–5w` | Delight |
| Mandarin localization | Simplified Chinese UI, CNY display, Alipay + WeChat Pay. Pending Korean/Hindi learnings. | `Localization` | `P3` | `L · 4–5w` | Delight |
| Loyalty / credits program | Earn credits on booking + review; redeem on next experience. Requires retention data to design correctly. | `Retention` | `P3` | `XL · ≥6w` | Delight |
| WhatsApp-native booking | WhatsApp Business API flow for Indonesian domestic repeat users. Not foreign visitors. | `Conversion` | `P3` | `L · 4–5w` | Delight |
| AI-powered "Next Experience" recommendations | Personalization engine using booking history. Requires sufficient transaction volume first. | `Retention` | `P3` | `XL · ≥6w` | Delight |

### Dependency Graph & Sequencing Rationale

**Trust Chain — must sequence in order**

`Operator vetting process (Ops)` → `Verified badge (Eng)` → `Free cancellation policy audit` → `Cancel badge on listings` → `Review nationality display`

**Conversion Chain — parallel tracks possible after auth**

`Guest checkout / SSO` → `Google/Apple Pay` → `Upfront pricing` → `Post-experience email` → `Loyalty credits`

**Discovery Chain — SEO before paid; content before localization**

`Destination landing pages` → `Curated editorial guides` → `Korean/Hindi localization` → `Mandarin localization`

> **Key sequencing principle:** Localization is expensive and produces zero return if the trust and conversion baseline is broken. A Korean-speaking user landing on a page that still has hidden fees and no cancellation policy will bounce at the same rate as an English-speaking user. Build the funnel first, then pour new traffic in. The dependency arrows above reflect this: localization is a terminal node, not a starting point.

---

## Phase 4 — North Star & Success Metrics

A full metrics framework for the product management team: North Star definition, 18 leading indicators organised by funnel stage and pillar, 9 lagging business outcomes, counter-metrics to prevent gaming, and a recommended PM review ritual.

### North Star Metric: Monthly Foreign Visitor Bookings Completed

A booking is "completed" when payment is confirmed AND the activity date has passed — i.e., the experience actually happened, not just that a reservation was made. This closes the loop on fulfilment quality, not just transactional volume.

**Why not GBV?** A single high-value private tour skews GBV without proving product-market fit. **Why not Revenue?** Revenue lags too far behind product decisions — it reflects Q-1 choices, not current sprint impact. **Why not Total Bookings?** Bundling domestic and foreign bookings hides the specific growth thesis this roadmap is built around. Foreign Visitor Bookings Completed is the earliest verifiable signal that all four funnel levers — discovery, trust, conversion, and delivery — are working simultaneously. As volume matures (>500 bookings/month), this graduates to **Foreign Visitor GBV per month**.

### Leading vs. Lagging Indicators

| Type | Who Tracks It | Role |
|---|---|---|
| **Leading Indicators** | PM team, weekly | Team-controllable inputs. They move _before_ the North Star moves. If a leading indicator is trending wrong, the team has time to course-correct within the same sprint. **Diagnostic**: they tell you _where_ in the funnel to look. |
| **Lagging Indicators** | Leadership, monthly/quarterly | Business outcome metrics. They confirm whether your leading indicator bets paid off — but they move slowly and cannot be directly acted upon. **Confirmatory**: they tell you _whether_ the strategy is working. |

### Metrics Tree — Full Funnel Hierarchy

> 📊 **[Chart: Metrics Tree — Full Funnel Hierarchy]** — _Visual not available in Markdown. See .html file._
>
> Team inputs (leading) ladder through four funnel stages — Acquisition (blue), Evaluation/Trust (amber), Conversion (green), Retention (purple) — to the North Star, then confirm as business outcomes (lagging). Each colour band represents one funnel stage.

**Funnel Stages → North Star → Lagging Outcomes:**

- **Acquisition** (blue): New foreign visitor sessions/wk · Organic search impressions (foreign) · % traffic from IN/AU/KR/CN → **Foreign session volume**
- **Evaluation/Trust** (amber): Listing trust score avg · Avg review count / listing · Detail page dwell time → **Evaluation→intent rate**
- **Conversion** (green): Checkout step drop-off rate · Account creation exit rate · Payment success rate → **Checkout conversion rate**
- **Retention** (purple): Post-experience review rate · Referral link share rate → **Repeat booking rate**
- All four funnel stages → **⭐ North Star: Foreign Bookings Completed / Month**
- North Star → Lagging business outcomes (dashed)

### Leading Indicators — What PM Reviews Weekly

18 metrics the PM team owns directly. Organised by funnel stage. Each metric maps to a specific roadmap initiative, has a named owner, a review cadence, and a threshold that triggers action.

| Metric | Definition | Funnel Stage | Roadmap Driver | Target / Alert Threshold | Cadence | Tool | Owner |
|---|---|---|---|---|---|---|---|
| **New foreign visitor sessions / week** | Unique sessions from non-Indonesian IPs (GA4 geo dimension) | Acquisition | SEO pages, paid social | Baseline → +20% MoM after SEO launch | Weekly | GA4 | Marketing / PM |
| **Organic search impressions (foreign)** | Google Search Console impressions filtered to IN / AU / KR / CN | Acquisition | SEO destination pages | Alert if <5% growth after 8 weeks of publish | Weekly | Search Console | Marketing |
| **% traffic from target geographies** | Sessions from IN + AU + KR + CN ÷ total sessions | Acquisition | Geo-targeted ads, SEO | Target: >15% of total sessions by M6 | Weekly | GA4 | Marketing / PM |
| **Search-to-detail-page CTR** | Listing detail page views ÷ internal search result views | Acquisition | Autocomplete, filters, listing thumbnails | Alert if <12%; target ≥18% | Weekly | GA4 + custom events | Product |
| **Listing trust score (avg)** | % of active listings with: free cancel badge + verified badge + ≥5 reviews + photo gallery | Evaluation | Verified badge, cancel badge, review ask | Target: 60% of listings score ≥3/4 by M3 | Weekly | Internal dashboard | Product + Ops |
| **Avg review count per listing** | Total reviews across all active listings ÷ listing count | Evaluation | Post-experience review email | Alert if avg <3; target ≥8 by M6 | Weekly | Internal DB | Product |
| **Detail page dwell time (foreign)** | Avg time on listing detail page, foreign IP segment only | Evaluation | Trust badges, review display, photo UX | Alert if <45s; target ≥90s | Weekly | GA4 + Hotjar | Product |
| **Detail-to-intent rate ("Book Now" tap)** | Unique "Book Now" clicks ÷ listing detail page views · foreign segment | Evaluation | Free cancel badge, upfront pricing, trust signals | Alert if <8%; target ≥14% | Weekly | GA4 events | Product |
| **Checkout funnel drop-off by step** | Abandonment rate at each of: date selection / package / auth / payment | Conversion | Guest checkout, upfront pricing, payment methods | Auth step: alert if >50% exit; target <20% | Weekly | GA4 funnel exploration | Product + Eng |
| **Account creation exit rate** | % of foreign users who leave at account creation gate vs. proceeding | Conversion | Guest checkout + SSO (NOW initiative) | Alert if >60%; target <15% post-SSO launch | Weekly | GA4 + session replay | Product |
| **Payment success rate by country** | Successful payments ÷ payment attempts, segmented by user country | Conversion | Google/Apple Pay integration | Alert if any country <80%; target ≥92% for all markets | Weekly | Payment gateway (Midtrans / Stripe) | Eng + Product |
| **Google/Apple Pay adoption rate** | % of foreign checkouts where G/A Pay is selected as payment method | Conversion | Google/Apple Pay integration | Target: ≥20% of foreign checkouts within 4 weeks of launch | Weekly | Payment gateway events | Eng + Product |
| **Overall checkout conversion rate (foreign)** | "Book Now" click → payment confirmed ÷ "Book Now" clicks · foreign segment | Conversion | All NOW initiatives together | Baseline first, then target +30% lift by M3 | Weekly | GA4 funnel | Product |
| **Pre-activity email open rate** | Opened ÷ delivered for T-24h reminder emails · foreign bookers | Fulfilment | Pre-activity automated email | Alert if <35%; target ≥55% | Weekly | Email platform (Mailchimp / Brevo) | Product + Marketing |
| **Day-of no-show rate (foreign)** | % of foreign bookings where operator reports no-show | Fulfilment | Pre-activity reminders, meeting point clarity | Alert if >5%; target <2% | Weekly | Operator ops report | Ops + Product |
| **Post-experience review submission rate** | Reviews submitted ÷ completed foreign bookings within 72h of activity | Retention | Post-experience email + review ask | Alert if <10%; target ≥25% by M6 | Weekly | Internal DB + email platform | Product |
| **Referral link share rate** | Referral links generated ÷ completed bookings | Retention | Referral program (NEXT horizon) | Target: ≥5% of completers share within 48h | Weekly | Referral platform / internal | Marketing + Product |
| **Return visit rate (foreign)** | % of foreign visitors who return to site/app within 30 days of first visit | Retention | Post-experience email, referral, loyalty | Alert if <5%; target ≥12% by M6 | Weekly | GA4 cohort analysis | Product |

### Lagging Indicators — What Leadership Reviews Monthly / Quarterly

Business outcome metrics. Confirmatory, not diagnostic. When a lagging metric is off-track, the PM team investigates leading indicators to find the cause — not the lagging metric itself.

| Metric | Definition & Formula | Cadence | Target (M12) | Leading Indicators That Drive It | Alert Signal |
|---|---|---|---|---|---|
| **⭐ Foreign Visitor Bookings Completed / Month** (North Star) | Confirmed bookings from non-ID users where activity date has passed | Monthly | Define baseline in M1; target 3× by M12 | All 18 leading indicators above | Two consecutive months of decline → war room |
| **Foreign Visitor GBV (monthly)** | Sum of transaction value of all completed foreign bookings · IDR | Monthly | Proportional to North Star × avg order value | Checkout conversion rate, payment success rate | GBV growing slower than booking count → AOV erosion |
| **Net Revenue from Foreign Visitors** | Foreign GBV × blended take rate (platform + service fees) | Monthly | Track absolute growth; no % target until M6 | Checkout conversion, payment success | Take rate declining → pricing model review |
| **Foreign Visitor NPS** | (Promoters% − Detractors%) from post-experience survey, foreign segment only | Quarterly | ≥40 by M12 (Klook benchmark: ~50) | Trust score, dwell time, no-show rate, review score | NPS <20 → qualitative review of open-text comments |
| **Foreign Visitor CAC** | Total acquisition spend (paid + content) ÷ new foreign bookers in period | Quarterly | Track only; reduce via organic after SEO matures | Organic sessions, referral rate, conversion rate | CAC rising while bookings flat → paid channel inefficiency |
| **Foreign Visitor LTV (modelled)** | Avg GBV per booking × estimated bookings per customer lifetime × net margin | Quarterly | LTV:CAC ≥ 3:1 by M12 | Repeat booking rate, review rate, referral rate | LTV:CAC <1.5 → retention investment required |
| **Foreign Visitor Repeat Booking Rate** | % of foreign customers who complete ≥2 bookings within any 12-month window | Quarterly | ≥8% by M12 (baseline near 0 today) | Return visit rate, post-experience email, referral | Flat at 0% after M6 → loyalty program accelerated |
| **% Total Revenue from Foreign Visitors** | Foreign net revenue ÷ total platform net revenue | Monthly | >20% by M12 | All acquisition + conversion leading indicators | Below 5% at M6 → strategy recalibration |
| **Avg Review Score — foreign visitors** | Mean star rating from reviews submitted by non-ID users | Monthly | ≥4.3 / 5.0 consistently | Trust score, no-show rate, operator quality | Drops below 4.0 → ops quality audit triggered |

### Counter-Metrics — Preventing Gaming

Every metric that is tracked will eventually be gamed — intentionally or through over-optimisation. For each major leading indicator, track a counter-metric that signals the optimisation has gone too far.

**Checkout conversion rate ↑**
- **Risk:** Hiding information, using dark patterns (fake countdown timers, fake "only 2 left"), or forcing upsells that inflate conversion but destroy satisfaction.
- **Counter-metric:** Dispute rate + post-booking cancellation rate within 24 hours. If conversion goes up but same-day cancellations increase, the UX is coercive, not genuinely improving.

**Review count per listing ↑**
- **Risk:** Incentivising reviews too aggressively produces low-quality or biased reviews — inflating the number while degrading the signal value.
- **Counter-metric:** Average review length (words) and NPS score from the same cohort. If review count rises but avg length drops below 15 words and NPS doesn't improve, review quality is declining.

**Foreign session volume ↑**
- **Risk:** Paid acquisition campaigns can artificially inflate session counts with low-intent traffic that bounces immediately, wasting budget and distorting the North Star signal.
- **Counter-metric:** Foreign session-to-detail-page rate (engagement quality). If sessions rise but <20% reach a listing detail page, traffic quality is low.

**Referral share rate ↑**
- **Risk:** Users share referral links to friends who create fake accounts to claim credits — referral fraud that inflates apparent acquisition while generating no real revenue.
- **Counter-metric:** Referred booking completion rate (referred users who actually complete and attend an experience, not just sign up). Target: >40% of referred signups complete a booking within 60 days.

### Recommended PM Review Ritual

> **Monday morning (15 min) — Leading indicator pulse:** Open the GA4 foreign visitor dashboard. Check: new foreign sessions, checkout funnel drop-off by step, payment success rate by country, detail-to-intent rate. Flag any metric outside threshold. If two or more are red, escalate to eng sync.
>
> **Sprint review (bi-weekly) — Initiative impact check:** For each shipped initiative, review its primary leading indicator 2 weeks post-launch. Example: if guest checkout shipped 2 weeks ago, show account creation exit rate before vs. after. No impact after 2 weeks = investigate or iterate.
>
> **Monthly (1 hour) — North Star + lagging review:** Pull the North Star number (Foreign Bookings Completed). Plot it on a trend chart. Then pull GBV, revenue %, and NPS. Write a 3-sentence narrative: "This month the North Star moved X because [leading indicator]. The lagging risk is [Y]. Next month we are betting on [Z] to move it." Share with leadership.
>
> **Quarterly (half-day) — Metrics audit:** Review whether current leading indicators still predict the North Star. Retire metrics that have become stable and no longer discriminate. Add new leading indicators as new initiatives launch (e.g., once referral program ships, add referral conversion rate to the weekly pulse).

---

## Phase 5 — Risk & Trade-off Analysis

For the top 5 NOW-horizon initiatives: key assumptions, failure modes, lightweight validation approach, and ownership model.

### 1. All-Inclusive Upfront Pricing

`ICE: 648` · `XS · 1d` · `NOW`

| | |
|---|---|
| **Key Assumptions** | Hidden fees are the primary cause of checkout abandonment for foreign visitors. Showing the total upfront will not reduce perceived affordability — users will still complete once they see the full number. |
| **Biggest Risk** | Foreign visitors see the "true" price (Base + Platform + Service) and perceive SatuSatu as more expensive than competitor listings — even if net price is similar. Price perception anchoring effect could lower conversion rather than improve it. |
| **Validation Approach** | Run A/B test: 50% of foreign visitors see current flow (fees at checkout), 50% see all-inclusive price on listing card. Primary metric: checkout completion rate. Secondary: average order value. Run for 4 weeks or 500 foreign sessions per variant. |
| **Ownership (RACI-lite)** | **R** Product — design spec · **A** Engineering — pricing logic · **C** Finance — fee structure review · **I** Marketing — messaging update |

### 2. Guest Checkout + Google/Apple SSO

`ICE: 432` · `S · ≤1w` · `NOW`

| | |
|---|---|
| **Key Assumptions** | Mandatory account creation is the primary abandonment trigger at the "Book Now" step for foreign visitors — not price, not trust, not payment method. Guest users will complete booking without an account. |
| **Biggest Risk** | Guest bookers cannot receive post-experience review requests or loyalty benefits, reducing review density and repeat bookings. Also: without accounts, customer support cannot identify users with booking disputes — ops overhead increases. |
| **Validation Approach** | Before building: add session recording (Hotjar/FullStory) to the account creation gate and measure drop-off %. If >40% of foreign visitors exit at that step, confirm assumption is correct. Then build SSO (lower friction than full guest checkout). Gate guest checkout for 3 months post-SSO to measure SSO's impact first. |
| **Ownership (RACI-lite)** | **R** Engineering — OAuth implementation · **A** Product — flow design & spec · **C** Security — token handling review · **I** Ops — support flow update |

### 3. SatuSatu Verified Operator Badge

`ICE: 392` · `S · ≤1w` · `NOW`

| | |
|---|---|
| **Key Assumptions** | Foreign visitors notice and interpret operator quality badges as a meaningful trust signal. SatuSatu can define and enforce a vetting standard that meaningfully differentiates operators — and can withhold the badge from underperforming operators without revenue impact. |
| **Biggest Risk** | Badge inflation: under operator/commercial pressure, the badge gets distributed too broadly and becomes meaningless (cf. Airbnb's "Superhost" dilution). Alternatively, if withholding the badge from popular operators causes supply-side churn, the business overrides the trust mechanism. |
| **Validation Approach** | Define vetting criteria first (Ops leads this in week 1–2). Apply badge retroactively to top 20% of operators by review score + dispute rate. Run a 6-week heatmap study on listing pages: do users click badges? Does time-on-page increase? Survey 20 foreign visitors on what the badge means to them before launch. |
| **Ownership (RACI-lite)** | **R** Ops — vetting criteria & process · **A** Product — badge UX design · **C** Engineering — data model · **I** Marketing — badge communication |

### 4. SEO Destination Landing Pages (NEXT)

`ICE: 270` · `M · 2–3w` · `NEXT`

| | |
|---|---|
| **Key Assumptions** | SatuSatu can rank competitively for Bali activity keywords against Klook, GetYourGuide, Viator, and TripAdvisor within 6 months. Organic foreign traffic will convert at a meaningful rate once it arrives. |
| **Biggest Risk** | Keyword competition for "Bali activities" is dominated by platforms with domain authority 10x SatuSatu's. Pages may not rank within the 6-month window, making this a long-horizon investment misclassified as NEXT. Content production becomes ongoing operational cost without clear payback period. |
| **Validation Approach** | Start with 3 long-tail pages: "best Nusa Penida tour from Bali," "Mount Batur sunrise trek booking," "Bali cooking class Ubud." These have lower SERP competition. Measure organic impressions at 60 and 90 days via Google Search Console. If impressions are growing, scale. If flat, pivot to backlink strategy before building more pages. |
| **Ownership (RACI-lite)** | **R** Marketing — content strategy & writing · **A** Product — page template design · **C** Engineering — structured data/schema · **I** Ops — experience data accuracy |

### 5. Korean + Hindi Localization (LATER)

`ICE: 192` · `L · 4–5w` · `LATER`

| | |
|---|---|
| **Key Assumptions** | Korean and Indian travelers will meaningfully prefer a native-language SatuSatu over an English-language Klook with far greater catalog depth. Language is the conversion barrier — not catalog size, reviews, or brand recognition. |
| **Biggest Risk** | Full i18n is expensive (string management, ongoing translation ops, QA per locale). If Korean/Indian users abandon because of catalog depth or trust gaps — not language — localization investment produces no conversion lift. Misattributing the root cause is the highest risk. |
| **Validation Approach** | Before building: run a 4-week geo-targeted campaign in Korea and India driving traffic to the current English site. Measure: (1) do they arrive? (2) do they convert? If conversion rate among Korean/Indian visitors is <0.5% — investigate qualitative reason before building localization. Use a no-code translation layer (e.g., Weglot) as a 4-week test proxy for true i18n investment. Validate conversion lift before committing to full build. |
| **Ownership (RACI-lite)** | **R** Engineering — i18n framework · **A** Product — locale strategy · **C** Marketing — translation vendor · **I** Ops — local payment setup |

### The Central Trade-off: Conversion vs. Expansion

> **Note:** Every rupiah and every sprint hour spent on localization (Later) is a sprint not spent closing the trust and conversion gaps (Now) that make any new traffic — localized or not — convert. The roadmap above is deliberately conservative on expansion: run 70% of engineering capacity at the funnel (pricing, auth, payment, trust) for the first quarter, then redirect toward growth once the baseline conversion rate is validated. A 5% improvement in checkout conversion from foreign visitors creates more GBV than a new language market with the same broken checkout flow.

---

_SatuSatu Product Roadmap Report · Framework-Driven Prioritization for Foreign Visitor Growth · March 2026_

_Input: UX Competitive Analysis (Mar 2026) · Frameworks: ICE primary + Kano classification layer · Horizon model: Now / Next / Later · Team constraint: ~10 engineers_
