---
name: Competitor Benchmarking
description: Monitors Klook, KKday, GetYourGuide, and Trip.com for feature changes, pricing shifts, and UX updates in the activities vertical.
model: gemini-2.5-flash
lifecycle_stage: "1–2. Discovery & Ideation"
tools: Brave Search MCP, Playwright MCP, Atlassian MCP
---

## Purpose

Provides structured competitive intelligence by monitoring OTA competitors in the activities/experiences vertical. Outputs a weekly digest of changes that the PM can use to update Kano classifications (Page 03) — if a competitor ships a feature SatuSatu lacks, that feature may shift from Performance to Basic.

## Input

- **Competitor list** — Default: Klook, KKday, GetYourGuide (GYG), Trip.com
- **Focus areas** — (optional) Specific aspects to monitor: pricing, checkout UX, trust signals, search/filter, mobile experience, new markets
- **Previous report** — (optional) Last benchmarking report for diff comparison

## Output

- **Weekly Competitor Digest** (markdown) with:
  - Change log per competitor (new features, removed features, pricing changes, UX changes)
  - Kano impact assessment: Does this change shift any SatuSatu backlog item's classification?
  - Screenshot evidence (if using Playwright MCP for automated browsing)
  - Recommended actions for SatuSatu backlog
- All outputs prefixed with `⚠️ AI DRAFT — PM REVIEW REQUIRED`

## Process

1. **Scan** — Use Brave Search MCP to search for recent news, blog posts, and changelogs for each competitor
2. **Browse** — Use Playwright MCP to visit competitor sites and capture current state of key pages (homepage, search results, listing detail, checkout)
3. **Compare** — Against previous report (if available), identify what has changed
4. **Classify** — For each change:
   - Is this a feature SatuSatu already has? (Parity)
   - Is this a feature SatuSatu lacks? (Gap — check if in backlog Page 03)
   - Does this shift any Kano classification? (Basic/Performance/Delight)
5. **Assess** — Rate competitive threat: Low (nice-to-have), Medium (should address), High (urgent gap)
6. **Report** — Generate digest with actionable recommendations

## Constraints

- All outputs must begin with `⚠️ AI DRAFT — PM REVIEW REQUIRED`
- Only analyze competitors in the activities/experiences vertical — ignore hotel/flight features
- Kano reclassification suggestions must reference the specific initiative from Page 03 by name and number
- Use Gemini 2.5 Flash for speed (this is a recurring, high-frequency task)
- Screenshots captured via Playwright must be stored locally, not uploaded to external services

## How to Use

1. Open Claude Code or Gemini in the playbook directory
2. Say: `Use the competitor-benchmarking skill to generate this week's competitor digest. Focus on [optional: checkout UX / trust signals / pricing].`
3. If you want automated browsing, ensure Playwright MCP is connected
4. Review the digest, validate Kano reclassification suggestions, and update the backlog tracker (Page 08) accordingly

## Example

**Input**: Weekly scan, focus on trust signals

**Expected Output** (excerpt):

```markdown
⚠️ AI DRAFT — PM REVIEW REQUIRED

## Competitor Digest — Week of March 24, 2026

### Klook
- 🆕 **Added "Free Cancellation" filter** to search results — users can filter activities by cancellation policy
  - Kano Impact: SatuSatu has Free Cancellation Badge (#1, P0) but NO filter. Consider adding filter as follow-up.
- 🔄 **Updated review display** — now shows "Verified Booking" tag next to reviews
  - Kano Impact: Shifts External Review Import (#19, P2) from Performance → Basic if 2+ competitors adopt this

### GetYourGuide
- 🆕 **Apple Pay added** to mobile checkout
  - Kano Impact: Google Pay + Apple Pay (#21, P2) — GYG adoption reinforces this as Basic
```
