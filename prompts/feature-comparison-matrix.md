---
type: prompt
id: feature-comparison-matrix
title: Feature Comparison Matrix
description: "Build a structured feature comparison across all identified competitors along key capability dimensions"
tags: [Production, Citations, Competitive]
inputs:
  product_name:
    label: "Product Name"
    description: "The name of the product"
    example: "Skrptiq"
    required: true
    type: text
  your_product_capabilities:
    label: "Product Capabilities"
    description: "Key capabilities of your product"
    example: "AI chat, workflow execution, graph visualisation, Hub import"
    required: true
    type: text
connections:
  - target: competitor-profiling
    type: derived_from
  - target: swot-generator
    type: uses
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 3500
  trigger: manual
---

## Feature Comparison Matrix

You are a product analyst building a detailed feature comparison matrix. Your output will be used to identify competitive advantages, gaps, and opportunities for differentiation.

### Input

**Your product name:** {{input.product_name}}

**Your product capabilities:** {{input.your_product_capabilities}}

**Competitor profiles:** {{steps.previous.output}}

**Key evaluation criteria (optional):** Focus on the most strategically relevant dimensions for this market segment.

### Instructions

Build a detailed feature comparison matrix that evaluates your product and all identified competitors across multiple dimensions. The matrix must be structured enough to support quantitative comparison while rich enough to capture qualitative nuances.

**Step 1: Define Comparison Dimensions**

Select at least 8 comparison dimensions from the following categories. Include all dimensions that are relevant to the market; skip only those that genuinely do not apply.

*Core Product Capabilities:*
- Primary features (list the 5-8 most important capabilities)
- Depth of functionality in each core area
- Customisation and configuration options
- Automation capabilities
- AI or intelligent features

*Platform and Technical:*
- Platform availability (web, iOS, Android, desktop, API)
- Integration ecosystem (number and quality of integrations)
- Data import/export capabilities
- API quality and documentation
- Performance and reliability (uptime, speed)
- Security certifications and compliance

*Business and Commercial:*
- Pricing model and price points
- Free tier availability and limitations
- Contract flexibility (monthly vs. annual, cancellation terms)
- Customer support channels and SLA

*User Experience:*
- Ease of onboarding (time to first value)
- Learning curve
- Documentation and educational resources
- Community size and activity
- Mobile experience quality

**Step 2: Score Each Dimension**

For each dimension, evaluate every product using this scale:

| Score | Meaning |
|-------|---------|
| Strong | Industry-leading capability, frequently cited as a strength |
| Adequate | Meets market expectations, no significant complaints |
| Weak | Below market expectations, frequently cited as a limitation |
| Absent | Capability does not exist |
| Unknown | Insufficient data to evaluate |

Accompany each score with a brief justification (1-2 sentences) citing specific evidence.

**Step 3: Identify Patterns**

After completing the matrix, analyse it for patterns:

1. **Your advantages:** Dimensions where you score "Strong" and most competitors score "Adequate" or below. These are your defensible strengths.
2. **Your gaps:** Dimensions where competitors score "Strong" and you score "Adequate" or below. These are your competitive vulnerabilities.
3. **Market table stakes:** Dimensions where everyone scores "Adequate" or "Strong." These are baseline expectations, not differentiators.
4. **Differentiation opportunities:** Dimensions where everyone scores "Weak" or "Absent." These are potential areas for category leadership.
5. **Competitive clusters:** Groups of competitors that score similarly across most dimensions. These represent strategic groups within the market.

### Output Format

Present the comparison as a markdown table with products as columns and dimensions as rows. Follow the table with the pattern analysis. Use clear headings and bullet points for the analysis section.
