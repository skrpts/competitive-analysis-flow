---
type: skill
id: competitor-profiling
title: Competitor Profiling
description: "Building detailed competitor profiles with structured data across multiple dimensions"
tags: [Production, Tested]
connections:
  - target: llm-service
    type: runs_on
  - target: competitive-intelligence-framework
    type: references
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 3500
  trigger: manual
---

## Competitor Profiling

This skill enables the systematic construction of competitor profiles that go beyond surface-level comparisons. Each profile captures the strategic, operational, and market characteristics of a competitor in a structured format suitable for quantitative and qualitative analysis.

### Core Capability

Given a market segment and product context, this skill identifies competitors and builds detailed profiles for each. It distinguishes between direct competitors (same problem, same audience), indirect competitors (adjacent problem or audience), and emerging threats (new entrants or substitutes).

### Profiling Dimensions

Each competitor profile captures data across the following dimensions:

**1. Company Fundamentals**
- Company name, headquarters, founding year
- Funding stage and total funding raised (if available)
- Estimated team size and growth trajectory
- Public or private status
- Key leadership (CEO, CPO, CTO)

**2. Product Characteristics**
- Primary product offering and value proposition
- Platform availability (web, mobile, desktop, API, CLI)
- Technology stack (where publicly known)
- Integration ecosystem (what tools it connects with)
- Release cadence and recent major launches

**3. Market Position**
- Target customer segment (SMB, mid-market, enterprise)
- Geographic focus
- Estimated market share or user base
- Notable customers or case studies
- Industry verticals served

**4. Business Model**
- Pricing structure (freemium, subscription, usage-based, perpetual licence)
- Price points for key tiers
- Free tier limitations
- Enterprise pricing approach (public vs. sales-led)

**5. Go-to-Market Strategy**
- Primary acquisition channels (organic, paid, sales-led, product-led, partnerships)
- Content strategy (blog, YouTube, podcasts, community)
- Developer relations activity (if applicable)
- Partnership and marketplace presence

**6. Strengths and Vulnerabilities**
- Commonly cited strengths in user reviews
- Commonly cited complaints or limitations
- Recent strategic moves (acquisitions, pivots, market expansion)
- Known technical debt or platform limitations

### Data Quality Standards

- Every data point should be sourced or qualified with a confidence level
- Distinguish between verified facts (from company websites, press releases, financial filings) and estimates (from third-party databases, review analysis, educated inference)
- Flag data points older than 12 months as potentially stale
- Acknowledge gaps explicitly rather than filling them with speculation

### Output Structure

Profiles are structured as standardised data cards that can be compared side-by-side. Each card follows the same six-dimension structure, making it straightforward to identify where competitors differ and where they cluster.

### Anti-Patterns

- **Vanity profiling:** Focusing only on where your product outperforms. Profiles must be objective.
- **Feature-only analysis:** Products compete on more than features — brand, pricing, community, and ecosystem all matter.
- **Snapshot thinking:** A competitor's current state is less important than their trajectory. Note growth direction, not just current position.
