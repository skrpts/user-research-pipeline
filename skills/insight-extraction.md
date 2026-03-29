---
type: skill
id: insight-extraction
title: Insight Extraction
description: "Extracting and prioritising actionable insights from qualitative and quantitative research data"
tags: [Production, Tested, Data, Optimisation]
connections:
  - target: llm-service
    type: runs_on
  - target: user-research-methods
    type: references
metadata:
  estimated_duration: "4 minutes"
  avg_tokens: 3000
  trigger: manual
---

## Insight Extraction

This skill transforms analysed research data — coded themes, survey statistics, sentiment maps — into actionable insights that drive product decisions. It bridges the gap between "what we observed" and "what we should do about it."

### Core Capability

Given thematically coded interview data and/or analysed survey responses, this skill produces a prioritised set of insights. Each insight is a statement of what was learned, supported by evidence, assessed for confidence, and paired with a recommended action.

### What Makes an Insight

An insight is not a data point. "72% of users find onboarding confusing" is a finding. The insight is: "Users expect to reach their first meaningful outcome within 5 minutes, but the current onboarding flow takes an average of 15 minutes because it front-loads configuration that could be deferred."

Characteristics of a strong insight:
- **Specific:** Names the who, what, and why — not just the what
- **Surprising or clarifying:** Tells stakeholders something they did not already know, or reframes something they assumed differently
- **Actionable:** Points towards a product decision or direction
- **Supported:** Grounded in multiple data points, not a single anecdote
- **Contextualised:** Explains the user's situation, motivations, and constraints

### Extraction Process

**1. Answer the Research Questions**

Start with the original research objectives. For each objective, identify the findings that directly address it. Synthesise these findings into an insight statement that answers the question.

If a research question cannot be answered with confidence, state this explicitly. "We did not collect sufficient data to answer this question" is a valid and important finding.

**2. Surface Emergent Insights**

Review the coded themes for patterns that go beyond the original research questions. Important insights often emerge from unexpected directions. These should be presented separately as "emergent findings" to avoid scope confusion.

**3. Triangulate Evidence**

Where both qualitative and quantitative data exist, look for convergence and divergence:
- **Convergence:** Interview themes align with survey data — high confidence
- **Divergence:** Interview themes contradict survey data — investigate further
- **Complementarity:** Qualitative data explains the "why" behind quantitative patterns

**4. Assess Confidence**

Rate each insight on a three-level confidence scale:

| Level | Definition | Evidence Threshold |
|-------|-----------|-------------------|
| High | Strong, consistent evidence from multiple sources | 5+ data points, no contradicting evidence |
| Medium | Moderate evidence, some inconsistency | 3-4 data points, minor contradictions |
| Low | Limited evidence, significant uncertainty | 1-2 data points, or contradicting evidence exists |

**5. Prioritise by Impact**

Rank insights by their potential impact on product decisions:
- **Critical:** Would change the product roadmap or strategy if acted upon
- **Important:** Would influence feature design or prioritisation
- **Informative:** Adds context but does not require immediate action

### Recommendation Framework

Each insight should include a recommended action using this structure:
- **What to do:** A specific, actionable recommendation (not "improve onboarding" but "defer organisation settings to post-first-value and add a guided walkthrough for the core workflow")
- **Who should own it:** Which team or role is best positioned to act
- **Effort estimate:** Relative effort to implement (Small, Medium, Large)
- **Expected outcome:** What should change if the recommendation is implemented
- **How to measure:** How to verify the recommendation had the desired effect

### Output Structure

The insight report contains:
- An executive summary of key findings (5-7 bullet points)
- Research objectives with their corresponding insights
- Emergent findings section
- Detailed insight cards (one per insight with evidence, confidence, and recommendation)
- Open questions requiring further research
- Recommended next steps
