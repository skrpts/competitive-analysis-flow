---
type: prompt
id: swot-generator
title: SWOT Analysis Generator
description: "Generate a structured SWOT analysis for your product relative to the competitive landscape"
tags: [Production]
connections:
  - target: market-positioning-analysis
    type: derived_from
  - target: positioning-map-prompt
    type: uses
metadata:
  estimated_duration: "4 minutes"
  avg_tokens: 3000
  trigger: manual
---

## SWOT Analysis Generator

You are a strategic analyst producing a SWOT analysis that is evidence-based, honest, and actionable. Your analysis must resist the temptation to inflate strengths or downplay weaknesses.

### Input

- **Competitor profiles:** {{steps.competitor-discovery.output}}
- **Feature comparison matrix:** {{steps.feature-comparison-matrix.output}}

Use the product name and capabilities from the feature comparison matrix, and the competitor profiles as the evidence base for this SWOT analysis.

### Instructions

Using the feature comparison matrix and competitor profiles as your evidence base, produce a detailed SWOT analysis for the specified product. Every item in every quadrant must be grounded in specific data from the competitive analysis.

**Strengths — Internal Advantages**

Identify areas where your product demonstrably outperforms competitors. For each strength:
- **Title:** A clear, specific label (not "great product" but "fastest time-to-first-value in the category")
- **Evidence:** Specific data points from the feature comparison or competitor profiles that support this claim
- **Confidence:** High (supported by multiple data points), Medium (supported by limited data), or Low (inferred from indirect evidence)
- **Sustainability:** How easy would it be for a competitor to replicate this advantage? Rate as Durable (hard to copy), Moderate (copyable with effort), or Fragile (easily replicated)

Include a minimum of 3 strengths. If you struggle to find 3, that itself is a significant finding.

**Weaknesses — Internal Disadvantages**

Identify areas where competitors have clear advantages over your product. Apply the same rigour:
- **Title:** Specific and honest
- **Evidence:** What competitors do better and how it manifests (customer reviews, feature gaps, pricing disadvantage)
- **Impact:** How this weakness affects customer acquisition, retention, or expansion
- **Addressability:** How difficult would it be to close this gap? Rate as Quick Fix, Moderate Effort, Major Initiative, or Structural (requires fundamental changes)

Include a minimum of 3 weaknesses. A SWOT with no meaningful weaknesses is dishonest and strategically dangerous.

**Opportunities — External Favourables**

Identify market trends, competitor vulnerabilities, or unmet needs that your product could exploit:
- **Title:** A specific opportunity statement
- **Source:** What market signal or competitive gap creates this opportunity (e.g., "Competitor X's recent pricing increase has caused customer dissatisfaction")
- **Time sensitivity:** Is this opportunity persistent, time-limited, or fleeting?
- **Requirements:** What would your product need to do or have to seize this opportunity?
- **Potential impact:** Small, Medium, or Large in terms of market share or revenue

Include a minimum of 3 opportunities.

**Threats — External Risks**

Identify competitive moves, market shifts, or external forces that could undermine your position:
- **Title:** A specific threat description
- **Source:** What is driving this threat (competitor action, market trend, regulatory change, technological shift)
- **Probability:** How likely is this threat to materialise? High, Medium, or Low
- **Impact if realised:** What would the consequence be for your product or business?
- **Mitigation options:** 1-2 actions that could reduce the probability or impact

Include a minimum of 3 threats.

**Cross-Quadrant Analysis**

After completing all four quadrants, identify strategic intersections:
- **Strength-Opportunity matches:** Where a strength positions you to seize a specific opportunity
- **Weakness-Threat compounds:** Where a weakness makes a specific threat more dangerous
- **Strength-Threat tensions:** Where a strength could be undermined by a specific threat
- **Weakness-Opportunity gaps:** Where a weakness prevents you from seizing a specific opportunity

These intersections are the most strategically valuable insights in the entire analysis.

### Output Format

Present each quadrant with a clear heading, then the cross-quadrant analysis as a separate section. Use tables for structured data and bullet points for narrative analysis.
