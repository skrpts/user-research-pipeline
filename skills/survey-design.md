---
type: skill
id: survey-design
title: Survey Design
description: "Designing effective surveys with proper question structure, response scales, and bias mitigation"
tags: [Production, Tested, Strategy, Research]
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

## Survey Design

This skill produces well-structured surveys that yield reliable, actionable data. It covers question writing, response scale design, question ordering, and common bias mitigation.

### Core Capability

Given research objectives and a target audience, this skill generates survey questions and interview guides that are clear, unbiased, and structured to produce useful data. It applies established survey methodology to ensure responses are valid and interpretable.

### Question Types and When to Use Them

**Likert Scale Questions**
Use for: Measuring attitudes, satisfaction, agreement
Format: Statement + 5-point or 7-point scale
Example: "I can easily find the features I need" — Strongly Disagree to Strongly Agree
Rules: Always include a neutral midpoint. Label all scale points, not just endpoints. Use consistent direction (positive to negative or vice versa, but never mix within a survey).

**Multiple Choice Questions**
Use for: Categorisation, behaviour frequency, preference ranking
Format: Question + exhaustive, mutually exclusive options
Rules: Include "Other (please specify)" when the option set may not be exhaustive. Limit to 7 options maximum. Randomise option order where possible to avoid primacy/recency bias.

**Rating Scale Questions**
Use for: Quantifying importance, frequency, or likelihood
Format: Question + numeric scale (typically 1-10)
Rules: Define what the endpoints mean (1 = Not at all important, 10 = Extremely important). Avoid scales with more than 10 points — respondents cannot reliably distinguish between more than 10 levels.

**Open-Ended Questions**
Use for: Exploration, capturing unexpected perspectives, generating quotes
Format: Question + free-text field
Rules: Use sparingly — each open-ended question increases completion time and dropout rate. Place at the end of sections, not the beginning. Provide character guidance (e.g., "in 2-3 sentences").

**Matrix Questions**
Use for: Rating multiple items on the same scale
Format: Grid with items as rows and scale points as columns
Rules: Limit to 5-7 items per matrix. Use when the same scale genuinely applies to all items. Watch for straightlining (respondents selecting the same column for every row).

### Bias Mitigation

**Leading questions:** Never embed the desired answer in the question. "How much do you love our new feature?" assumes the respondent loves it. Use "How would you rate your experience with the new feature?"

**Double-barrelled questions:** Each question must ask about one thing only. "How satisfied are you with the speed and reliability of the product?" asks about two things. Split into two questions.

**Social desirability bias:** For sensitive topics, use indirect framing. Instead of "Do you read the documentation?" try "How frequently do you consult the documentation when encountering a new feature?"

**Acquiescence bias:** Mix positively and negatively worded items. If all statements are positive, respondents tend to agree with everything.

**Order effects:** Place general questions before specific ones. Place easy questions before difficult ones. Place sensitive questions later in the survey when trust has been established.

### Survey Structure

1. **Introduction:** Purpose, estimated time, confidentiality statement (1-2 sentences)
2. **Screening questions:** Verify the respondent meets participation criteria (1-3 questions)
3. **Core questions:** Grouped by topic, with the most important topics first (10-20 questions)
4. **Demographics:** Only if needed for segmentation, placed last (3-5 questions)
5. **Close:** Thank you, next steps, optional contact information

### Length Guidelines

| Audience | Maximum Questions | Maximum Time |
|----------|------------------|--------------|
| Customers (incentivised) | 25 | 10 minutes |
| Customers (unincentivised) | 15 | 5 minutes |
| Internal users | 20 | 8 minutes |
| One-time respondents | 10 | 3 minutes |

### Interview Guide Design

When designing interview guides rather than surveys, this skill also applies. Interview guides follow a conversational flow:
- Opening questions to build rapport and establish context
- Core questions that directly address research objectives
- Probing questions prepared for predictable surface-level responses
- Closing questions to capture anything the guide missed
