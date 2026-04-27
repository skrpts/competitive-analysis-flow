---
type: workflow
id: competitive-analysis-flow
title: Competitive Analysis Flow
description: "End-to-end workflow for structured competitor research, comparison, and strategic positioning recommendations"
tags: [Production, Tested, Competitive, Planning]
connections:
  - target: competitor-profiling
    type: uses
  - target: market-positioning-analysis
    type: uses
  - target: strategic-recommendation
    type: uses
  - target: data-analysis
    type: uses
  - target: language-polish
    type: uses
  - target: llm-service
    type: runs_on
  - target: competitive-intelligence-framework
    type: references
  - target: competitive-analysis-playbook
    type: references
  - target: competitor-comparison-template
    type: references
  - target: input-gap-check
    type: uses
metadata:
  estimated_duration: "30 minutes"
  avg_tokens: 20000
  trigger: manual
output_step: "language-polish"
composite_steps:
  - "competitor-profiling"
  - "market-positioning-analysis"
  - "strategic-recommendation"
  - "data-analysis"
  - "input-gap-check"
execution:
  - skill: "competitor-profiling"
    step_type: "synthesis"
    prompt: "competitor-discovery"
  - skill: "market-positioning-analysis"
    step_type: "synthesis"
    prompt: "positioning-map-prompt"
  - skill: "strategic-recommendation"
    prompt: "competitive-brief-writer"
    step_type: "synthesis"
  - skill: "data-analysis"
    prompt: "analyse-data"
    step_type: "synthesis"
    context:
      analysis_focus: ""
  - skill: "input-gap-check"
    step_type: "review"
  - skill: "language-polish"
    prompt: "polish-language"
    step_type: "content"
---

## Competitive Analysis Flow

This workflow produces a thorough competitive analysis from initial competitor identification through to strategic positioning recommendations. It follows a five-stage pipeline that builds progressively deeper insight at each stage.

### Stage 1: Competitor Discovery

**Input:** Your product description, market segment, and any known competitors.

1. Invoke the **competitor-discovery** prompt using the **competitor-profiling** skill.
2. The prompt identifies and catalogues competitors across three tiers:
   - **Direct competitors:** Products solving the same problem for the same audience
   - **Indirect competitors:** Products solving a related problem or serving an adjacent audience
   - **Emerging threats:** New entrants, open-source alternatives, or platform features that could displace your solution
3. For each competitor, capture: name, URL, founding year, funding stage, estimated team size, target market, and primary value proposition.
4. **Validation gate:** At least 3 direct competitors and 2 indirect competitors must be identified. If fewer are found, the market segment definition may be too narrow — prompt the user to broaden it.

### Stage 2: Feature Comparison

**Input:** The competitor catalogue from Stage 1.

1. Invoke the **feature-comparison-matrix** prompt.
2. Build a structured comparison across key capability dimensions:
   - Core features (what the product fundamentally does)
   - Pricing model and tiers
   - Integration ecosystem
   - Platform availability (web, mobile, desktop, API)
   - Target company size (SMB, mid-market, enterprise)
3. Each dimension is scored or described consistently across all competitors.
4. **Validation gate:** The matrix must cover at least 8 comparison dimensions. Fewer suggests insufficient depth.

### Stage 3: SWOT Analysis

**Input:** The feature comparison matrix from Stage 2, plus your product's current capabilities.

1. Invoke the **swot-generator** prompt.
2. Generate a SWOT analysis for your product relative to the competitive landscape:
   - **Strengths:** Where your product demonstrably outperforms competitors
   - **Weaknesses:** Where competitors have clear advantages
   - **Opportunities:** Market gaps or trends you could exploit
   - **Threats:** Competitive moves or market shifts that could undermine your position
3. Each SWOT item includes evidence from the feature comparison and a confidence level (High, Medium, Low).
4. **Validation gate:** Each quadrant must contain at least 3 items. An empty or near-empty quadrant suggests analytical blind spots.

### Stage 4: Positioning Map

**Input:** SWOT analysis and feature comparison from Stages 2-3.

1. Invoke the **positioning-map-prompt** using the **market-positioning-analysis** skill.
2. Identify the two most strategically relevant dimensions for positioning (e.g., price vs. feature depth, simplicity vs. power, SMB-focus vs. enterprise-focus).
3. Plot each competitor and your product on these dimensions with narrative justification.
4. Identify positioning white space — areas where no competitor is strongly positioned.
5. **Validation gate:** The positioning narrative must reference specific evidence from the feature comparison. Unsupported positioning claims are flagged for revision.

### Stage 5: Competitive Brief

**Input:** All outputs from Stages 1-4.

1. Invoke the **competitive-brief-writer** prompt using the **strategic-recommendation** skill.
2. Compile findings into an executive-ready competitive brief following the **competitor-comparison-template**.
3. Include strategic recommendations: where to invest, where to differentiate, where to match competitors, and where to concede.
4. **Output:** A complete competitive analysis document ready for leadership review.

### Error Handling

- **Insufficient market data:** If competitor discovery yields too few results, suggest broadening the market segment or provide guidance on manual research to supplement.
- **Stale information:** Flag any competitor data points that could not be verified against recent sources. Recommend a refresh cycle (quarterly for fast-moving markets, biannually for stable markets).
- **Bias detection:** If the SWOT analysis shows no weaknesses or the positioning map places your product at the ideal point on both axes, flag potential confirmation bias and prompt for critical re-evaluation.
- **Missing pricing data:** If competitor pricing is not publicly available, note this explicitly rather than guessing. Suggest methods for obtaining pricing intelligence (trial sign-ups, sales conversations, third-party databases).

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.product_name}}` | Yes | Your product name | `Acme Project Manager` |
| `{{input.your_product_description}}` | Yes | Your product description | `Paste a short brief describing the goal, audience, and constraints.` |
| `{{input.market_segment}}` | Yes | Market segment | `Paste the relevant brief, notes, source material, or dataset here.` |
| `{{input.target_customers}}` | Yes | Target customers | `Mid-market B2B SaaS companies with 50-500 employees` |
| `{{input.any_known_competitors}}` | Yes | Any known competitors | `Paste the relevant brief, notes, source material, or dataset here.` |
| `{{input.your_product_capabilities}}` | No | Your product's current capabilities | `Paste the relevant brief, notes, source material, or dataset here.` |

## Outputs

| Name | Description |
|------|-------------|
| A complete competitive analysis document ready for leadership review | A complete competitive analysis document ready for leadership review |

## Setup

Before running this workflow:

1. No external services required — paste your content directly and provide any supporting context as inputs or source nodes.
2. Review the included documents, assets, or source nodes and customise them to match your team, brand, or domain conventions where needed.
3. No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Most stages work with any capable model; stronger models usually improve synthesis, judgement, and writing quality.
- Extraction, classification, and formatting steps generally run well on smaller or faster models.
- Because there are no vendor-specific integrations here, provider choice is mostly a trade-off between speed, quality, and cost.

## Example Input

To test this workflow immediately after import:

```
Product Name: "Acme Project Manager"
Your Product Description: "Paste a short brief describing the goal, audience, and constraints."
Market Segment: "Paste the relevant brief, notes, source material, or dataset here."
Target Customers: "Mid-market B2B SaaS companies with 50-500 employees"
Any Known Competitors: "Paste the relevant brief, notes, source material, or dataset here."
Your Product Capabilities: "Paste the relevant brief, notes, source material, or dataset here."
```

