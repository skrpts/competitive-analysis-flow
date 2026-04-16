---
type: skill
id: data-analysis
title: Data Analysis
description: "Extracting patterns, trends, and actionable insights from qualitative and quantitative data"
tags: [Production, Tested, Competitive, Data]
context_params:
  analysis_focus:
    label: "Analysis Focus"
    description: "What aspects to focus the analysis on"
    default: ""
    required: true
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 3500
  trigger: manual
---

## Data Analysis

This skill takes raw data — survey responses, usage metrics, interview transcripts, market reports, or competitive intelligence — and extracts structured patterns, trends, and actionable insights.

### Core Capability

Given a dataset and an analysis objective, this skill produces a structured analysis that identifies what the data says, what it means, and what to do about it.

### Analysis Framework

**1. Data Assessment**

Before analysis begins, assess the data:
- **Completeness:** Are there gaps? Missing segments? Underrepresented groups?
- **Quality:** Are there obvious errors, duplicates, or inconsistencies?
- **Relevance:** Does the data actually address the analysis objective?
- **Recency:** Is the data current enough to inform decisions?

Flag any quality issues upfront rather than discovering them mid-analysis.

**2. Pattern Identification**

For quantitative data:
- **Trends:** What is increasing, decreasing, or stable over time?
- **Distributions:** Where do values cluster? Are there outliers?
- **Correlations:** Which variables move together? (Note: correlation is not causation — flag this explicitly)
- **Segments:** Do different groups show meaningfully different patterns?

For qualitative data:
- **Themes:** What topics recur across multiple sources?
- **Sentiment:** What is the overall tone? Where does it shift?
- **Frequency:** How often does each theme appear? (A theme mentioned once is an anecdote, not a finding)
- **Contradictions:** Where do sources disagree? What explains the disagreement?

**3. Insight Extraction**

Transform patterns into insights using the "So what?" test:
- **Pattern:** "Feature X usage dropped 30% in Q3"
- **Insight:** "Users are abandoning Feature X because the recent redesign moved the entry point from the sidebar to a submenu, increasing clicks-to-access from 1 to 3"
- **Recommendation:** "Restore the sidebar shortcut or add a contextual entry point on the dashboard"

Each insight must include:
- The finding (what the data shows)
- The interpretation (what it means)
- The confidence level (how strongly the data supports this interpretation)
- The recommendation (what to do about it)

**4. Synthesis**

Combine individual insights into a coherent narrative:
- Group related insights into themes
- Identify which insights reinforce each other and which conflict
- Prioritise insights by business impact and confidence level
- Surface the 3-5 most important takeaways

### Output Structure

The analysis produces:
- An executive summary (3-5 key findings, one paragraph each)
- A detailed findings section (one section per theme, with supporting data)
- A recommendations table (insight, confidence, impact, recommended action)
- A limitations section (data quality issues, gaps, caveats)
