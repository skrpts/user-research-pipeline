---
type: workflow
id: user-research-pipeline
title: User Research Pipeline
description: "End-to-end workflow for planning, conducting, and synthesising user research into actionable insights"
tags: [Production, Tested, Research, Audience]
connections:
  - target: interview-synthesis
    type: uses
  - target: survey-design
    type: uses
  - target: insight-extraction
    type: uses
  - target: data-analysis
    type: uses
  - target: llm-service
    type: runs_on
  - target: user-research-methods
    type: references
  - target: research-ethics-guide
    type: references
  - target: research-repository-guide
    type: references
  - target: interview-note-template
    type: references
  - target: research-report-template
    type: references
  - target: evidence-claim-check
    type: uses
  - target: pii-masking
    type: uses
  - target: dedup-and-merge
    type: uses
metadata:
  estimated_duration: "25 minutes"
  avg_tokens: 18000
  trigger: manual
output_step: "insight-extraction"
composite_steps:
  - "interview-synthesis"
  - "survey-design"
  - "insight-extraction"
  - "data-analysis"
  - "evidence-claim-check"
  - "pii-masking"
  - "dedup-and-merge"
execution:
  - skill: "interview-synthesis"
    step_type: "synthesis"
  - skill: "survey-design"
    step_type: "generation"
  - skill: "insight-extraction"
    step_type: "synthesis"
  - skill: "data-analysis"
    step_type: "synthesis"
  - skill: "pii-masking"
    step_type: "content"
  - parallel:
    - skill: "evidence-claim-check"
      step_type: "review"
    - skill: "dedup-and-merge"
      step_type: "synthesis"
---

## User Research Pipeline

This workflow guides you from a research question through to actionable insights. It covers research planning, instrument design (interview guides and surveys), data analysis, and insight synthesis. The pipeline supports both qualitative (interviews) and quantitative (surveys) research methods.

### Stage 1: Research Planning

**Input:** A research question or set of questions, product context, and target user segments.

1. Invoke the **research-plan-generator** prompt.
2. The prompt produces a structured research plan covering:
   - Research objectives (what you want to learn)
   - Methodology selection (interviews, surveys, or both — with justification)
   - Participant criteria (who to recruit, how many, screening questions)
   - Timeline and logistics (how long the study will take, resources needed)
   - Analysis approach (how findings will be processed)
3. **Validation gate:** The plan must include clear, answerable research objectives. Vague objectives ("understand user needs") are rejected in favour of specific ones ("identify the top 3 barriers to onboarding completion for new users in their first week").

### Stage 2: Instrument Design

**Input:** The research plan from Stage 1.

This stage branches based on the chosen methodology:

**Path A: Interview Guide (if methodology includes interviews)**
1. Invoke the **interview-guide-builder** prompt using the **survey-design** skill.
2. The prompt generates a structured interview guide with:
   - Opening questions (rapport building, background)
   - Core questions (directly addressing research objectives)
   - Probing follow-ups (for when participants give surface-level answers)
   - Closing questions (anything else, future contact)
3. **Validation gate:** Each research objective must be addressed by at least 2 core questions. Probing questions must be ready for predictable shallow responses.

**Path B: Survey Design (if methodology includes surveys)**
1. Invoke the **survey-question-writer** prompt using the **survey-design** skill.
2. The prompt generates survey questions with:
   - Proper question types (Likert scales, multiple choice, open-ended)
   - Response scale design (balanced, labelled, appropriate length)
   - Question ordering (general to specific, non-leading sequencing)
   - Estimated completion time
3. **Validation gate:** The survey must be completable in under 10 minutes. Questions must be free of leading language, double-barrelling, and assumed knowledge.

**Path C: Both** — run Path A and Path B sequentially.

### Stage 3: Data Analysis

**Input:** Interview transcripts and/or survey responses.

1. Invoke the **transcript-analyser** prompt using the **interview-synthesis** skill.
2. For interview transcripts, the analysis produces:
   - Thematic coding (identifying recurring themes across interviews)
   - Quote extraction (pulling verbatim quotes that best illustrate each theme)
   - Sentiment mapping (which topics generated positive, negative, or mixed sentiment)
   - Participant-level summaries (key takeaways from each individual interview)
3. For survey responses, the analysis produces:
   - Quantitative summaries (distributions, means, medians for scaled questions)
   - Open-response coding (thematic analysis of free-text answers)
   - Cross-tabulation (how responses vary by demographic or segment)
4. **Validation gate:** Themes must be supported by at least 3 data points (quotes or responses). Single-instance observations are noted as anecdotes, not themes.

### Stage 4: Insight Synthesis

**Input:** Analysed data from Stage 3.

1. Invoke the **insight-report-prompt** using the **insight-extraction** skill.
2. The prompt compiles findings into an insight report using the **research-report-template**:
   - Key insights (findings that answer the research objectives)
   - Supporting evidence (quotes, data points, patterns)
   - Confidence levels (how strongly the evidence supports each insight)
   - Actionable recommendations (what to do based on each insight)
   - Open questions (what remains unanswered and requires further research)
3. **Output:** A complete research report ready for stakeholder presentation.

### Error Handling

- **Insufficient participants:** If fewer than 5 interviews are available, flag that findings may not be representative. Recommend continuing recruitment before drawing conclusions.
- **Low survey response rate:** If fewer than 30 responses are collected, note statistical limitations. Recommend extending the survey window or adjusting recruitment.
- **Contradictory findings:** When interview and survey data conflict, present both perspectives. Recommend follow-up research to resolve the contradiction.
- **Scope creep:** If analysis reveals important themes outside the original research objectives, note them in a separate "Emergent Findings" section rather than expanding the scope.
- **Sensitive data:** Follow the research-ethics-guide for handling personally identifiable information. Anonymise all quotes and data points in the final report.

## Inputs

| Name | Required | Description | Example |
|------|----------|-------------|---------|
| `{{input.research_questions}}` | Yes | The research question(s) to investigate | `How do users discover new features after onboarding?` |
| `{{input.product_context}}` | Yes | Background on the product and its current state | `B2B project management tool, 6 months post-launch` |
| `{{input.target_segments}}` | Yes | User segments to include in research | `Power users (daily), casual users (weekly), churned users` |
| `{{input.transcripts}}` | No | Interview transcripts and/or survey responses to analyse | `Paste raw transcripts or survey CSV data` |
| `{{input.resources}}` | No | Available resources for the research | `1 researcher, 2 weeks, access to UserTesting panel` |
| `{{input.timeline}}` | No | Timeline constraints | `Must be completed within 3 weeks` |
| `{{input.interview_duration}}` | No | Duration for each interview | `45 minutes` |
| `{{input.focus_areas}}` | No | Specific areas to explore in interviews | `Onboarding experience, feature discovery` |
| `{{input.survey_type}}` | No | Type of survey to create | `Exploratory` |
| `{{input.max_completion_time}}` | No | Maximum survey completion time | `8 minutes` |
| `{{input.hypotheses}}` | No | Key hypotheses to test in the survey | `Users who complete onboarding are 2x more likely to return` |
| `{{input.interview_count}}` | No | Number of interviews conducted | `8` |
| `{{input.participant_descriptions}}` | No | Descriptions of interview participants | `P1: Product manager, daily user. P2: Designer, weekly user.` |

## Outputs

| Name | Description |
|------|-------------|
| Research plan | Structured plan covering methodology, timeline, and participant criteria |
| Interview guide / survey | Ready-to-use interview script or survey questions tailored to research goals |
| Thematic analysis | Coded themes with supporting evidence from transcripts and responses |
| Insight report | Final report with key findings, recommendations, and anonymised supporting quotes |

## Setup

Before running this workflow:

1. **Prepare your research materials** — have transcripts, survey responses, or both ready to paste into the pipeline

No specific AI provider or API key is required beyond your configured skrptiq LLM provider.

## Provider Notes

- Transcript analysis is the most token-intensive stage — benefits from a model with a large context window
- For multiple long transcripts, consider processing them one at a time rather than all at once
- Thematic coding quality improves with models that can hold the full dataset in context

## Example Input

To test this workflow immediately after import:

```
Research questions: How do first-time users decide whether to continue using the product after their first session?
Product context: A personal finance tracking app, launched 3 months ago, seeing 40% drop-off after day 1.
Target segments: New users who completed onboarding, new users who abandoned onboarding
Transcripts: [Paste 2-3 interview transcripts or a set of survey responses here]
```
