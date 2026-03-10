---
type: skill
id: strategic-recommendation
title: Strategic Recommendation
description: "Generating actionable strategic recommendations from competitive data, SWOT analysis, and positioning insights"
tags: [Production, Tested]
connections:
  - target: claude-service
    type: runs_on
  - target: competitive-intelligence-framework
    type: references
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Strategic Recommendation

This skill transforms competitive analysis data into actionable strategic recommendations. It bridges the gap between "we know what competitors are doing" and "here is what we should do about it."

### Core Capability

Given a complete competitive analysis (competitor profiles, feature comparison, SWOT analysis, and positioning map), this skill generates prioritised strategic recommendations across four action categories: invest, differentiate, match, and concede.

### The Four Action Categories

**1. Invest — Areas to Double Down**

These are areas where your product already has an advantage and the market values that advantage. Recommendations here focus on extending the lead:
- Which strengths are most valued by customers?
- Where is the gap between you and the nearest competitor largest?
- What investments would make this advantage harder to replicate?
- How can this advantage be made more visible in marketing and sales?

**2. Differentiate — Areas to Create Separation**

These are areas where you can create meaningful distance from competitors by taking a different approach. Recommendations focus on zigging where others zag:
- Which white spaces from the positioning analysis are most viable?
- What unique capabilities does your team or technology enable?
- Where are competitors converging on the same approach, leaving room for an alternative?
- What customer needs are competitors collectively ignoring?

**3. Match — Areas to Reach Parity**

These are areas where competitors have an advantage that is causing you to lose deals or churn customers. Recommendations focus on closing critical gaps:
- Which competitor advantages are most frequently cited in lost-deal analysis?
- What is the minimum viable feature set to neutralise this advantage?
- Can you match through partnerships or integrations rather than building?
- What is the cost of not matching — in revenue, market share, or brand perception?

**4. Concede — Areas to Deliberately Not Compete**

These are areas where competing would require disproportionate investment relative to the return, or where competing would dilute your positioning. Recommendations focus on clear-eyed acceptance:
- Which competitor advantages are structural (funding, team size, established network effects)?
- Where would matching require you to compromise your product vision or positioning?
- Can you reframe this gap as a feature of your positioning? ("We are deliberately simpler.")
- How should sales and marketing handle this gap in competitive conversations?

### Recommendation Format

Each recommendation includes:
- **Action category:** Invest, Differentiate, Match, or Concede
- **Area:** The specific capability, market segment, or strategic dimension
- **Recommendation:** 2-3 sentences describing the recommended action
- **Evidence:** References to specific competitive analysis findings
- **Priority:** High, Medium, or Low based on market impact and feasibility
- **Effort estimate:** Relative effort required (Low, Medium, High)
- **Expected impact:** What success looks like and how to measure it

### Prioritisation Criteria

Recommendations are prioritised using a 2x2 matrix of market impact and feasibility:
- **High impact, high feasibility:** Do first — these are quick wins with strategic value
- **High impact, low feasibility:** Plan carefully — these are big bets requiring investment
- **Low impact, high feasibility:** Do opportunistically — nice wins that build momentum
- **Low impact, low feasibility:** Deprioritise — not worth the effort right now

### Quality Standards

- Every recommendation must cite specific evidence from the competitive analysis
- Recommendations must be actionable — a product team should know what to do next
- Trade-offs must be explicit — every recommendation has a cost, and it must be stated
- Time horizons must be specified — is this a next-quarter action or a next-year strategy?
