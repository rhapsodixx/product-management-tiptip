---
name: PRD Review with Scoring
description: Scores a Product Requirements Document against SatuSatu's 7-dimension rubric and provides actionable feedback with a pass/fail recommendation.
model: claude-sonnet-4
lifecycle_stage: "3. Definition & Documentation"
tools: Atlassian MCP, Sequential Thinking MCP
---

## Purpose

Enforces PRD quality by scoring every draft against a standardized rubric before engineering commitment. Catches missing sections, vague acceptance criteria, and disconnected metrics — the three most common PRD failure modes. References Page 06 (risk analysis gate) to ensure the pre-PRD analysis was completed.

## Input

- **Draft PRD** — Markdown, Confluence page (via Atlassian MCP), or pasted text
- **Initiative context** — Initiative name, ICE score, Kano classification, Dependency Pillar from Page 03/04
- **Risk Analysis** — Completed Page 06 risk analysis for this initiative (required input)

## Output

- **Score card** (markdown) with:
  - Score per dimension (0–100 scale, 7 dimensions)
  - Weighted total score (0–100)
  - Pass/Fail recommendation (Pass ≥ 70, Conditional 50–69, Fail < 50)
  - Specific feedback per dimension with line-level citation
  - Missing sections checklist
- All outputs prefixed with `⚠️ AI DRAFT — PM REVIEW REQUIRED`

## Process

1. **Validate gate** — Confirm that a Risk & Trade-off Analysis (Page 06) exists for this initiative. If not, output: "⛔ BLOCKED: Complete Page 06 Risk Analysis before PRD review."
2. **Parse** — Read the PRD and identify each section
3. **Score** — Rate each of the 7 dimensions on a 0–100 scale:

| Dimension | Weight | Scoring Criteria |
|---|---|---|
| **Problem Statement** | 15% | Is it clear, specific, and tied to a user pain point from the journey map (Page 01)? |
| **User Stories** | 20% | Does it follow "As a [user], I want [action], so that [value]" format? Are edge cases covered? |
| **Acceptance Criteria** | 20% | Are criteria testable? Unambiguous? Do they cover happy path + error states? |
| **Success Metrics** | 15% | Are metrics tied to NSM or Must-Have metrics from Page 05? Is the measurement plan specified? |
| **Dependencies** | 10% | Are dependencies cross-referenced with Page 04 chains? Is the Blocked By / Blocks relationship clear? |
| **Risk Acknowledgment** | 10% | Does the PRD reference the Page 06 analysis? Are mitigations documented? |
| **Technical Feasibility** | 10% | Has the Engineering PIC validated the effort estimate? Are technical constraints noted? |

4. **Calculate** — Weighted total = Σ(dimension_score × weight)
5. **Recommend** — Pass (≥70), Conditional Pass (50–69), Fail (<50)
6. **Report** — Generate scorecard with specific, actionable feedback per dimension

## Constraints

- All outputs must begin with `⚠️ AI DRAFT — PM REVIEW REQUIRED`
- Do NOT pass a PRD that lacks a Risk Analysis reference — this is a non-negotiable gate (Page 06)
- Scoring must be strict: vague acceptance criteria = score ≤ 40 for that dimension
- Use Claude Sonnet 4 for this skill (deep reasoning required for nuanced evaluation)
- If using Sequential Thinking MCP, break the review into 7 reasoning steps (one per dimension)

## How to Use

1. Complete the Risk & Trade-off Analysis (Page 06) for the initiative
2. Open Claude Code in the playbook directory
3. Say: `Use the prd-review skill to score this PRD for [initiative name]. The Risk Analysis is complete.`
4. Paste or attach the PRD (or provide the Confluence page ID if Atlassian MCP is connected)
5. Review the scorecard — address all dimensions scoring below 60 before engineering handoff

## Example

**Input**: Draft PRD for "Free Cancellation Badge" (Initiative #1, P0)

**Expected Output** (excerpt):

```markdown
⚠️ AI DRAFT — PM REVIEW REQUIRED

## PRD Scorecard: Free Cancellation Badge

| Dimension | Score | Weight | Weighted | Feedback |
|---|---|---|---|---|
| Problem Statement | 85 | 15% | 12.8 | ✅ Clear: "Foreign visitors abandon checkout when cancellation policy is not visible." Tied to Booking stage (Page 01). |
| User Stories | 70 | 20% | 14.0 | ⚠️ Missing edge case: what happens for activities with partial cancellation (e.g., 48h cutoff)? Add story for this variant. |
| Acceptance Criteria | 55 | 20% | 11.0 | ❌ Criteria say "badge is shown" but don't define WHERE (listing card? detail page? both?). Not testable as written. |
| Success Metrics | 80 | 15% | 12.0 | ✅ Tied to Checkout Initiation Rate (Must-Have, Page 05). Missing: counter-metric monitoring (Booking Cancellation Rate). |
| Dependencies | 90 | 10% | 9.0 | ✅ No blockers. XS effort, no dependency chain. |
| Risk Acknowledgment | 75 | 10% | 7.5 | ✅ References Page 06 analysis. Missing: mitigation plan for partial-cancel operators. |
| Technical Feasibility | 80 | 10% | 8.0 | ✅ PIC validated: <1 day, data model exists. |

### Total: 74.3 / 100 — ✅ PASS

### Action Items Before Handoff
1. Add user story for partial cancellation variant
2. Make acceptance criteria testable — specify exact badge placement
3. Add Booking Cancellation Rate as counter-metric to monitor
```
