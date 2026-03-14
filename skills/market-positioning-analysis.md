---
type: skill
id: market-positioning-analysis
title: Market Positioning Analysis
description: "Analysing market positioning across strategic dimensions and identifying competitive white space"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
  - target: competitive-intelligence-framework
    type: references
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Market Positioning Analysis

This skill analyses how products are positioned within a market and identifies gaps where differentiated positioning is possible. It transforms raw competitive data into strategic spatial understanding.

### Core Capability

Given a feature comparison matrix and SWOT analysis, this skill identifies the most strategically relevant dimensions for positioning, maps competitors and your product along these dimensions, and highlights white space — areas of the market where no competitor is strongly positioned.

### Dimension Selection

The first step is identifying which two dimensions create the most strategically useful positioning map. Common dimension pairs include:

- **Price vs. Feature depth** — Useful when the market has clear economy and premium segments
- **Simplicity vs. Power** — Useful for products where ease of use trades off against capability
- **SMB focus vs. Enterprise focus** — Useful when competitors serve different company sizes
- **Horizontal vs. Vertical** — Useful when some competitors specialise in specific industries while others are general-purpose
- **Self-serve vs. Sales-led** — Useful when go-to-market strategy is a key differentiator
- **Established vs. Innovative** — Useful when market disruption is occurring

The selected dimensions must be:
- **Independent:** Movement along one axis does not necessitate movement along the other
- **Meaningful:** Users and buyers actually care about these dimensions
- **Differentiating:** Competitors spread across the space rather than clustering in one area

### Positioning Method

For each product (competitors and your own):

1. **Evidence collection:** Gather concrete evidence for where the product sits on each dimension. Pricing data, feature lists, customer reviews, marketing language, and case studies all provide positioning signals.

2. **Placement justification:** Assign a position on each dimension with explicit justification. Avoid "gut feel" placement — every position should reference at least two evidence points.

3. **Trajectory annotation:** Note whether the product is moving on either dimension. A competitor currently positioned as "simple" but rapidly adding features is on a trajectory towards "powerful."

### White Space Identification

White space exists where:
- No competitor occupies a region of the positioning map
- The region represents a viable market position (not white space simply because nobody wants to be there)
- Your product could credibly occupy the space given its current capabilities and trajectory

For each white space identified, assess:
- **Viability:** Is there genuine customer demand for a product positioned here?
- **Accessibility:** How much would your product need to change to occupy this space?
- **Defensibility:** If you move into this space, how easily could competitors follow?

### Output Structure

The positioning analysis produces:
- A narrative positioning map describing where each player sits and why
- A white space assessment identifying 2-4 potential positioning opportunities
- A recommended positioning statement for your product
- Risks and trade-offs associated with the recommended position

### Limitations

- Positioning analysis reflects a point in time. Markets shift, and competitors reposition. Recommend a refresh frequency.
- Two-dimensional maps necessarily simplify reality. Acknowledge what the chosen dimensions do not capture.
- White space is not always opportunity. Sometimes a space is empty because the market has rejected that combination.
