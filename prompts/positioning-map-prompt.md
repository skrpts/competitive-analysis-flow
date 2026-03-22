---
type: prompt
id: positioning-map-prompt
title: Positioning Map Generator
description: "Create a narrative positioning map based on strategically relevant dimensions with white space analysis"
tags: [Production]
connections:
  - target: market-positioning-analysis
    type: derived_from
  - target: competitive-brief-writer
    type: uses
metadata:
  estimated_duration: "4 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Positioning Map Generator

You are a strategic positioning expert creating a detailed positioning map narrative. Your map must be evidence-based, strategically insightful, and actionable for product and marketing teams.

### Input

This prompt receives all outputs from the previous stages. Use the product name from the feature comparison matrix produced in Stage 2, the feature comparison matrix from Stage 2, the SWOT analysis from Stage 3, and the competitor profiles from Stage 1. Derive strategic priorities from the product description and market segment established in Stage 1.

### Instructions

Create a detailed positioning map narrative that visualises where your product and competitors sit relative to each other along the most strategically important dimensions.

**Step 1: Dimension Selection**

Evaluate the following candidate dimension pairs and select the one that creates the most strategically useful map. The right pair should spread competitors across the space rather than clustering them, and both dimensions should matter to buyers.

Candidate pairs:
- Price point (low to high) vs. Feature depth (basic to complete)
- Ease of use (simple to complex) vs. Capability range (narrow to broad)
- Target segment (SMB to enterprise) vs. Deployment model (self-serve to managed)
- Innovation pace (conservative to modern) vs. Market maturity (new to established)
- Specialisation (vertical/niche to horizontal/general) vs. Integration depth (standalone to ecosystem)

Justify your dimension selection. Explain why the chosen pair provides the most strategic insight for this particular market. If none of the candidate pairs fit well, define a custom pair with justification.

**Step 2: Product Placement**

For each product (your product and all competitors), describe its position on the map:

- **Position:** Where it sits on each axis (use descriptive positioning like "upper-left quadrant" or "centre-right")
- **Justification:** 2-3 specific evidence points explaining why this product belongs at this position
- **Trajectory:** Is this product moving? In which direction? What signals indicate this movement?
- **Cluster membership:** Does this product cluster with others, or does it occupy a unique position?

**Step 3: Quadrant Characterisation**

Describe what each quadrant of the map represents in market terms:

- **Upper-left:** [Description of what products in this region tend to offer and who they serve]
- **Upper-right:** [Description]
- **Lower-left:** [Description]
- **Lower-right:** [Description]

Note which quadrants are crowded and which are sparse. Explain why.

**Step 4: White Space Analysis**

Identify positions on the map where no competitor is strongly placed. For each white space:

- **Location:** Where on the map this gap exists
- **Viability assessment:** Is there genuine customer demand for a product positioned here? What evidence supports this?
- **Strategic fit:** How well does this position align with your product's current trajectory and capabilities?
- **Entry cost:** What would it take to credibly occupy this position? (Low/Medium/High effort)
- **Defensibility:** If you move here, how quickly could competitors follow?

**Step 5: Positioning Recommendation**

Based on the map analysis, recommend a positioning strategy:

- **Current position:** Where your product sits today
- **Recommended position:** Where you should aim to be positioned
- **Gap analysis:** What needs to change (in product, pricing, messaging, or go-to-market) to achieve the recommended position
- **Positioning statement:** Draft a one-sentence positioning statement that captures the recommended position: "For [target customer], [product] is the [category] that [key differentiator], unlike [competitor reference] which [competitor approach]."

### Output Format

Present the analysis in the order above with clear section headings. Use descriptive spatial language to make the map vivid without requiring an actual graphic. Include a summary table showing each product's position on both axes.
