---
name: Product Research & Journey Mapping
description: Analyzes support tickets, user feedback, and market data to identify themes, pain points, and opportunities mapped to SatuSatu's customer journey.
model: gemini-2.5-pro
lifecycle_stage: "1. Discovery & Research"
tools: NotebookLM MCP, Brave Search MCP, Atlassian MCP, Sequential Thinking MCP
---

## Purpose

Automates the discovery phase by analyzing unstructured user data (support tickets, reviews, interview notes) and producing a structured research report. The output maps directly to SatuSatu's 6-stage customer journey (Page 01) and Dependency Pillars (Page 04), enabling the PM to quickly identify which funnel stage has the most friction and which pillar needs attention.

## Input

- **Support tickets** — CSV or text export from support tool (minimum 50 tickets for meaningful patterns)
- **User reviews** — App store reviews, Google reviews, or TripAdvisor/social media mentions
- **Competitor data** — (optional) Screenshots or URLs of competitor features to benchmark against
- **Scope filter** — (optional) Limit analysis to a specific journey stage or pillar

## Output

- **Themes report** (markdown) with:
  - Top 10 themes ranked by frequency
  - Each theme mapped to: Journey Stage (Page 01), Dependency Pillar (Trust/Conversion/Discovery from Page 04), Severity (Blocking/Frustrating/Minor)
  - Frequency count and representative quotes per theme
  - Recommended actions tied to existing backlog items (Page 03) where applicable
- **Opportunity matrix** — 2×2 showing Frequency vs. Severity with theme placement
- All outputs prefixed with `⚠️ AI DRAFT — PM REVIEW REQUIRED`

## Process

1. **Ingest** — Load all input data into context. If using NotebookLM MCP, create a notebook with the source files.
2. **Categorize** — For each ticket/review, classify:
   - Journey stage: Dreaming → Planning → Booking → Pre-Experience → Experience → Post-Experience (Page 01)
   - Dependency Pillar: Trust / Conversion / Discovery (Page 04)
   - Severity: Blocking (user cannot proceed), Frustrating (user can proceed with friction), Minor (cosmetic/preference)
3. **Cluster** — Group classified items into themes (e.g., "Payment method confusion", "Missing cancellation info", "Search returns irrelevant results")
4. **Rank** — Sort themes by: (1) frequency, (2) severity weight (Blocking=3, Frustrating=2, Minor=1), (3) pillar priority (Trust > Conversion > Discovery)
5. **Cross-reference** — Check each theme against Page 03's scoring table. If a backlog item already addresses this theme, note the initiative name and ICE score.
6. **Report** — Generate the structured output following the format above

## Constraints

- All outputs must begin with `⚠️ AI DRAFT — PM REVIEW REQUIRED`
- Do NOT invent user quotes — only use direct text from the input data
- Do NOT recommend solutions outside SatuSatu's approved tool stack (Page 00)
- Severity classification must be falsifiable — provide the specific user action that was blocked or degraded
- Use Gemini 2.5 Pro for this skill (large context window needed for 200+ tickets)

## How to Use

1. Export support tickets or user feedback into a CSV or text file
2. Open Claude Code / Gemini in the playbook directory
3. Say: `Use the product-research-journey-mapping skill to analyze these [N] support tickets. Focus on [optional: specific journey stage or pillar].`
4. Attach the data file(s)
5. Review the AI draft, validate theme classifications against your domain knowledge, and refine

## Example

**Input**: 150 support tickets from Q1 2026

**Expected Output** (excerpt):

```markdown
⚠️ AI DRAFT — PM REVIEW REQUIRED

## Top Themes from Q1 2026 Support Tickets (n=150)

| # | Theme | Frequency | Journey Stage | Pillar | Severity | Existing Backlog Item |
|---|---|---|---|---|---|---|
| 1 | "Can I cancel for free?" — no visible cancellation policy | 23 (15%) | Booking | Trust | Blocking | Free Cancellation Badge (#1, P0) |
| 2 | Payment failed / no alternative method | 18 (12%) | Booking | Conversion | Blocking | Google Pay + Apple Pay (#21, P2) |
| 3 | Search returned wrong location results | 14 (9%) | Planning | Discovery | Frustrating | Autocomplete + Search Filters (#27, P2) |
| 4 | "Is this a legit site?" — no reviews visible | 12 (8%) | Planning | Trust | Frustrating | External Review Import (#19, P2) |
| 5 | Forced to create account to book | 11 (7%) | Booking | Conversion | Blocking | Guest Checkout + SSO (#6, P1) |
```
