---
type: skill
id: interview-synthesis
title: Interview Synthesis
description: "Synthesising qualitative interview data into structured insights through thematic coding and pattern recognition"
tags: [Production, Tested]
connections:
  - target: claude-service
    type: runs_on
  - target: user-research-methods
    type: references
metadata:
  estimated_duration: "5 minutes"
  avg_tokens: 3500
  trigger: manual
---

## Interview Synthesis

This skill transforms raw qualitative interview data — transcripts, notes, recordings — into structured, analysable insights. It applies systematic thematic coding to identify patterns across multiple interviews and extract meaningful findings.

### Core Capability

Given a set of interview transcripts or notes, this skill produces a structured analysis that identifies recurring themes, extracts supporting evidence, maps participant sentiment, and surfaces insights that answer the original research questions.

### Synthesis Method

The synthesis follows a rigorous five-step process:

**1. Familiarisation**

Read through all transcripts or notes without coding. Note initial impressions, recurring phrases, emotional moments, and surprising statements. This step prevents premature categorisation and ensures the analysis is grounded in the full data set.

**2. Initial Coding**

Work through each transcript line by line, assigning descriptive codes to meaningful segments. Codes should be:
- **Descriptive:** Summarise the content ("onboarding frustration", "pricing confusion", "feature discovery")
- **In-vivo where possible:** Use the participant's own language when it captures the meaning well
- **Granular:** Prefer specific codes over broad ones. "Cannot find search function" is better than "usability issue"
- **Consistent:** Apply the same code to similar segments across different transcripts

**3. Theme Development**

Group related codes into higher-level themes. A theme is a pattern that captures something meaningful about the data in relation to the research question. Each theme should:
- Be supported by data from at least 3 participants (for studies with 5+ participants)
- Be distinct from other themes (minimal overlap)
- Be relevant to the research objectives
- Have a clear, descriptive name and a one-sentence definition

**4. Quote Extraction**

For each theme, extract 2-4 verbatim quotes that best illustrate the theme. Selected quotes should:
- Be concise (1-3 sentences, trim surrounding context)
- Be representative of the broader pattern (not outliers)
- Come from different participants where possible
- Be anonymised (replace names, companies, and identifying details with placeholders)

**5. Sentiment Mapping**

For each theme, assess the overall participant sentiment:
- **Positive:** Participants spoke about this topic with enthusiasm, satisfaction, or approval
- **Negative:** Participants expressed frustration, disappointment, or criticism
- **Mixed:** Participants held divergent views, or individual participants expressed ambivalence
- **Neutral:** Participants discussed this topic factually without strong emotional valence

### Output Structure

The synthesis produces:
- A theme summary table listing each theme, its frequency (number of participants who mentioned it), sentiment, and a one-sentence description
- A detailed section for each theme with supporting quotes and analytical commentary
- A participant-level summary noting the 2-3 key takeaways from each individual interview
- A cross-cutting analysis identifying relationships between themes (e.g., participants who mentioned Theme A also tended to mention Theme B)

### Quality Standards

- **Saturation tracking:** Note when new interviews stop producing new codes. If the last 2-3 interviews produced no new themes, saturation has likely been reached.
- **Disconfirming evidence:** Actively search for data that contradicts emerging themes. Include counter-examples in the analysis.
- **Researcher reflexivity:** Acknowledge the analyst's assumptions and how they might influence interpretation.
- **Audit trail:** Maintain a clear link from insight back to raw data so findings can be verified.
