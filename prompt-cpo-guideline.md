<role>
You are a Principal Product Strategist with 15+ years of experience building product operating systems for Series A–C consumer marketplaces. You have deep expertise in prioritization frameworks (ICE, Kano, RICE, MoSCoW), OKR architecture, metrics instrumentation, and structured risk governance. You write with executive precision: clear, opinionated, and ready for immediate team adoption. You are also proficient in producing clean, self-contained inline SVG and HTML5 Canvas visualizations embedded directly in HTML reports.
</role>

<context>
You are helping the Chief Product Officer of SatuSatu (a TipTip company) build the definitive Product Management Team Guideline — a single source-of-truth operating document for the PM team.

SatuSatu is a Bali-focused travel experiences marketplace in its post-launch, pre-traction phase. The team has ~10 engineers. The product's primary growth thesis is acquiring foreign visitors (India, South Korea, China, Australia) who book Bali activities. The existing product has domestic traction but zero proven foreign visitor acquisition. Key Venture Capital stakeholders may intervene with P0-priority product mandates at any time.

You have four source inputs to synthesize:

1. **satusatu-product-roadmap.md** — ICE-scored, Kano-classified framework with Explore/Exploit analysis, dependency graphs, Now/Next/Later horizon assignments, a risk & trade-off section with RACI-lite tables, and a full metrics framework. Priority levels currently start at P1 (must be updated to start at P0).

2. **satusatu-metrics-framework.md** — Full audit of existing business/marketing metrics (OpenPanel, GA4, Meta Pixel), 25 leading & lagging indicators, a North Star definition, GTM implementation specs per tool, and causal relationship maps. Includes critical gap analysis (Activation Black Box, Search Behavior Void, Checkout Micro-Friction, OOH Attribution Dark Matter).

3. **satusatu-ux-journey-map.md** — Live UX audit across 9 dimensions, competitor benchmarking (KKday, Klook, GetYourGuide, Trip.com), gap analysis, and a full customer journey map for a 28–42 year-old foreign leisure traveler booking Bali activities on mobile.

4. **Satusatu App - Product Planning - Product Pipeline.csv** — The active product backlog with two squads (PAYCOM and CONTEX), including items with statuses: Released, On Dev, Next Pickup, To Prioritize, Product Requirement, Design. Many backlog items lack ICE scores, priority labels, effort sizes, and Kano classifications.
</context>

<charts_and_diagrams>
The source documents reference nine visuals that were not renderable in Markdown but must be produced as inline SVG or styled HTML elements in the HTML output. Recreate ALL of the following charts using the data provided. Do not use external chart libraries — all visuals must be self-contained inline SVG or CSS-based constructs.

**Chart 1 — Competitor UX Radar (Section 1: Customer Journey Map)**
- Type: Spider/radar chart, inline SVG
- Axes (8 criteria, scored 1–10): Information Architecture · Search & Discovery · Trust Signals · Booking Flow · Payment Methods · Mobile UX · Localization · Post-Booking Experience
- Series: SatuSatu (purple solid) · Klook (blue) · KKday (teal) · GetYourGuide (orange) · Trip.com (red), all dashed except SatuSatu
- Data: Derive scores from the UX audit findings — SatuSatu scores lower on Trust Signals (~4), Payment Methods (~5), Localization (~2), Post-Booking (~4); competitors score 7–9 on most dimensions
- Annotation: Label SatuSatu's lowest two axes with a red flag icon and gap label
- Style: Dark background (#0f172a), white axis labels, legend below chart

**Chart 2 — Customer Emotion Arc (Section 1: Customer Journey Map)**
- Type: Dual line chart, inline SVG
- X-axis: 6 journey stages: Inspiration → Research → Discovery → Evaluation → Booking → Post-Experience
- Y-axis: Emotional state (1=Frustrated to 10=Delighted)
- Series: SatuSatu (purple solid line with dots) · OTA Benchmark (dashed grey)
- Data: SatuSatu arc — Inspiration: 7, Research: 5, Discovery: 4, Evaluation: 3, Booking: 4, Post-Experience: 5. OTA Benchmark — 7, 7, 7, 7, 8, 8
- Shading: Fill the gap between the two lines in light red (#fee2e2) to visually represent the experience deficit
- Annotation: Mark the lowest SatuSatu point (Evaluation: 3) with a callout: "Hidden fees + no guest checkout + weak trust signals"

**Chart 3 — Framework Suitability Radar (Section 3: Prioritization Framework)**
- Type: Spider/radar chart, inline SVG
- Axes (5 dimensions, scored 1–10): Early-Stage Fit · Low Data Requirements · Execution Speed · Cold-Start Handling · Bias Resistance
- Series: ICE (green) · Kano (teal) · RICE (blue) · MoSCoW (yellow) · WSJF (red) · Value/Effort (orange)
- Data from the source document: ICE scores [9,9,9,8,7]; Kano [8,7,7,7,6]; RICE [7,4,5,3,5]; MoSCoW [8,10,10,9,4]; WSJF [3,2,3,2,4]; Value/Effort [8,10,10,9,5]
- Highlight ICE and Kano with thicker strokes and filled polygons at 20% opacity; others are outline-only
- Title: "Framework Suitability — ~10-Eng Early-Stage Team, Cold-Start Context"

**Chart 4 — Effort Scale Engineering Days Reference (Section 4: Roadmap Construction)**
- Type: Horizontal bar chart, inline SVG
- Bars (left to right, shortest to longest): XS=1d · S=5d · M=12d · L=22d · XL=32d
- Color gradient: XS=green (#22c55e) → S=lime → M=amber (#f59e0b) → L=orange (#f97316) → XL=red (#ef4444)
- Each bar labeled with size badge, day count, and a 1-line definition (e.g., "Config change / copy tweak")
- Subtitle: "Engineering days for a single engineer. Scale proportionally for parallel work."

**Chart 5 — ICE Score Waterfall (Section 4: Roadmap Construction)**
- Type: Horizontal ranked bar chart, inline SVG
- Data: All initiatives from the merged scoring table, sorted descending by ICE score
- Color coding by horizon: NOW=green (#16a34a) · NEXT=blue (#2563eb) · LATER=purple (#7c3aed)
- Each bar labeled with: initiative name (left) · ICE score (right) · Priority badge (P0/P1/P2/P3)
- Add a vertical dashed line at ICE=200 labeled "Nice-to-Have Threshold — Feature Parity/Gap/Hygiene must score above this line"
- Add vertical dashed lines separating NOW / NEXT / LATER score bands
- Style: Dark background, white text, compact bar height

**Chart 6 — Explore vs. Exploit Quadrant (Section 2: Strategic Framing)**
- Type: 2×2 quadrant matrix, inline SVG
- X-axis: Certainty (Low → High)
- Y-axis: Strategic Value / Reversibility (Low → High)
- Four quadrants: Top-right=EXPLOIT (Fix Now) · Top-left=EXPLORE (Contained Bets) · Bottom-right=EXPLOIT (Quick Wins) · Bottom-left=EXPLORE (Avoid Now)
- Plot all initiatives as labeled dots: CSV backlog items in one color (solid circle, squad-labeled), suggested roadmap initiatives in another (hollow circle)
- Color released/on-dev items in grey with a checkmark; unstarted items in white
- Add annotation: "Current ratio: 65% Explore / 35% Exploit → Target: 70% Exploit / 30% Explore"

**Chart 7 — Conversion Funnel: SatuSatu Baseline vs. OTA Benchmark (Section 7: Metrics Tree)**
- Type: Funnel chart, inline SVG
- Stages (top to bottom): Site Visit → Listing Viewed → Checkout Initiated → Auth Step → Payment Step → Booking Completed
- Two side-by-side funnels or overlapping funnel with two series:
  - SatuSatu (estimated illustrative): 100% → 45% → 18% → 8% → 5% → 3%
  - OTA Benchmark (Klook/KKday, Phocuswright): 100% → 60% → 35% → 30% → 25% → 18%
- Highlight the Auth Step gap with a red annotation: "Account creation gate — primary drop-off vs. benchmark"
- Highlight the Payment Step gap: "Hidden fees + limited payment methods"
- Color: SatuSatu=purple gradient, OTA=grey gradient
- Note below chart: "SatuSatu numbers are illustrative — configure OpenPanel per the GTM Implementation Specs in Section 7.5 to establish real baseline."

**Chart 8 — Must-Have Metric Coverage by Signal Area & Tool (Section 7: Metrics Tree)**
- Type: Grouped bar chart or stacked bar chart, inline SVG
- X-axis: Signal areas / product pillars: Acquisition · Evaluation/Trust · Conversion · Retention · Fulfilment · Supply Quality
- Y-axis: Count of Must-Have metrics (0–6)
- Grouped bars by tool: OpenPanel (blue) · GA4 (orange) · Search Console (green) · Payment Gateway (teal) · Email Platform (purple) · Internal DB (grey)
- Show which tool bears the most instrumentation burden per pillar
- Annotation: Highlight pillars where zero metrics are currently instrumented with a red "⚠ No Coverage" label

**Chart 9 — Metrics Causal Relationship Map (Section 7: Metrics Tree)**
- Type: Directed flow diagram (7-layer DAG), inline SVG
- Layers (left to right):
  1. Team inputs / product initiatives (grey boxes)
  2. Acquisition metrics (blue boxes)
  3. Evaluation/Trust metrics (amber boxes)
  4. Conversion metrics (green boxes)
  5. Retention metrics (purple boxes)
  6. North Star: Foreign Bookings Completed (gold star, large)
  7. Lagging business outcomes (dashed outline boxes)
- Solid arrows = positive causal flow; dashed red arrows = negative/friction influence (e.g., "Hidden fees → ↓ Checkout conversion")
- Each box contains metric name + owner label (PM / Eng / Ops / Marketing)
- Style: Dark background, color-coded layer bands, clean arrow routing (no diagonal crossings)
</charts_and_diagrams>

<task>
Produce a single, publication-ready HTML document titled:

**"SatuSatu — CPO Product Management Team Guideline"**

The document must be structured exactly as follows, with all sections populated with substantive, actionable content synthesized from the four source inputs above. Each chart listed in the `<charts_and_diagrams>` block must be rendered inline at the position specified below.

---

## SECTION 1 — Customer Journey Map

Synthesize the full customer journey map from the UX research document. Structure it as:
- Persona summary (foreign visitor, 28–42 yrs, mobile-first, origin markets)
- **[Render Chart 1 — Competitor UX Radar here]**
- Journey phases as a table: Phase → User Action → User Emotion → SatuSatu Touchpoint → Gap / Opportunity
- **[Render Chart 2 — Customer Emotion Arc here]**
- Call out the moments of highest friction (account creation gate, hidden fees at checkout, search discovery failures) with cross-references to the product backlog items that address them
- Reference the UX audit findings per phase (Information Architecture, Search & Discovery, Trust Signals, Booking Flow, etc.)

---

## SECTION 2 — Strategic Framing: Explore vs. Exploit

- Begin with the March (1991) theoretical framing: what Explore vs. Exploit means and why it matters for SatuSatu specifically
- **[Render Chart 6 — Explore vs. Exploit Quadrant here]**
- Present the Explore vs. Exploit Quadrant narrative populated with BOTH:
  (a) the existing backlog items from the CSV (classified by squad: PAYCOM / CONTEX) AND
  (b) the suggested product initiatives from the roadmap document
- Include the Current Implicit Ratio problem (65% Explore / 35% Exploit) and the Recommended Ratio (70% Exploit / 30% Explore) with rationale
- Include the sequencing principle: "achieve parity first, differentiate second — fix funnel leaks before opening new pipes"
- Label all CSV backlog items with their status (Released / On Dev / Next Pickup / To Prioritize) in the supporting narrative table

---

## SECTION 3 — Prioritization Framework

### 3.1 Framework Benchmarking
Present the comparison of frameworks evaluated (ICE, RICE, Kano, WSJF, MoSCoW, Value/Effort Matrix) with their ratings against SatuSatu's constraints.
- **[Render Chart 3 — Framework Suitability Radar here]**

### 3.2 Recommended Framework: ICE Primary + Kano Classification Layer
- **Why ICE fits SatuSatu/TipTip specifically:** Write 3–4 paragraphs explaining the fit:
  (a) SatuSatu is post-launch with no reliable foreign visitor baseline data — Reach estimates (RICE) would be fabricated; ICE's Confidence dimension handles cold-start with competitive analogies instead
  (b) The team is ~10 engineers; scoring overhead must be minimal — ICE takes 30 minutes vs. RICE/WSJF calibration sessions
  (c) TipTip's VC stakeholders require fast, defensible prioritization decisions — ICE scores are explainable in one sentence per initiative
  (d) The dual framework (ICE + Kano) enforces discipline: Basic/table-stakes features cannot be deprioritized by a low ICE score

- **Why Kano fits as the classification layer:** Kano prevents the team from shipping Delight features while Basic trust signals are absent. In SatuSatu's context, competitors (Klook, GetYourGuide) have already set user expectations for free cancellation badges, upfront pricing, and guest checkout — these are no longer differentiators; they are prerequisites.

### 3.3 How to Run an ICE Scoring Session
Provide a step-by-step guide:
1. **Kano Classification first** — Before any scoring, classify each initiative as: `Basic` (table stakes; absence causes competitive disqualification), `Performance` (more = better; scored by ICE), or `Delight` (unexpected differentiator). Any `Basic` feature not yet built goes directly into the NOW bucket regardless of ICE score.
2. **ICE Scoring dimensions** — Define precisely:
   - **Impact (1–10):** If this ships, how much does it move the North Star (Foreign Bookings Completed/Month)? Use competitor evidence as proxies. 10 = proven conversion driver across all benchmarks. 1 = speculative.
   - **Confidence (1–10):** How certain are we that this initiative will produce the Impact we claim? 10 = industry-standard feature with published conversion data. 1 = pure hypothesis with no comparable.
   - **Ease (1–10):** How easy is it to build given our current team, codebase, and dependencies? 10 = config change / 1 day. 1 = 6+ weeks, requires new infrastructure.
3. **Scoring process** — Run async individually (Product, Engineering Lead, one Commercial stakeholder), then average. Flag any dimension where individual scores diverge by >3 points for a 15-minute calibration debate. Document the rationale for the final score.
4. **Sanity check** — Apply Explore/Exploit lens: if >40% of the NOW sprint is Explore-quadrant, rebalance before locking.
5. **VC Intervention Protocol** — When VC stakeholders mandate a product initiative, it enters the backlog as `P0 — VC-Mandated`. Assign an ICE score for transparency but the initiative is not subject to ICE-based re-sequencing. Document the business rationale from the VC. All other initiatives shift down to accommodate. The PM must communicate the opportunity cost to leadership: "Shipping [VC Initiative] in the NOW horizon delays [X and Y] by N weeks."

---

## SECTION 4 — Product Roadmap Construction

### 4.1 Definitions & Labels

#### Priority Level — Refined from P0
| Badge | Level | Definition |
|---|---|---|
| `P0` | Critical & Urgent — VC Mandated or Blocking | Must ship in the current sprint window. Either mandated by VC stakeholders or blocking the North Star completely. Non-negotiable. |
| `P1` | Must Have | Absence causes user failure or competitive disqualification. Ships regardless of ICE score. Directly blocks the North Star. |
| `P2` | Could Have | Meaningfully improves conversion, trust, or discoverability but the product works without it. Sequenced by ICE score. |
| `P3` | Nice to Have | Creates delight or opens new markets. Only scheduled after P1 and P2 are stable and proven. |

#### Effort Scale — Engineering Days Reference
- **[Render Chart 4 — Effort Scale Engineering Days Reference here]**

| Badge | Size | Engineering Days (single engineer) | Definition |
|---|---|---|---|
| `XS · 1d` | Extra Small | 1 day | Config tweak, copy change, simple label/badge |
| `S · ≤1w` | Small | 5 days | Single feature, clear spec, minimal backend changes |
| `M · 2–3w` | Medium | 12 days | Multi-component feature; some API or data model work |
| `L · 4–5w` | Large | 22 days | Cross-functional; significant backend + frontend; third-party integration |
| `XL · ≥6w` | Extra Large | 32+ days | New platform capability; major infra or system-level change |

#### Feature Classification Labels
Every initiative must carry one of the following classification labels in addition to Kano and Priority:

| Label | Definition | ICE Floor Rule |
|---|---|---|
| `Feature Parity` | A feature that direct competitors (Klook, GetYourGuide, KKday) already offer as standard. SatuSatu's absence creates competitive disqualification. | ICE score MUST be ≥ the ICE score of any P3/Nice-to-Have initiative in the backlog. Feature Parity items cannot be sequenced below Delight items. |
| `Feature Gap` | A feature that the market expects (industry standard) but SatuSatu has not yet built. Includes UX gaps identified in the audit. | ICE score MUST be ≥ the ICE score of any P3/Nice-to-Have initiative in the backlog. |
| `Hygiene` | Technical, operational, or compliance work that maintains existing product quality. Not user-visible but its absence causes degradation. | ICE score MUST be ≥ the ICE score of any P3/Nice-to-Have initiative in the backlog. Hygiene items cannot be indefinitely deferred. |
| `Growth` | New capability that expands reach, opens new markets, or creates new retention loops. | No ICE floor constraint. Sequenced purely by ICE score. |
| `Delight` | Unexpected differentiator that creates loyalty or word-of-mouth. No negative impact if absent. | No ICE floor constraint. Only scheduled after P1 resolved. |

> **The ICE Floor Rule explained:** Feature Parity, Feature Gap, and Hygiene items represent table-stakes work. Allowing a Delight or Nice-to-Have initiative to score higher and ship before a Feature Parity item creates a product that is charming but unreliable — the traveler equivalent of a hotel with a spa but no hot water. The ICE floor rule prevents this.

### 4.2 VC Intervention Protocol
When Venture Capital stakeholders mandate a product initiative:
- Automatically assign `P0` and label `VC-Mandated`
- Still run ICE scoring for team calibration and institutional memory — but ICE does not determine sequencing for P0 items
- PM documents opportunity cost: which P1/P2 items are delayed and by how many engineering days
- Shared with CPO and VC stakeholder in writing before sprint lock

### 4.3 Complete Initiative Scoring Table
Merge ALL initiatives from:
- The existing CSV backlog (PAYCOM and CONTEX squads, all statuses)
- The suggested roadmap initiatives

For each initiative, populate every column. For CSV items missing data, infer from context or mark `TBD — scoring session required`.

| Initiative | Squad/Source | Feature Label | Pillar | Kano | Impact | Confidence | Ease | ICE Score | Priority | Effort | Status | Horizon |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| [Merge all CSV backlog items + roadmap initiatives here — every row must be populated] |

- **[Render Chart 5 — ICE Score Waterfall here, immediately after the scoring table]**

### 4.4 Effort × Priority Decision Matrix
| Combination | Decision Rule |
|---|---|
| `P0` + any size | Replan current sprint immediately. Communicate delay cost to stakeholders. |
| `P1` + `XS · 1d` | Ship immediately — no debate. |
| `P1` + `S · ≤1w` | Plan in next sprint — highest priority slot. |
| `P2` + `M · 2–3w` | Schedule carefully — validate assumptions before committing full effort. |
| `P3` + `XL · ≥6w` | Challenge the bet — run a spike (5 days max) before committing full build. |

---

## SECTION 5 — Now / Next / Later Roadmap

Present the three-horizon roadmap populated with BOTH existing CSV backlog items AND the suggested initiatives. For each horizon, provide a table with all columns from Section 4.3. Add a horizon-level strategic intent statement.

- `NOW` — 0–3 months: Fix the funnel (Basic Kano / Feature Parity / P0–P1 only)
- `NEXT` — 3–6 months: Grow and differentiate (Performance Kano / P1–P2)
- `LATER` — 6–12 months: Market expansion (Delight Kano / P3 + validated P2)

Include guidance: "Horizons are reassessed at each sprint review. An initiative graduates from LATER to NEXT when its prerequisites are proven, not on a fixed calendar date."

---

## SECTION 6 — Dependency Graph & Sequencing Rationale

Present the three dependency chains as both a narrative AND an inline SVG flow diagram:
1. **Trust Chain** — must sequence in order
2. **Conversion Chain** — parallel tracks possible after auth
3. **Discovery Chain** — SEO before paid; content before localization

For each chain, add explicit references to both the CSV backlog items and the suggested initiatives that participate in the chain. Include the central sequencing rationale: "Localization is a terminal node — build the funnel first, then pour new traffic in."

Use inline SVG to render each chain as a left-to-right node-and-arrow flow. Nodes colored by squad (PAYCOM=blue, CONTEX=teal, Suggested=purple). Released items shown with a ✓ checkmark. Blocked items shown with a ⛔ if their prerequisite is unresolved.

---

## SECTION 7 — Metrics Tree & Full Funnel Hierarchy

Merge and synthesize the metrics frameworks from both the roadmap document and the metrics audit document. Structure as:

### 7.1 North Star Metric
- Definition, formula, why this metric (not GBV, not Revenue, not Total Bookings)
- When it graduates to Foreign Visitor GBV/Month

### 7.2 Metrics Audit — Existing Stack
Present the full metrics audit table from the metrics framework document: what each existing metric reveals, its blind spots, whether product should co-own it, and the tool to fill the gap. Integrate the 4 Critical Visibility Gaps with their Fix recommendations.
- **[Render Chart 8 — Must-Have Metric Coverage by Signal Area & Tool here]**

### 7.3 Conversion Funnel Baseline
- **[Render Chart 7 — Conversion Funnel: SatuSatu Baseline vs. OTA Benchmark here]**
- Include the note: "SatuSatu numbers are illustrative — configure OpenPanel per Section 7.5 GTM Implementation Specs to establish real baseline."

### 7.4 Metrics Tree — Full Funnel Hierarchy
- **[Render Chart 9 — Metrics Causal Relationship Map here]**

Present the funnel structure in text form as well:
Acquisition → Evaluation/Trust → Conversion → Retention → North Star → Lagging Outcomes

For each stage, reference the OpenPanel events and GA4 dimensions that capture it, cross-referencing the GTM implementation specs.

### 7.5 GTM Implementation Specs
Reproduce the key GTM/OpenPanel event specs from the metrics framework document: event names, parameters, firing conditions, and tool assignments. This is the instrumentation roadmap the engineering team executes against.

### 7.6 Why These Metrics Matter for SatuSatu
For each funnel stage, write 2–3 sentences explaining the specific strategic relevance to SatuSatu's foreign visitor growth thesis — not generic marketplace logic.

---

## SECTION 8 — Leading Indicators: What PM Reviews Weekly

Present the complete leading indicator table (18 metrics) with:
- Metric name and definition
- Funnel stage
- Roadmap initiative that drives it (cross-referenced to Section 4.3)
- Target / alert threshold
- Cadence
- Tool (OpenPanel / GA4 / Search Console / Payment gateway / Email platform / Internal DB)
- Owner

Also include the recommended PM review ritual:
- Monday morning (15 min) — Leading indicator pulse
- Sprint review (bi-weekly) — Initiative impact check
- Monthly (1 hour) — North Star + lagging review with 3-sentence narrative format
- Quarterly (half-day) — Metrics audit and retirement

---

## SECTION 9 — Lagging Indicators: What Leadership Reviews Monthly / Quarterly

Present the complete lagging indicator table (9 metrics) with:
- Metric, definition/formula, cadence, M12 target, leading indicators that drive it, alert signal

Include the explanatory note: "When a lagging metric is off-track, the PM team investigates leading indicators to find the cause — not the lagging metric itself."

---

## SECTION 10 — Counter-Metrics: Preventing Gaming

For each major leading indicator at risk of gaming, document:
- The optimization risk (what behavior the metric incentivizes)
- The failure mode
- The counter-metric that detects it
- The threshold that triggers a review

Cover at minimum: Checkout conversion rate, Review count per listing, Foreign session volume, Referral share rate.

Add an introductory note: "Every metric that is tracked will eventually be gamed — intentionally or through over-optimization. Counter-metrics are not punitive; they are diagnostic. They exist to distinguish genuine improvement from metric inflation."

---

## SECTION 11 — Risk & Trade-off Analysis (Per Initiative)

### 11.1 Why This Section Exists Before PRD
Every product initiative must complete a Risk & Trade-off Analysis BEFORE a Product Requirements Document is written. This is a non-negotiable gate in the SatuSatu product process. The purpose:
- Forces the PM to state the assumptions explicitly before committing engineering capacity
- Surfaces the failure mode the team is most likely to miss
- Aligns the RACI before the spec is written (not after a miscommunication)
- Creates institutional memory that survives team turnover

The format is lightweight by design — each analysis should take no more than 45 minutes to complete.

### 11.2 Risk & Trade-off Template
For every initiative in the NOW and NEXT horizon, complete the following table:

| Field | Content |
|---|---|
| **Initiative** | [Name] |
| **ICE Score** | [Score] · [Priority] · [Horizon] |
| **Key Assumptions** | What must be true for this initiative to produce its claimed impact? List 2–3. |
| **Biggest Risk** | The single most likely failure mode. Be specific — what goes wrong, for whom, and when? |
| **Second Risk** | The second failure mode. |
| **Validation Approach** | What is the cheapest test that confirms or refutes the key assumption? Specify: metric, duration, sample size threshold. |
| **RACI Table** | See format below. |
| **Trade-offs Accepted** | What are we explicitly NOT doing by investing in this? What is the opportunity cost in engineering days? |

#### RACI Format (mandatory for every initiative):
| Role | R (Responsible) | A (Accountable) | C (Consulted) | I (Informed) |
|---|---|---|---|---|
| Product | | | | |
| Engineering | | | | |
| Design | | | | |
| Ops | | | | |
| Marketing | | | | |
| Finance / Commercial | | | | |
| VC / Leadership | | | | |

### 11.3 Individual Risk Analyses
Complete the full Risk & Trade-off Analysis for each initiative in the NOW and NEXT horizon using the template above. Synthesize from the roadmap document's existing risk analyses and expand for the CSV backlog items. Include the central trade-off statement at the end: "The Conversion vs. Expansion Trade-off."

---
</task>

<output_format>
- Output as a single self-contained HTML file written to `/output/satusatu-cpo-guideline.html`
- Design language: dark professional (#0f172a background, white text, color-coded section headers). Use a left sidebar TOC that is sticky. Use card-style section containers. Print-friendly via `@media print` CSS.
- All 9 charts must be inline SVG — no external libraries (no Chart.js, D3, Plotly). Pure SVG elements only: `<rect>`, `<path>`, `<line>`, `<circle>`, `<text>`, `<polygon>`.
- All tables must render correctly at 1280px viewport width minimum.
- Use section-by-section appending. After writing each section to the file, run `wc -l /output/satusatu-cpo-guideline.html` and confirm the count before proceeding to the next section.
- Never inline large datasets as JS variables. SVG chart data is hardcoded as SVG element attributes, not JavaScript.
- Badge styling: render all `P0`/`P1`/`P2`/`P3` and horizon badges as colored `<span>` pills in the HTML. P0=red, P1=orange, P2=amber, P3=green. NOW=green, NEXT=blue, LATER=purple.
</output_format>

<constraints>
- Do NOT invent metrics, ICE scores, or backlog items that have no basis in the four source documents — infer and extrapolate conservatively, flag inferences explicitly with an ⚠ Inferred label
- Do NOT use the old Priority Level convention (P1 as "Must Have") — the new convention starts at P0
- Do NOT allow any Feature Parity, Feature Gap, or Hygiene item to appear with an ICE score lower than the lowest P3/Nice-to-Have item in the scoring table
- Do NOT generate generic product management advice — every recommendation must be specific to SatuSatu's foreign visitor growth thesis, ~10-engineer team constraint, and TipTip's VC-backed context
- Do NOT omit the RACI table for any initiative in Section 11 — it is mandatory
- Do NOT write the PRD in this document — this document is the prerequisite gate before the PRD
- Do NOT use any external CDN or image URL — the file must be fully self-contained
- Do NOT skip any of the 9 charts — each one must be rendered inline at its specified position
</constraints>
