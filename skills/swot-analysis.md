---
type: skill
id: swot-analysis
title: SWOT Analysis Generator
description: "Generating a structured, evidence-based SWOT analysis for your product relative to the competitive landscape"
tags: [Production, Competitive, Planning]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "4 minutes"
  avg_tokens: 3000
  trigger: manual
---

## SWOT Analysis Generator

This skill produces a rigorous SWOT analysis that resists inflating strengths or downplaying weaknesses. Every item in every quadrant is grounded in specific evidence from the competitive analysis.

### Core Capability

Given the competitor profiles and the feature comparison matrix as the evidence base, this skill derives Strengths, Weaknesses, Opportunities, and Threats for your product — each with a specific title, supporting evidence, and a qualifier (confidence, sustainability, addressability, time-sensitivity, or probability as appropriate).

### Method

1. **Quadrant population:** Identify a minimum of three items per quadrant, each traceable to concrete data points in the feature comparison or competitor profiles.
2. **Honesty check:** A SWOT with no meaningful weaknesses is dishonest and strategically dangerous — surface real gaps.
3. **Cross-quadrant analysis:** Find the strategic intersections (strength-opportunity matches, weakness-threat compounds, strength-threat tensions, weakness-opportunity gaps) — the most valuable insights in the analysis.

### Output Structure

Each quadrant under a clear heading, followed by the cross-quadrant analysis. The SWOT feeds the positioning and brief stages downstream.
