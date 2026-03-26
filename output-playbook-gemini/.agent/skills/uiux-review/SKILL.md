---
name: UI/UX Review with Scoring
description: Screenshot-based design audit scoring accessibility, consistency, trust signals, and usability against product standards.
model: claude-haiku-4
lifecycle_stage: "4. Prototyping & Testing"
tools: Figma MCP, Playwright MCP
parallel: false  # Vision analysis requires holistic view of the screenshot — splitting dimensions loses cross-dimension context (e.g., trust signal placement affects CTA clarity)
---

## Embedded Context

This skill is self-contained. All referenced frameworks are embedded below.

### Customer Journey Stages
| # | Stage | User Goal | UI Implication |
|---|---|---|---|
| 1 | Inspiration | Discover activities | Hero imagery, curated sections, editorial content |
| 2 | Research | Compare options, read reviews | Search/filter, listing cards, review display |
| 3 | Evaluation | Trust audit | Badges, social proof, cancellation policy, "is this legit?" signals |
| 4 | Booking | Complete transaction | CTA clarity, payment methods, price transparency, guest checkout |
| 5 | Pre-Experience | Logistics & reassurance | Confirmation details, maps, operator contact, reminders |
| 6 | Post-Experience | Review & return | Review prompts, loyalty hooks, referral flows |

### Trust Signal Checklist (must be visible on relevant pages)
| Signal | Where Expected | Priority |
|---|---|---|
| Free Cancellation Badge | Listing card + detail page + checkout | P0 |
| Locally Curated / Verified Badge | Listing card + detail page | P1 |
| Star Rating + Review Count | Listing card + detail page | P1 |
| Social Proof Counter ("X booked") | Homepage + listing detail | P1 |
| Review Nationality Flags | Detail page (when shipped) | P2 |
| Operator Verification Badge | Detail page | P2 |

### Primary Persona
- **Who**: Foreign leisure traveler (India, China, South Korea, Australia), age 28–42
- **Device**: Mobile-first (375px primary viewport)
- **Core anxiety**: "Is this platform safe? Will my money be protected?"

### Approved Design Tools
Figma only. No Sketch, no Adobe XD.

---

## Purpose

Provides structured design review by scoring UI screenshots or Figma exports against UX standards and customer journey requirements. Catches trust signal gaps, accessibility issues, and consistency problems before engineering builds the wrong thing.

Uses Claude Haiku 4 for vision analysis — optimized for image input with fast, structured responses.

## Input

- **Screenshots** — PNG/JPG of the UI being reviewed (desktop and/or mobile)
- **Figma export** — Via Figma MCP (Dev Mode), pull design data directly
- **Context** — Which journey stage and initiative this UI belongs to
- **Device target** — Desktop, mobile, or both

## Output

- **Design scorecard** (markdown) with:
  - Score per dimension (0–10 scale, 5 dimensions)
  - Total score (0–50)
  - Pass/Fail recommendation (Pass ≥ 35, Conditional 25–34, Fail < 25)
  - Annotated feedback per dimension with specific UI element references
  - Screenshot annotations (described textually if image output not available)
- All outputs prefixed with `⚠️ AI DRAFT — PM REVIEW REQUIRED`

## Process

1. **Load** — Ingest screenshot(s) or pull Figma design data via MCP
2. **Identify context** — Determine which journey stage and initiative this UI supports
3. **Score** — Rate each of 5 dimensions on 0–10 scale:

| Dimension | Weight | What to Check |
|---|---|---|
| **Trust Signals** | 25% | Is the cancellation badge visible? Social proof counter? Verified badge? Review ratings? (Use Trust Signal Checklist above) |
| **CTA Clarity** | 20% | Is the primary action obvious? Is there exactly one CTA per viewport? Is it labeled with action verbs? |
| **Information Architecture** | 20% | Is pricing transparent (all-inclusive)? Are essential details (date, time, meeting point) visible without scrolling? |
| **Mobile Responsiveness** | 20% | Does the layout work at 375px width? Are tap targets ≥ 44px? Is text readable without zooming? |
| **Accessibility** | 15% | Color contrast ≥ 4.5:1? Alt text for images? Keyboard navigable? WCAG 2.1 AA compliance? |

4. **Benchmark** — Compare against competitor UX (Klook, KKday, GYG) if screenshots are available
5. **Report** — Generate scorecard with actionable design-specific feedback

## Constraints

- All outputs must begin with `⚠️ AI DRAFT — PM REVIEW REQUIRED`
- Trust signals scoring MUST reference the specific items from the Trust Signal Checklist (see Embedded Context)
- Do NOT suggest tools outside the approved stack — e.g., no Sketch, no Adobe XD
- Use Claude Haiku 4 for this skill (vision-optimized, fast structured responses)
- Mobile review is mandatory — if only desktop screenshot is provided, flag mobile review as incomplete

## How to Use

1. Take screenshots of the UI or export from Figma
2. Open Claude Code in any directory
3. Say: `Use the uiux-review skill to score this checkout page design. This is for [initiative name] at the [journey stage] stage.`
4. Attach screenshot(s) — both mobile (375px) and desktop (1280px) recommended
5. Review the scorecard with your designer — prioritize dimensions scoring below 6

## Example

**Input**: Screenshot of listing detail page (mobile), Initiative: Free Cancellation Badge (#1, P0)

**Expected Output** (excerpt):

```markdown
⚠️ AI DRAFT — PM REVIEW REQUIRED

## UI/UX Scorecard: Listing Detail Page (Mobile)
**Initiative**: Free Cancellation Badge (#1, P0) · **Journey Stage**: Evaluation/Booking

| Dimension | Score | Feedback |
|---|---|---|
| Trust Signals | 4/10 | ❌ Cancellation badge is present but placed below the fold — 80% of mobile users won't see it. Move to pricing area or sticky CTA bar. Social proof counter is missing entirely. |
| CTA Clarity | 7/10 | ✅ "Book Now" button is prominent. ⚠️ Secondary CTA "Add to Wishlist" competes for attention — reduce visual weight. |
| Information Architecture | 6/10 | ⚠️ Price shows base only — add-ons appear at checkout. Violates all-inclusive pricing principle. Meeting point is hidden in collapsed accordion. |
| Mobile Responsiveness | 8/10 | ✅ Layout works at 375px. Tap targets adequate. ⚠️ Image carousel swipe indicator is barely visible. |
| Accessibility | 5/10 | ❌ Price text contrast is 3.2:1 (below 4.5:1 minimum). Badge icon has no alt text. |

### Total: 30/50 — ⚠️ CONDITIONAL PASS

### Priority Fixes
1. Move cancellation badge above the fold (Trust Signals)
2. Fix price text contrast to ≥ 4.5:1 (Accessibility)
3. Show all-inclusive price on listing (Information Architecture)
```
