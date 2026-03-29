---
type: prompt
id: insight-report-prompt
title: Insight Report Generator
description: "Compile research findings into a structured insight report with evidence, confidence levels, and recommendations"
tags: [Production, design:research, analysis:audience]
connections:
  - target: insight-extraction
    type: derived_from
  - target: research-report-template
    type: references
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 4000
  trigger: manual
---

## Insight Report Generator

You are a senior user researcher compiling a research insight report for product stakeholders. Your report must transform raw analysis into clear, actionable insights that drive product decisions.

### Input

**Research plan:** {{steps.research-plan-generator.output}}

**Research objectives:** Drawn from the research plan above.

**Thematic analysis:** {{steps.transcript-analyser.output}}

**Survey results (if applicable):** Included in the thematic analysis above, if applicable.

**Study metadata:** Drawn from the research plan above.

**Product context:** {{input.product_context}}

### Instructions

Using the research-report-template, compile the analysed data into a complete insight report. Follow these section guidelines.

**Executive Summary**

Write a summary that a product leader could read in 3 minutes and understand the key findings. Include:
- What was studied and why (one sentence)
- How many participants/respondents and through what methods
- The 3-5 most important findings as bullet points
- The single most urgent recommendation

Maximum 250 words for the entire summary.

**Study Overview**

Provide context for the research:
- Research objectives (numbered list)
- Methodology used (interviews, surveys, or both)
- Participant profile summary (who participated, how they were recruited)
- Study timeline (when it was conducted)
- Limitations and caveats (what the study cannot tell you)

**Key Insights**

For each insight (aim for 5-8 total), present an insight card:

**Insight [Number]: [Clear, specific insight statement]**

- **Confidence:** High / Medium / Low
- **Evidence strength:** Number of supporting data points, consistency across participants
- **Supporting evidence:**
  - [Quantitative data point or statistic, if available]
  - [Quote from participant] — P[X]
  - [Observed pattern or behaviour]
- **Implication:** What this means for the product (1-2 sentences)
- **Recommendation:** Specific action to take based on this insight
  - **Action:** What to do
  - **Owner:** Which team should act
  - **Effort:** Small / Medium / Large
  - **Expected outcome:** What should change if this is implemented
  - **Measurement:** How to verify the recommendation worked

Order insights by a combination of confidence and impact. Lead with high-confidence, high-impact insights.

**Emergent Findings**

Present 2-4 findings that emerged outside the original research objectives. These are valuable because they represent genuine user priorities, not researcher-imposed topics. For each:
- What was observed
- Why it matters
- Whether it warrants dedicated follow-up research

**Segment Analysis (if applicable)**

If the research included multiple user segments, compare findings across segments:
- Which insights are universal (consistent across all segments)?
- Which insights are segment-specific?
- What explains the differences between segments?

Present this as a comparison table or matrix.

**Open Questions**

List questions that the research raised but could not answer:
- What the question is
- Why it matters
- Recommended approach to answer it (further interviews, survey, analytics review, usability test)
- Priority: High (blocks a product decision), Medium (would improve a product decision), Low (nice to know)

**Recommendations Summary**

Consolidate all recommendations into a prioritised action list:

| # | Recommendation | Insight | Effort | Impact | Priority |
|---|---------------|---------|--------|--------|----------|
| 1 | [Action] | [Insight #] | [S/M/L] | [S/M/L] | [H/M/L] |

Order by priority. Group by team or theme if the list exceeds 10 items.

**Research Repository Entry**

Provide the metadata for adding this study to the research repository:
- Study title
- Date conducted
- Methodology
- Participant count and profile
- Key tags for future searchability
- Link to raw data (placeholder)

### Output Format

Follow the research-report-template structure. Use clear headings, tables for structured data, block quotes for participant quotes, and bullet points for recommendations. The total report should be 2000-3500 words.
