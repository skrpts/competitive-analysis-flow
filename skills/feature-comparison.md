---
type: skill
id: feature-comparison
title: Feature Comparison Matrix
description: "Building a structured feature comparison across all identified competitors along key capability dimensions"
tags: [Production, Competitive, Planning]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 3500
  trigger: manual
---

## Feature Comparison Matrix

This skill builds a detailed, evidence-based feature comparison across your product and all identified competitors, scoring each along the dimensions that matter most in the market.

### Core Capability

Given the competitor discovery output plus your own product name and capabilities, this skill selects the strategically relevant comparison dimensions, scores every product on each, and surfaces the patterns — your advantages, your gaps, market table stakes, and differentiation opportunities.

### Method

1. **Dimension selection:** Choose at least eight dimensions spanning core capabilities, platform/technical, commercial, and user-experience categories. Include only dimensions that genuinely apply to this market.
2. **Scoring:** Rate every product on each dimension (Strong / Adequate / Weak / Absent / Unknown), each with a one-to-two sentence justification grounded in specific evidence.
3. **Pattern analysis:** Read the completed matrix for defensible advantages, competitive vulnerabilities, baseline expectations, white-space dimensions, and competitive clusters.

### Output Structure

A markdown comparison table (products as columns, dimensions as rows) followed by the pattern analysis. The matrix feeds the SWOT, positioning, and brief stages downstream.
