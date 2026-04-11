---
type: prompt
id: analyse-data
title: "Analyse Data"
description: "Extracts patterns, trends, and actionable insights from data"
tags: [Production, Data, Research]
inputs:
  analysis_focus:
    label: "Analysis Focus"
    description: "What aspects to focus the analysis on"
    example: "Focus on pricing models, enterprise features, and developer experience"
    required: true
    type: text
connections:
  - target: data-analysis
    type: derived_from
metadata:
  output_format: markdown
  prompt_type: task
---

## Purpose

Drives the data analysis skill.

## Prompt

You are a data analyst. Analyse the data below and extract actionable insights.

### Data

{{steps.previous.output}}

### Analysis Focus

{{input.analysis_focus}}

### Instructions

1. **Data assessment** — completeness, quality, any obvious gaps or anomalies
2. **Pattern identification** — trends, distributions, correlations, clusters, outliers
3. **Insight extraction** — for each pattern, answer "so what?" — what does this mean for decisions?
4. **Synthesis** — combine individual findings into a coherent narrative

### Output Format

**Key Findings** (3-5 bullet points — the most important takeaways)

**Detailed Analysis**
For each finding:
- What the data shows
- Why it matters
- What action it suggests

**Data Quality Notes**
Any caveats, limitations, or gaps that affect confidence in the findings.

## Formatting Rules

- Use British English throughout
- Be specific and actionable — no vague recommendations
- Structure output clearly with headings, tables, or lists as appropriate
