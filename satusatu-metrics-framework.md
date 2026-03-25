# SatuSatu — Product Metrics Framework & Audit

**Product Analytics · March 2026**

A full audit of existing business/marketing metrics, a North Star definition, a 25-metric leading & lagging framework, GTM implementation specs per tool, and a causal relationship map — built for the product team to own independently of marketing.

- `OpenPanel` · Product Source of Truth
- `GA4` via GTM · Acquisition & SEO
- `Meta Pixel` · Meta Attribution
- OOH Triangulation Methods

---

## Task 1: Audit of Existing Metrics

What the current business/marketing metric set reveals, where it is blind, which are misattributed, and which tool in the current stack can close each gap.

### Tool Stack Overview

**OpenPanel** — Source of truth for in-product behavioral data. Mixpanel-equivalent: event tracking, funnels, retention cohorts, user properties. All key behavioral events flow here. Product analytics home.

**GA4 via GTM** — Preferred for SEO, acquisition analytics, and Google Ads attribution. GTM is the deployment container for all client-side tags. Connects to Search Console. Looker Studio reporting layer.

**Meta Pixel** — Scoped to Meta campaign attribution only. On-site for conversion events, audience building (lookalikes, retargeting), and ROAS reporting in Meta Ads Manager. Not a general analytics source.

### Metrics Audit Table

| # | Metric | Currently Owned By | Type | What It Reveals Well | Blind Spots (What Product Cannot See) | Product Should Co-Own? | Tool to Fill Gap |
|---|--------|--------------------|------|----------------------|---------------------------------------|------------------------|------------------|
| 1 | **ROAS** — Return on Ad Spend | Marketing | `Lagging` | Whether paid channels return revenue above spend, in aggregate | Post-acquisition user quality. High-ROAS campaigns may acquire low-LTV users who never return. ROAS can be inflated by organic users misattributed via click-last-touch. | Shadow — yes | `OpenPanel` channel cohort: completion rate + D30 repeat rate by acquisition source |
| 2 | **Ad Impressions** | Marketing | `Leading` | Ad reach and audience coverage across Meta & Google | Zero product signal. Impressions reveal nothing about what users do on the platform. Creative fatigue invisible. | No | N/A — marketing-only signal |
| 3 | **Ad Clicks / CTR** | Marketing | `Leading` | Ad creative and audience targeting engagement rate | Post-click behavior is entirely invisible. High CTR + high bounce = misleading ad. Product needs post-click engagement quality, not just click volume. | Shadow — yes | `GA4` Landing page engagement rate (engaged sessions ÷ sessions) segmented by campaign |
| 4 | **Landing Page Views** | Marketing | `Leading` | Traffic volume successfully delivered by paid campaigns to the site | Bounce rate, scroll depth, time-on-page, exit intent — all missing. A pageview with immediate exit is counted identically to a 5-minute deep engagement session. | Co-own quality layer | `GA4` Engagement rate + scroll events on paid landing pages |
| 5 | **Visit Home** — Homepage sessions | Shared | `Leading` | Site-level traffic volume; entry point into the acquisition funnel | Traffic quality, new vs. returning split, first-session intent signals. A spike from a low-intent audience looks identical to high-intent foreign visitor traffic. | Yes — PM primary | `OpenPanel` first-session event sequence: what do new users do in session 1? |
| 6 | **Catalog Detail Views** — Listing page views | Shared | `Leading` | Discovery interest exists — users are engaging with specific attraction listings | Which categories are browsed, search vs. browse source, scroll depth per listing, photo engagement, how listing quality correlates with next actions. Aggregate count hides all of this. | Yes — PM primary | `OpenPanel` `listing_viewed` event with category, source, photo_count, review_count, scroll_depth params |
| 7 | **Initiate Payment** | Shared | `Leading` | Purchase intent exists — user entered the checkout flow | Step-level drop-offs within checkout (date selection → pax count → contact → payment method). Payment failures. Form errors. Which payment methods are abandoned vs. completed. All invisible. | Yes — PM primary | `OpenPanel` per-step checkout events (step 1–4 individually, not just initiation) + `payment_error` event |
| 8 | **Paid (Booking Completed)** | Shared | `Lagging` | Transaction count — the core conversion event is being captured | Cancellation rate within 24h (inflates count), time-to-book from first visit, channel attribution breakdown, which listing categories convert best, foreign vs. domestic split. | Yes — NSM input | `OpenPanel` + `GA4` + `Meta Pixel` — all 3 must fire in parallel via GTM multi-tag |
| 9 | **Revenue** | Business | `Lagging` | Total revenue; broad financial health signal | Per-channel LTV, organic vs. paid revenue contribution split, refund impact on net revenue, category revenue mix. Revenue growth can mask whether we're acquiring high-LTV or low-LTV users. | Co-own with shared reporting | `GA4` ecommerce events + `OpenPanel` user-level revenue by cohort |
| 10 | **Basket Size** — Avg order value | Business | `Lagging` | Average transaction value; product price positioning signal | AOV difference between foreign vs. domestic visitors. Category mix driving AOV. Multi-booking behavior. Upsell success. A single average obscures all distribution shape. | Co-own with segmentation | `OpenPanel` segment by visitor_type and category |
| 11 | **DAU / MAU** — Engagement ratio | Business | `Leading` | Platform stickiness ratio; broad engagement health check | What actions drive return visits. Whether DAU growth is from bookers or browsers. Cohort-level retention (do users who booked return?). Activity type per session. All hidden inside a single ratio. | Yes — product owns retention | `OpenPanel` retention cohort segmented by `has_booked=true` user property; D7/D30 return rates |

### Critical Visibility Gaps — Zero Instrumentation Today

Signal areas where product currently has no events, no data, and therefore no ability to diagnose or improve.

> **⚠ Critical Gap: Activation Black Box**
>
> No metric captures what new users do in their first session beyond raw page view counts. No "first meaningful action" event exists. Product cannot distinguish a curious browser from a high-intent foreign visitor about to book.
>
> Fix → OpenPanel: `listing_viewed` + `checkout_initiated` filtered to session_number=1

> **⚠ Critical Gap: Search Behavior Void**
>
> Search queries, zero-result rate, and search-to-listing click rate are entirely invisible. Product cannot know what users are looking for, whether the catalog satisfies demand, or where discovery fails completely.
>
> Fix → OpenPanel + GA4: `search_performed` event with query, results_count, zero_results boolean

> **⚠ High Priority: Checkout Micro-Friction**
>
> Between "Initiate Payment" and "Paid" there is a complete blackout. Payment failures, form errors, date-picker abandonment, and payment method preferences are all invisible — likely where the largest recoverable revenue loss lives.
>
> Fix → OpenPanel: one event per checkout sub-step (1–4) + `payment_error` event with error_code

> **⚠ High Priority: OOH Attribution Dark Matter**
>
> Out-of-home ad spend (billboards, transit) has zero digital signal. Whether OOH drives branded search, direct traffic, or incremental bookings is completely unknown. Budget allocation decisions are made blind.
>
> Fix → GA4 + Search Console: branded search volume delta as proxy + OpenPanel geo-segmented cohort

> **ℹ Moderate: Supply Quality Signals**
>
> Listing completeness, photo count, review volume, and operator response rate are invisible at the product analytics layer. Product cannot correlate supply quality with conversion rate or identify which listings are drag factors.
>
> Fix → OpenPanel: `listing_viewed` with photo_count, review_count, avg_rating as event properties

> **ℹ Moderate: Retention & Repeat Behavior**
>
> DAU/MAU as a single ratio hides whether repeat visits come from bookers or browsers. No cohort analysis exists. Product cannot distinguish users who booked once and returned from those who browsed and left permanently.
>
> Fix → OpenPanel: retention cohort with `has_booked` user property segmentation, D7 / D30 return rates

> 📊 **[Chart: Conversion Funnel — Estimated Baseline vs. OTA Benchmark]** — _Illustrative drop-off rates per stage. Exact SatuSatu numbers require OpenPanel funnel configuration. OTA benchmark sourced from Phocuswright and Klook/KKday public data. Visual not available in Markdown. See .html file._

---

## Task 2: North Star Metric

A single metric that product owns, reflects the core value exchange, is actionable by product decisions, and is measurable in the current stack.

## North Star Metric: Weekly Qualified Bookings Completed

> `COUNT(booking_id WHERE status='confirmed' AND NOT cancelled_within_24h=true)` — rolling 7-day window

**Tools:** `OpenPanel` — Primary Owner · `GA4` — Cross-validation · `Meta Pixel` — Channel Attribution

Count of unique booking transactions in any rolling 7-day window where (1) payment is confirmed by the payment gateway and (2) the booking has not been cancelled within 24 hours of placement. Measured weekly as an absolute count and tracked as a trend. The 24-hour cancellation filter removes accidental, duplicate, and low-quality bookings — making this metric resistant to gaming. The 7-day rolling window provides enough signal to detect trends while remaining responsive to product changes deployed in any given sprint.

### Why This Metric Works

- **Captures core value exchange** — a customer discovers and commits to a real-world experience
- **Product-actionable** — search quality, listing trust, checkout friction, and payment methods all directly move this number
- **Resistant to gaming** — requires real payment + 24h cancellation filter; cannot be inflated by accidental or test transactions
- **Weekly cadence** — fast enough for sprint feedback loops; less noisy than daily; more actionable than monthly revenue
- **Volume-compound** — grows with both conversion rate improvement AND traffic growth, rewarding work across the full funnel

### Counter-Metrics to Track Alongside NSM

Prevent optimization at the expense of quality:

- **Cancellation rate within 48h** — if NSM rises but cancellations spike, growth is hollow
- **Average booking value** — if NSM grows via heavy discounting, revenue quality falls
- **D7 return visit rate** — if NSM grows but users don't return, we're not building a product people come back to
- **Organic branded search volume** — sanity check that growth isn't purely from paid budget increases

### Rejected North Star Candidates

### Rejected: Revenue (Total GMV)

**Why rejected:** Revenue is a pure lagging indicator — it confirms what already happened. It is gameable via discounting (revenue rises while margin collapses). It is owned by finance, not product, and no product decision moves it without first moving bookings as an intermediate step. Revenue is the business outcome that results from improving the NSM — it should not be the NSM itself.

### Rejected: Booking Conversion Rate (Visit → Paid %)

**Why rejected:** Conversion rate is a ratio, not a count. It can improve while total bookings fall (e.g., if low-intent traffic is filtered out). It does not reward platform growth — 3% conversion on 100 visitors is worse than 2.5% on 10,000 visitors. This is a critical diagnostic metric that lives below the NSM and should be tracked as a leading indicator, not as the north star itself.

### Rejected: DAU / MAU Ratio

**Why rejected:** Engagement frequency without value exchange. A user who browses the catalog daily without booking scores identically to one who booked twice last week. For a transactional marketplace, engagement without conversion is not a viable north star. This metric is already tracked by the business team and adds no product-specific ownership.

### Rejected: Monthly Active Bookers

**Why rejected:** Monthly cadence is too slow for a product team running weekly sprints. A 4-week lag between product changes and metric movement makes it impossible to diagnose what worked. Weekly Qualified Bookings Completed provides identical directional signal at 4× the resolution. Monthly Active Bookers is appropriate for executive reporting but not as an operational product north star.

### Rejected: Session Count / Unique Visitors

**Why rejected:** Traffic volume is a marketing input, not a product outcome. Product does not control SEO rankings or ad budgets directly. Optimizing for traffic without measuring what that traffic does leads to vanity growth. Traffic belongs in the acquisition input layer — it feeds the NSM but is not the NSM.

---

## Task 3: Leading & Lagging Metrics Framework

25 metrics across two axes: indicator type (Leading / Lagging) and priority tier (Must-Have / Nice-to-Have), covering all product signal areas.

> **ℹ Note:** `Must-Have` metrics are non-negotiable — product cannot make informed decisions without them. `Nice-to-Have` metrics enrich decision-making but are non-critical at current maturity. `Leading` = behavioral input signals (early, actionable). `Lagging` = outcome confirmations (late, explanatory).

| # | Metric Name | Signal Area | Type | Priority | Definition | Why It Matters for SatuSatu | Owner | Tool |
|---|-------------|-------------|------|----------|------------|-----------------------------|-------|------|
| 1 | **Checkout Initiation Rate** | Conversion | `Leading` | `Must-Have` | % of listing-view sessions where user clicks Book Now and enters checkout step 1 | The gap between discovery interest and purchase intent. The single most actionable conversion lever product owns — every trust, UX, and pricing decision affects it directly. | Product | `OpenPanel` |
| 2 | **Payment Abandonment Rate** | Conversion | `Leading` | `Must-Have` | % of checkout_initiated events NOT followed by booking_completed within 30 minutes | Quantifies revenue lost inside the payment flow. Foreign visitors face currency, payment method, and UPI friction — this metric makes the size of that loss visible for the first time. | Product | `OpenPanel` |
| 3 | **Search-to-Catalog CTR** | Discovery | `Leading` | `Must-Have` | % of search queries resulting in at least one listing detail page click | Measures search relevance and result quality. A low rate means users search, find nothing compelling, and leave — a supply gap or search algorithm failure that blocks the entire funnel. | Product | `OpenPanel` |
| 4 | **Catalog Engagement Depth** | Discovery | `Leading` | `Must-Have` | Average number of unique listing detail pages viewed per session | Indicates discovery quality and consideration depth. Sessions with 1 listing view are low-intent; 4+ views signals high purchase consideration. Predicts checkout initiation rate. | Product | `OpenPanel` |
| 5 | **Activation Rate** | Activation | `Leading` | `Must-Have` | % of new users (first session) who view ≥2 listings AND fire checkout_initiated within session 1 | Predicts whether new traffic converts to purchase intent. A falling activation rate means top-of-funnel quality is declining or the first-session experience is broken before the funnel even starts. | Product | `OpenPanel` |
| 6 | **D7 Return Visit Rate** | Retention | `Leading` | `Must-Have` | % of new users who return to the platform within 7 days of their first visit | Leading predictor of repeat booking. Foreign visitors planning Bali trips browse across 3–5 sessions over 2–6 weeks. D7 return means the platform was memorable enough to come back to. | Product | `OpenPanel` |
| 7 | **Search Zero-Result Rate** | Discovery | `Leading` | `Must-Have` | % of search queries that return 0 results | Signals supply gaps and search quality failures. Foreign visitors search in English — a zero-result response to "snorkeling Bali" or "Ubud cooking class" is a direct, measurable revenue loss event. | Product | `OpenPanel` + `GA4` |
| 8 | **Paid Ad Landing Bounce Rate** | Acquisition | `Leading` | `Must-Have` | % of paid traffic sessions that exit without viewing any listing detail page | Measures acquisition quality vs. ad targeting precision. A high rate means marketing is buying the wrong audience or landing pages are misaligned with ad creative — a shared product/marketing problem. | Shared | `GA4` |
| 9 | **★ Weekly Qualified Bookings Completed** — North Star Metric | Conversion | `Lagging` | `Must-Have` | Confirmed bookings not cancelled within 24h; rolling 7-day count | This IS the north star. Every product decision ultimately must move this number. Reviewed weekly in product rituals as the single most important product health signal. | Product | `OpenPanel` + `GA4` + `Meta Pixel` |
| 10 | **Booking Conversion Rate** | Conversion | `Lagging` | `Must-Have` | (Qualified bookings ÷ unique sessions) × 100; rolling 30-day | Summarizes overall funnel health in one ratio. Monitor for trend direction; when it moves, use leading indicators to diagnose where in the funnel the change originated. | Shared | `GA4` + `OpenPanel` |
| 11 | **30-Day Repeat Booking Rate** | Retention | `Lagging` | `Must-Have` | % of users who complete ≥2 confirmed bookings within a rolling 30-day window | Proves the platform has retention value beyond a one-time transaction. Critical for LTV calculation, organic referral growth, and justifying any loyalty or retention-focused initiative. | Product | `OpenPanel` |
| 12 | **Booking Cancellation Rate** | Conversion | `Lagging` | `Must-Have` | % of confirmed bookings cancelled within 48h of placement | Counter-metric to the NSM. Prevents gaming via accidental or low-confidence bookings. Also flags UX trust issues — a user who books and immediately cancels experienced something that broke confidence. | Product | `OpenPanel` + Backend |
| 13 | **Average Booking Value** | Conversion | `Lagging` | `Must-Have` | Mean IDR value per confirmed transaction (rolling 30-day) | Revenue efficiency independent of volume. Counter-metric: if NSM grows but ABV falls, growth may be driven by heavy discounting or a shift toward lower-value listings. | Shared | `GA4` + `OpenPanel` |
| 14 | **Organic Branded Search Volume** — OOH Proxy | Brand/OOH | `Lagging` | `Must-Have` | Weekly branded query volume for ["satusatu", "satu satu bali", "satusatu.com"] via GA4 + Search Console integration | The only available proxy for OOH (billboard, transit) campaign effectiveness. A statistically significant spike in branded search during OOH flight dates proves brand awareness lift. | Shared | `GA4` + Search Console |
| 15 | **Wishlist / Save Rate** | Discovery | `Leading` | `Nice-to-Have` | % of listing views resulting in a wishlist or save action | Intent signal below checkout threshold. Useful for designing retargeting segments and understanding consideration behavior in multi-session booking journeys. | Product | `OpenPanel` |
| 16 | **Photo View Rate** | Supply Quality | `Leading` | `Nice-to-Have` | % of listing views where user views ≥3 photos in the gallery | Proxy for listing visual quality. High photo engagement correlates with higher checkout initiation. Identifies under-performing listings with weak visual presentation. | Product | `OpenPanel` |
| 17 | **Filter Usage Rate** | Discovery | `Leading` | `Nice-to-Have` | % of search sessions using at least one filter (price, duration, category, rating) | Indicates user sophistication and catalog depth. Low filter usage may mean filters aren't discoverable, aren't relevant to the catalog, or users don't trust the catalog enough to filter it. | Product | `OpenPanel` |
| 18 | **Avg Time on Listing Page** | Discovery | `Leading` | `Nice-to-Have` | Mean seconds spent on a listing detail page per session | Weak proxy for listing copy and photo quality. Most useful as a relative metric in A/B tests on listing page redesigns rather than as an absolute benchmark. | Product | `OpenPanel` |
| 19 | **Review Submission Rate** | Trust | `Leading` | `Nice-to-Have` | % of completed bookings where user submits a review within 14 days post-activity | Builds social proof supply. More reviews → more trust signals → higher checkout initiation for future visitors. A compounding trust flywheel that product can accelerate with post-booking email design. | Product | `OpenPanel` |
| 20 | **Listing Completeness Score** | Supply Quality | `Leading` | `Nice-to-Have` | % of active listings with ≥5 photos, ≥200-char description, price set, and ≥1 confirmed review | Supply quality KPI. Incomplete listings suppress conversion and harm SEO ranking. Direct Ops responsibility but product must monitor for correlation with conversion rate. | Shared | Backend + `OpenPanel` |
| 21 | **Multi-Destination Browse Rate** | Discovery | `Leading` | `Nice-to-Have` | % of sessions browsing listings across ≥2 distinct destination tags (e.g., Ubud + Nusa Penida) | Platform stickiness and intent depth signal. High multi-destination browsing = user planning a multi-day itinerary = higher potential LTV per user across multiple future bookings. | Product | `OpenPanel` |
| 22 | **Platform Average Rating** | Trust | `Lagging` | `Nice-to-Have` | Mean star rating across all reviewed listings (rolling 30-day) | Platform trust health. A declining average rating is a leading indicator of increasing cancellation rate and word-of-mouth degradation. Requires review data from backend. | Shared | `OpenPanel` + Backend |
| 23 | **CAC by Channel** | Acquisition | `Lagging` | `Nice-to-Have` | Total channel spend ÷ new booking users acquired via that channel (monthly) | Attribution efficiency for budget allocation decisions. Requires manual merge of marketing spend data with GA4/OpenPanel conversion attribution — not fully automatable in current stack. | Shared | `GA4` + Marketing data |
| 24 | **90-Day Revenue per User** | Retention | `Lagging` | `Nice-to-Have` | Total booking revenue attributed to a user cohort within 90 days of their first booking | LTV proxy for early-stage product. Required to evaluate whether acquisition investment is justified and to compare channel quality beyond just CAC. | Shared | `OpenPanel` + `GA4` |
| 25 | **NPS Score** | Sentiment | `Lagging` | `Nice-to-Have` | Promoter % − Detractor % from post-activity survey triggered T+2 days after activity date | Broad customer satisfaction signal. Requires a survey tool (Typeform, Delighted) not in the current stack — flag as new capability if prioritized in a future quarter. | Product | Survey tool — new capability needed |

> 📊 **[Chart: Must-Have Metric Coverage by Signal Area & Tool]** — _Number of Must-Have metrics per product pillar, broken down by primary tracking tool ownership. Shows where each tool bears the most instrumentation burden. Visual not available in Markdown. See .html file._

---

## Task 4: Tracking Implementation Guide

Per Must-Have metric: tool ownership, GTM setup method, exact event specification, dashboard home, measurement cadence, cross-tool firing notes, and OOH proxy methods.

> **ℹ Note: OOH Attribution Triangulation — General Method**
>
> Out-of-home (billboard, transit) has no direct digital signal. Use this triangulation approach across all campaigns:
>
> - **Branded search delta (GA4 + Search Console):** Establish a 4-week pre-campaign branded search baseline for terms ["satusatu", "satu satu bali"]. Monitor weekly during OOH flight. A statistically significant spike (>20% above baseline) indicates brand awareness lift attributable to OOH.
> - **Direct traffic baseline delta (GA4):** Compare Default Channel = Direct sessions week-over-week during OOH flight vs. same period prior year or control period.
> - **Geo-segmented cohort (OpenPanel):** Create a user cohort of sessions from cities/regions where OOH placements are active. Compare activation rate, catalog engagement depth, and booking conversion rate vs. control cities with no OOH placement.
> - **Timing correlation:** Map weekly NSM (bookings) and branded search volume against OOH flight calendar. Sustained co-movement is evidence of OOH contribution even without deterministic attribution.

### Implementation Card 01: Weekly Qualified Bookings Completed (NSM)

**Tools:** `OpenPanel` · `GA4` · `Meta Pixel`

The most critical event in the stack. Must fire to all three tools simultaneously via GTM multi-tag setup. One trigger, three tags.

**Step 1 — dataLayer push (site code, on booking confirmation screen)**

```javascript
window.dataLayer.push({
  event: 'booking_completed',
  booking_id:     order.id,           // 'TXN-20260315-001'
  listing_id:     order.listingId,
  listing_name:   order.listingName,
  category:       order.category,     // 'adventure' | 'cultural' | 'culinary'
  value:          order.totalIDR,     // 450000
  currency:       'IDR',
  payment_method: order.paymentMethod,// 'google_pay' | 'credit_card' | 'bank_transfer'
  visitor_type:   user.segment,       // 'foreign' | 'domestic'
  user_country:   user.countryCode    // 'IN' | 'AU' | 'KR' | 'CN'
});
```

**Step 2a — GTM Tag: OpenPanel (Custom HTML, Trigger: booking_completed)**

```javascript
if (window.op) {
  op('track', 'booking_completed', {
    booking_id:   '{{DL - booking_id}}',
    listing_id:   '{{DL - listing_id}}',
    category:     '{{DL - category}}',
    value:        {{DL - value}},
    visitor_type: '{{DL - visitor_type}}'
  });
}
```

**Step 2b — GTM Tag: GA4 Event (type: GA4 Event, Event: purchase)**

```javascript
// GTM GA4 Event tag — parameters:
transaction_id: {{DL - booking_id}}
value:          {{DL - value}}
currency:       IDR
items: [{
  item_id:       {{DL - listing_id}},
  item_name:     {{DL - listing_name}},
  item_category: {{DL - category}},
  price:         {{DL - value}},
  quantity:      1
}]
```

**Step 2c — GTM Tag: Meta Pixel (Custom HTML, same trigger)**

```javascript
fbq('track', 'Purchase', {
  value:        {{DL - value}},
  currency:     'IDR',
  content_ids:  ['{{DL - listing_id}}'],
  content_type: 'product',
  num_items:    1
});
```

| Field | Value |
|-------|-------|
| GTM Setup | 1 trigger → 3 tags in parallel. Custom Event trigger name: "booking_completed". |
| Dashboard Home | OpenPanel Events view + GA4 Monetization report + Meta Ads Manager |
| Cadence | `Daily` monitoring · `Weekly` NSM review |
| Cross-tool Note | All 3 must fire within the same GTM container execution to ensure consistent attribution windows |

---

### Implementation Card 02: Checkout Initiation Rate

**Tools:** `OpenPanel` · `GA4`

Fires when user clicks the primary "Book Now" CTA on a listing detail page and enters checkout step 1 (date selection). Track per listing to identify high-intent vs. low-intent supply.

**dataLayer push (on Book Now click)**

```javascript
window.dataLayer.push({
  event:        'checkout_initiated',
  listing_id:   listing.id,
  listing_name: listing.name,
  category:     listing.category,
  value:        listing.priceIDR,
  currency:     'IDR',
  visitor_type: user.segment,
  source:       referrer // 'search' | 'homepage' | 'direct' | 'recommendation'
});
```

**OpenPanel tag (GTM Custom HTML)**

```javascript
op('track', 'checkout_initiated', {
  listing_id:   '{{DL - listing_id}}',
  category:     '{{DL - category}}',
  value:        {{DL - value}},
  visitor_type: '{{DL - visitor_type}}',
  source:       '{{DL - source}}'
});
```

**GA4 tag (GTM GA4 Event — begin_checkout)**

```javascript
// Event name: begin_checkout
// Parameters:
currency: IDR
value: {{DL - value}}
items: [{ item_id: {{DL - listing_id}},
           item_name: {{DL - listing_name}} }]
```

| Field | Value |
|-------|-------|
| GTM Trigger | Custom Event: "checkout_initiated" fired on Book Now click via dataLayer |
| Dashboard Home | OpenPanel Funnel: listing_viewed → checkout_initiated |
| Cadence | `Daily` |
| Metric Calculation | checkout_initiated sessions ÷ listing_viewed sessions × 100 |

---

### Implementation Card 03: Payment Abandonment Rate

**Tools:** `OpenPanel`

Computed metric — no new event beyond Card 2 is strictly required. Track checkout step sub-events to diagnose WHERE in the checkout flow abandonment occurs. Also track payment_error for gateway failures.

**Per-step checkout event (fire on each step transition)**

```javascript
// Fire on each checkout sub-step
// step: 1=date-select, 2=pax-count, 3=contact-info, 4=payment
function trackCheckoutStep(step, stepName) {
  window.dataLayer.push({
    event:        'checkout_step',
    step_number:  step,
    step_name:    stepName,
    listing_id:   cart.listingId,
    value:        cart.totalIDR,
    visitor_type: user.segment
  });
}

// Payment error event (on gateway failure response)
window.dataLayer.push({
  event:          'payment_error',
  error_code:     response.errorCode,  // 'insufficient_funds' | 'card_declined'
  payment_method: user.selectedMethod,
  listing_id:     cart.listingId,
  value:          cart.totalIDR
});
```

**OpenPanel funnel configuration (no extra tag needed)**

```javascript
// In OpenPanel: create a 5-step funnel
// Step 1: listing_viewed
// Step 2: checkout_initiated
// Step 3: checkout_step (step_number=3 contact-info)
// Step 4: checkout_step (step_number=4 payment)
// Step 5: booking_completed
// Abandonment = step N without step N+1 within 30 min window
```

| Field | Value |
|-------|-------|
| GTM Trigger | Custom Event: "checkout_step" and "payment_error" — each needs a GTM OpenPanel tag |
| Dashboard Home | OpenPanel Funnel report — step-level drop-off percentages |
| Cadence | `Daily` |
| Metric Calculation | 1 − (booking_completed ÷ checkout_initiated) within 30-min session window |

---

### Implementation Card 04: Booking Conversion Rate

**Tools:** `GA4` · `OpenPanel`

Computed ratio — no new events needed. Requires consistent session identification between GA4 (for session count) and OpenPanel (for booking count). Cross-tool session correlation via GTM variable.

**Session correlation enrichment (fire on session start)**

```javascript
// Pass GA4 session ID to OpenPanel for cross-tool join
// GTM Variable: {{GA - Session ID}} (built-in GA4 variable)
// Fire on All Pages trigger

window.dataLayer.push({
  event:      'session_start_enriched',
  ga_session: '{{GA - Session ID}}',  // for cross-tool correlation
  is_new_user: {{GA - New User}},
  visitor_type: user.segment
});

// OpenPanel user property enrichment (Custom HTML tag)
op('set', {
  ga_session_id: '{{DL - ga_session}}',
  visitor_type:  '{{DL - visitor_type}}',
  is_new_user:   {{DL - is_new_user}}
});
```

| Field | Value |
|-------|-------|
| Dashboard Home | GA4 Explore: sessions (denominator) + OpenPanel: bookings (numerator) → Looker Studio join |
| Cadence | `Weekly` |
| Metric Calculation | qualified_bookings_7d ÷ unique_sessions_7d × 100 |
| GTM Note | All Pages trigger. GA4 Session ID is a GTM built-in variable — enable under Variables in GTM. |

---

### Implementation Card 05: Search-to-Catalog CTR

**Tools:** `OpenPanel` · `GA4`

Requires two new events: search_performed (on search execution) and listing_clicked_from_search (on result click). The ratio between these two events in the same session defines the metric.

**Event 1: search_performed**

```javascript
window.dataLayer.push({
  event:           'search_performed',
  search_query:    query.text,        // 'snorkeling bali'
  results_count:   results.length,    // 0 triggers zero_result alert
  zero_results:    results.length === 0,
  filters_applied: activeFilters.join(','), // 'category:adventure,price:lt500k'
  visitor_type:    user.segment,
  ui_language:     i18n.locale        // 'en' | 'id' | 'zh'
});
```

**Event 2: listing_clicked_from_search**

```javascript
window.dataLayer.push({
  event:        'listing_clicked_from_search',
  listing_id:   result.id,
  listing_name: result.name,
  position:     result.rank,          // 1-indexed position in results
  search_query: currentQuery,
  visitor_type: user.segment
});
```

**OpenPanel tag (Custom HTML, trigger on each event)**

```javascript
// Tag 1 fires on 'search_performed', Tag 2 on 'listing_clicked_from_search'
op('track', '{{Event}}', {
  query:         '{{DL - search_query}}',
  results_count: {{DL - results_count}},
  zero_results:  {{DL - zero_results}},
  listing_id:    '{{DL - listing_id}}',  // empty for search_performed
  position:      {{DL - position}}        // empty for search_performed
});
```

| Field | Value |
|-------|-------|
| Dashboard Home | OpenPanel Funnel: search_performed → listing_clicked_from_search (per-session) |
| Cadence | `Daily` (zero_results) · `Weekly` (CTR trend) |
| GA4 Note | GA4 built-in site_search event captures search_term automatically if you configure Search Settings in GA4 Admin — enable this as a zero-instrumentation fallback for search_query tracking. |
| Alert | Set OpenPanel alert: zero_results rate > 10% triggers Slack notification to PM |

---

### Implementation Card 06: Catalog Engagement Depth

**Tools:** `OpenPanel`

Track listing_viewed with rich supply-quality properties. OpenPanel counts unique listing_viewed events per session to compute average depth. The supply quality properties (photo_count, review_count) enable correlation analysis.

**listing_viewed event (fire on listing detail page load)**

```javascript
window.dataLayer.push({
  event:         'listing_viewed',
  listing_id:    listing.id,
  listing_name:  listing.name,
  category:      listing.category,    // 'adventure' | 'cultural' | 'culinary'
  price_idr:     listing.priceIDR,
  photo_count:   listing.photos.length,
  review_count:  listing.reviewCount,
  avg_rating:    listing.avgRating,   // 4.7
  source:        session.entrySource, // 'search' | 'homepage' | 'direct' | 'share'
  visitor_type:  user.segment,
  session_depth: session.listingViewCount + 1 // nth listing in this session
});
```

**OpenPanel tag (GTM Custom HTML)**

```javascript
op('track', 'listing_viewed', {
  listing_id:    '{{DL - listing_id}}',
  category:      '{{DL - category}}',
  price_idr:     {{DL - price_idr}},
  photo_count:   {{DL - photo_count}},
  review_count:  {{DL - review_count}},
  avg_rating:    {{DL - avg_rating}},
  source:        '{{DL - source}}',
  session_depth: {{DL - session_depth}}
});
```

| Field | Value |
|-------|-------|
| Dashboard Home | OpenPanel: AVG(COUNT(listing_viewed) per session) — session-level aggregation |
| Cadence | `Weekly` |
| Supply Correlation | Use photo_count and avg_rating as event properties to segment: do high-photo listings drive deeper catalog exploration? |
| GTM Note | Also fire GA4 view_item event from this same trigger for ecommerce funnel completeness in GA4 Explore. |

---

### Implementation Card 07: Activation Rate

**Tools:** `OpenPanel`

Computed metric in OpenPanel using user property session_number. Activation = new user (session_number=1) who fires listing_viewed ≥2 times AND checkout_initiated in the same session. No additional events — just user property enrichment.

**Session-start enrichment (All Pages trigger, runs first)**

```javascript
// GTM Variable: {{GA - Session Number}} (built-in, enable in GTM Variables)
window.dataLayer.push({
  event:          'session_enriched',
  session_number: {{GA - Session Number}},
  is_new_user:    {{GA - New User}},    // GTM built-in boolean
  visitor_type:   user.segment,
  ui_language:    i18n.locale
});

// OpenPanel user property tag (fires on session_enriched)
op('set', {
  session_number: {{DL - session_number}},
  visitor_type:   '{{DL - visitor_type}}',
  ui_language:    '{{DL - ui_language}}'
});
```

**OpenPanel activation funnel configuration**

```javascript
// In OpenPanel → Funnels:
// Filter: session_number = 1 (first session only)
// Step 1: listing_viewed (count ≥ 2, same session)
// Step 2: checkout_initiated
// Conversion = users reaching Step 2 / users in Step 1
// Activation Rate = this funnel's overall conversion %
```

| Field | Value |
|-------|-------|
| Dashboard Home | OpenPanel Funnels — filter cohort to session_number=1 new users |
| Cadence | `Weekly` cohort comparison |
| GTM Note | session_enriched fires on every page. Use GTM's built-in GA Session Number variable — requires GA4 to be configured first. |
| Segmentation | Compare activation rate by visitor_type (foreign vs. domestic) and ui_language to find highest-intent audience segments. |

---

### Implementation Card 08: D7 Return Visit Rate

**Tools:** `OpenPanel`

Computed in OpenPanel's built-in retention cohort report. No new events needed — requires only that users are consistently identified across sessions. Critical: anonymous users must get a persistent anonymous ID from the OpenPanel SDK (set on first visit, stored in localStorage).

**User identification on every session (GTM All Pages tag)**

```javascript
// For logged-in users: use user_id
// For anonymous: OpenPanel SDK assigns persistent anon ID automatically
// Ensure OpenPanel SDK initializes BEFORE any other tags

// If user is logged in, identify with consistent ID
if (user.isLoggedIn) {
  op('identify', user.id, {
    email:        user.email,
    visitor_type: user.segment,  // 'foreign' | 'domestic'
    country:      user.country,
    created_at:   user.createdAt
  });
}
// Anonymous users: SDK auto-manages device-level ID via localStorage
// No action needed — but ensure SDK loads on every page
```

**OpenPanel retention cohort setup (no events needed)**

```javascript
// In OpenPanel → Retention:
// Cohort event:   session_start (or 'page_view' if session_start not tracked)
// Return event:   session_start
// Cohort window:  Weekly (group users by week of first visit)
// Retention day:  Day 7
// D7 Return Rate = % of Week N cohort who return on Day 7 ± 1 day
// Segment by:     visitor_type to compare foreign vs. domestic retention
```

| Field | Value |
|-------|-------|
| Dashboard Home | OpenPanel → Retention → Day 7 column per weekly cohort |
| Cadence | `Weekly` cohort review |
| GTM Note | OpenPanel SDK should be initialized in GTM as the very first tag — use Tag Sequencing to ensure it fires before all other OpenPanel tags. |
| Privacy Note | Anonymous ID is device-local only. Incognito sessions will generate a new ID — accepted limitation for anonymous retention tracking. |

---

### Implementation Card 09: 30-Day Repeat Booking Rate

**Tools:** `OpenPanel`

Computed metric — no new events needed beyond booking_completed (Card 01). OpenPanel's user-level event history enables a "users with ≥2 booking_completed events in rolling 30 days" query. Requires consistent user identification from Card 08.

**OpenPanel user-level query (no implementation — configuration only)**

```javascript
// In OpenPanel → People / Users:
// Filter: COUNT(booking_completed) >= 2 in last 30 days
// Denominator: COUNT(users WHERE COUNT(booking_completed) >= 1 in last 30 days)
// Repeat Rate = (users with ≥2 bookings) / (all bookers) × 100

// For monthly Looker Studio reporting:
// Export via OpenPanel API → join with GA4 revenue data
// Endpoint: POST /api/v1/query with event=booking_completed
// Group by: user_id, date_range=last_30_days
// Aggregate: COUNT(events) per user → filter >= 2
```

**Booking_completed event enrichment for repeat tracking**

```javascript
// Add is_repeat_booker property to booking_completed (Card 01)
// Check before pushing the booking_completed dataLayer event:
const hasBookedBefore = await api.getUserBookingCount(user.id) > 0;
window.dataLayer.push({
  event:            'booking_completed',
  // ... all existing properties ...
  is_repeat_booker: hasBookedBefore,
  booking_sequence: userBookingCount + 1  // 1=first, 2=second, etc.
});
```

| Field | Value |
|-------|-------|
| Dashboard Home | OpenPanel People segment + monthly Looker Studio dashboard |
| Cadence | `Monthly` |
| Backend Note | booking_sequence requires a server-side lookup of prior booking count — low overhead; one DB query before confirmation page render. |
| Segmentation | Compare repeat rate by visitor_type — foreign visitors may have lower 30-day repeat rate but higher 90-day rate due to trip planning cadence. |

---

### Implementation Card 10: Booking Cancellation Rate

**Tools:** `OpenPanel` · `Backend Required`

Partially trackable client-side (if cancellation UI exists in-app), but the authoritative signal requires server-side instrumentation. Flag as the one Must-Have metric requiring backend priority.

**Client-side: cancellation request submission (if in-app flow)**

```javascript
// On cancellation form submit
window.dataLayer.push({
  event:               'booking_cancelled',
  booking_id:          booking.id,
  listing_id:          booking.listingId,
  cancellation_reason: form.reason,  // 'change_of_plans' | 'found_cheaper' | 'operator_issue'
  hours_since_booking: booking.hoursSincePlacement,
  days_before_activity: booking.daysUntilActivity,
  visitor_type:        user.segment
});
// OpenPanel tag fires from this dataLayer event (same pattern as Card 01)
```

**Server-side: backend pushes to OpenPanel API when booking status changes**

```javascript
// Node.js / backend example
// Trigger: booking status webhook or DB status change listener
await fetch('https://api.openpanel.dev/track', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'openpanel-client-id': process.env.OP_CLIENT_ID,
    'openpanel-client-secret': process.env.OP_SECRET
  },
  body: JSON.stringify({
    type:       'track',
    payload: {
      name:     'booking_cancelled',
      userId:   booking.userId,
      properties: {
        booking_id:   booking.id,
        reason:       booking.cancelReason,
        hours_after:  booking.hoursSincePlacement,
        is_within_24h: booking.hoursSincePlacement < 24
      }
    }
  })
});
```

> **⚠ Critical Gap:** Backend instrumentation required — the client-side event alone cannot capture operator-initiated cancellations or gateway-triggered voids. This is the single Must-Have metric requiring engineering backend work. Flag as high-priority in the next sprint.

| Field | Value |
|-------|-------|
| Dashboard Home | OpenPanel Events: booking_cancelled / booking_completed ratio — rolling 7-day |
| Cadence | `Weekly` |

---

### Implementation Card 11: Average Booking Value

**Tools:** `GA4` · `OpenPanel`

Partially tracked today as "Basket Size" — but without proper GA4 ecommerce schema, Looker Studio reports are limited. Implement the standard GA4 purchase event to unlock GA4 Monetization reports and enable Looker Studio ecommerce dashboards.

**GA4 purchase event is already firing from Card 01, Step 2b. Add these segmentation properties to enrich ABV analysis:**

```javascript
// Extend Card 01 booking_completed dataLayer push with:
window.dataLayer.push({
  event: 'booking_completed',
  // ... existing properties ...
  listing_tier: listing.priceTier,   // 'budget' | 'mid' | 'premium'
  pax_count:    booking.paxCount,     // 2
  price_per_pax: booking.totalIDR / booking.paxCount
});

// In GA4: Monetization → Ecommerce Purchases
// Average Purchase Revenue = Revenue / Transactions (auto-computed)
// Segment by item_category and visitor_type (user properties)

// In OpenPanel: AVG(value) WHERE event='booking_completed'
// Segment by: category, visitor_type, listing_tier
```

| Field | Value |
|-------|-------|
| Dashboard Home | GA4 Monetization → Average Purchase Revenue. OpenPanel: custom metric AVG(value) |
| Cadence | `Weekly` |
| Counter-metric | Track alongside NSM — if NSM grows but ABV falls by >15%, investigate discount or supply mix changes |
| Segment Priority | Foreign vs. domestic ABV delta is critical — foreign visitors expected to book higher-value experiences. Monitor for divergence. |

---

### Implementation Card 12: Organic Branded Search Volume (OOH Proxy)

**Tools:** `GA4` · `Search Console`

No GTM implementation required. Data comes from Google Search Console linked to GA4 property. This metric is the primary proxy for OOH campaign effectiveness and must be baseline-measured before any OOH campaign launches.

**GA4 + Search Console setup (one-time admin configuration)**

```javascript
// Step 1: Link Google Search Console to GA4 property
// GA4 Admin → Property → Search Console links → Add link
// Select verified Search Console property for satusatu.com

// Step 2: Access branded search data
// GA4 → Reports → Acquisition → Search Console → Queries
// Filter: Query contains "satusatu" OR "satu satu"
// Metrics: Impressions, Clicks, Average Position

// Step 3: Export to Looker Studio for trend visualization
// Data Source: Search Console (Looker Studio native connector)
// Dimension: Date (weekly), Query
// Metric: Impressions, Clicks
```

**OOH triangulation protocol (run during every OOH campaign)**

```javascript
// Pre-campaign (T-4 weeks): export baseline weekly branded impressions
// During campaign: monitor weekly delta vs. 4-week average baseline
// Post-campaign (T+2 weeks): measure decay curve

// Supplementary signals:
// 1. GA4 Default Channel: Direct → weekly session count delta
// 2. OpenPanel: user cohort filter by city where OOH active
//    → compare activation_rate vs. control city cohort
//    → compare booking_conversion_rate vs. control

// Alert threshold: branded search +20% above baseline
// during OOH flight = OOH brand awareness confirmation
```

> **ℹ Note:** Search Console data appears in GA4 with a 48-hour delay. Check weekly, not daily, to avoid premature conclusions. Branded search volume is affected by news, social virality, and seasonal search trends — isolate OOH signal from these confounders using the geo-cohort method in OpenPanel.

| Field | Value |
|-------|-------|
| Dashboard Home | Looker Studio → Search Console connector → branded query impressions trend chart |
| Cadence | `Weekly` (during OOH flights) · `Monthly` (baseline) |

---

### Nice-to-Have Metrics — Tracking Notes

One-line implementation reference. Add these after all Must-Have events are stable and flowing correctly.

| # | Metric | Event to Add | Tool | Note |
|---|--------|--------------|------|------|
| 15 | **Wishlist / Save Rate** | `listing_saved` on Save button click | `OpenPanel` | GTM Click trigger on [data-action="wishlist"] elements. Include listing_id and visitor_type. Compute rate vs. listing_viewed in OpenPanel Funnels. |
| 16 | **Photo View Rate** | `photo_gallery_viewed` on 3rd photo swipe/click | `OpenPanel` | Fire once per listing view session when photo_index ≥ 3. Use IntersectionObserver or swipe event count. Include listing_id and photo_count. |
| 17 | **Filter Usage Rate** | `search_filter_applied` on filter change | `OpenPanel` | GTM Click trigger on filter UI elements. Include filter_type and filter_value. Compute as % of search sessions containing at least 1 filter event. |
| 18 | **Avg Time on Listing Page** | No new event — use OpenPanel Session Duration per page | `OpenPanel` | OpenPanel natively tracks time on page per session. Filter by path contains "/listing/" in the Pages report. No additional instrumentation required. |
| 19 | **Review Submission Rate** | `review_submitted` on review form submit | `OpenPanel` | GTM Form Submit trigger on review form. Include booking_id and listing_id for attribution. Rate = review_submitted / booking_completed (30-day window). |
| 20 | **Listing Completeness Score** | Backend computed — no client-side event | `Backend` | Query: % of listings WHERE photo_count ≥ 5 AND description_length ≥ 200 AND price IS NOT NULL AND review_count ≥ 1. Export to Looker Studio monthly. |
| 21 | **Multi-Destination Browse Rate** | Derived from listing_viewed events | `OpenPanel` | Add destination_tag property to listing_viewed (Card 06). OpenPanel Funnel: COUNT(DISTINCT destination_tag) ≥ 2 per session. Requires destination_tag in listing data. |
| 22 | **Platform Average Rating** | Backend computed from reviews table | `Backend` | AVG(review.rating) WHERE listing.status='active' AND review.created_at > NOW()-30d. Push to Looker Studio monthly. Alert if average drops below 4.2. |
| 23 | **CAC by Channel** | Blend marketing spend data with GA4 conversion data | `GA4` | Manual: export channel spend from Meta Ads + Google Ads. Join with GA4 Acquisition report (new users by channel who completed booking). Compute monthly in Looker Studio. |
| 24 | **90-Day Revenue per User** | Derived from booking_completed events in OpenPanel | `OpenPanel` | OpenPanel user-level: SUM(value) WHERE event=booking_completed AND date_range=user_cohort_date + 90d. Group by first_booking_month cohort. Export via API to Looker Studio. |
| 25 | **NPS Score** | Post-activity survey — new capability required | Survey tool | Deploy Typeform or Delighted survey via email T+2 days after activity_date. Score = Promoters% − Detractors%. Not achievable with current stack without adding a survey tool. |

---

## Task 5: Metrics Relationship Map

Causal dependency diagram showing how leading metrics flow into lagging outcomes and ultimately the North Star. Solid arrows = positive causal flow. Dashed red = negative/friction influence.

> 🗺 **[Diagram: Metrics Causal Relationship Map]** — _7-layer SVG diagram not available in Markdown. See .html file for interactive version._

### Map Legend

The diagram spans 7 causal layers:

**Layer 1 — Acquisition**
- Paid Ad CTR (`GA4` — acquisition input)
- Branded Search Volume (`GA4` + Search Console · OOH Proxy)
- Landing Bounce Rate ↑ (`GA4` — negative signal)

**Layer 2 — Activation**
- Activation Rate (`OpenPanel` · new user, session 1)

**Layer 3 — Discovery**
- Search-to-Catalog CTR (`OpenPanel` — Must-Have)
- Catalog Engagement Depth (`OpenPanel` — depth per session)
- Zero-Result Rate ↑ (`OpenPanel` + `GA4` — supply signal, negative)

**Layer 4 — Intent**
- Checkout Initiation Rate (`OpenPanel` — intent signal)
- Payment Abandonment Rate ↑ (`OpenPanel` — friction signal, negative)

**Layer 5 — North Star**
- ★ Weekly Bookings Completed (`OpenPanel` + `GA4` + `Meta Pixel`)

**Layer 6 — Retention**
- D7 Return Visit Rate (`OpenPanel` — retention leading)
- 30-Day Repeat Booking Rate (`OpenPanel` — retention lagging)

**Layer 7 — Outcomes**
- Revenue (`GA4` + `OpenPanel` — outcome)
- Avg Booking Value (`GA4` + `OpenPanel` — ABV)
- ROAS (`GA4` + `Meta Pixel` — marketing outcome)

### Causal Flow Summary

- Acquisition inputs (Paid Ad CTR, Branded Search) → drive Activation Rate; Landing Bounce Rate negatively impacts Activation
- Activation Rate → feeds Search-to-Catalog CTR and Catalog Engagement Depth; Zero-Result Rate negatively impacts Discovery
- Discovery → drives Checkout Initiation Rate; Payment Abandonment negatively impacts the NSM
- Checkout Initiation Rate → flows positively into the North Star (Weekly Bookings Completed)
- North Star → drives D7 Return Visit Rate and 30-Day Repeat Booking Rate
- D7 Return Rate → leads to Repeat Bookings → drives Revenue
- NSM × Avg Booking Value → Revenue → ROAS (marketing downstream outcome)

**Map Node Color Key:**

- Purple border = `OpenPanel` metric
- Blue border = `GA4` metric
- Dark purple fill = North Star Metric
- Red border = Negative / friction signal
- Amber border = Revenue / outcome
- Green border = `GA4` + `Meta Pixel` marketing metric
