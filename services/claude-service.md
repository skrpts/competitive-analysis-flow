---
type: service
id: claude-service
title: Claude Service
description: "How this skrpt uses Anthropic Claude for competitive research, analysis, and strategic recommendation"
tags: [Production, Tested]
connections: []
metadata:
  provider: "anthropic"
  model: "claude-sonnet"
  estimated_duration: "N/A"
---

## Claude Service — Competitive Analysis Flow

This skrpt uses Anthropic Claude as its primary AI service for all analytical and generative tasks within the competitive analysis pipeline.

### Usage Pattern

Claude is invoked at each stage of the workflow:

1. **Competitor Discovery** — Claude identifies and profiles competitors across direct, indirect, and emerging threat tiers. This requires broad market knowledge, the ability to categorise competitors by strategic relevance, and structured data extraction from available information.

2. **Feature Comparison** — Claude builds a multi-dimensional comparison matrix. This requires the ability to evaluate products along consistent dimensions and score them fairly, resisting bias towards the user's own product.

3. **SWOT Analysis** — Claude generates an evidence-based SWOT analysis. This requires critical thinking, the ability to identify weaknesses honestly, and the capacity to spot cross-quadrant strategic intersections.

4. **Positioning Map** — Claude creates a narrative positioning map. This requires spatial reasoning, the ability to select meaningful strategic dimensions, and white space identification.

5. **Competitive Brief Assembly** — Claude compiles all findings into a cohesive executive brief. This requires synthesis, prioritisation, and the ability to distil complex analysis into actionable recommendations.

### Configuration

- **Temperature:** 0.4 for analytical tasks (profiling, comparison, SWOT), 0.6 for strategic tasks (positioning, recommendations)
- **Max tokens:** 4000 per invocation, 8000 for the final brief assembly
- **Context window:** The full pipeline accumulates context. Each stage receives the outputs of all previous stages.

### Web Search Integration

This skrpt benefits from web search capabilities when available. Claude can use web search to:
- Verify competitor data points (pricing, features, funding)
- Identify recent competitor announcements or strategic moves
- Discover emerging competitors not initially known to the user

When web search is unavailable, Claude relies on its training data and the context provided by the user.

### Requirements

- An active Anthropic API key or Claude CLI access
- Sufficient token quota for the full pipeline (approximately 20,000 tokens per analysis)
- Optional: web search access for real-time competitive data
