---
type: service
id: claude-service
title: Claude Service
description: "How this skrpt uses Anthropic Claude for research planning, instrument design, and insight synthesis"
tags: [Production, Tested]
connections: []
metadata:
  provider: "anthropic"
  model: "claude-sonnet"
  estimated_duration: "N/A"
---

## Claude Service — User Research Pipeline

This skrpt uses Anthropic Claude as its primary AI service for research planning, instrument design, data analysis, and insight synthesis.

### Usage Pattern

Claude is invoked at each stage of the pipeline:

1. **Research Planning** — Claude designs the research study, selecting methodology, defining participant criteria, and building a timeline. This requires knowledge of research methods and the ability to match methods to objectives.

2. **Interview Guide Building** — Claude creates structured interview guides with opening, core, probing, and closing questions. This requires understanding of conversational flow and the ability to write open-ended, non-leading questions.

3. **Survey Question Writing** — Claude designs survey questionnaires with proper question types, response scales, and bias mitigation. This requires survey methodology expertise and attention to question design anti-patterns.

4. **Transcript Analysis** — Claude performs thematic coding on interview transcripts, identifying themes, extracting quotes, and mapping sentiment. This requires careful, systematic reading and the ability to identify patterns across multiple data sources. This is the most token-intensive stage.

5. **Insight Report Generation** — Claude compiles findings into an actionable insight report with confidence levels, recommendations, and open questions. This requires synthesis and the ability to translate findings into product decisions.

### Configuration

- **Temperature:** 0.2 for analytical tasks (transcript analysis, coding), 0.4 for design tasks (research planning, guide building, survey design), 0.5 for synthesis tasks (insight reporting)
- **Max tokens:** 4000 per invocation, 8000 for transcript analysis (which may process multiple transcripts)
- **Context window:** The pipeline accumulates context progressively. Transcript analysis may require the full context window for studies with many interviews.

### Data Sensitivity

This pipeline processes potentially sensitive data:
- Interview transcripts may contain personally identifiable information
- Survey responses may include confidential opinions
- Claude processes this data in-session only — no data is retained between invocations
- Users should ensure their Anthropic API usage terms permit processing of the data types in their study

### Requirements

- An active Anthropic API key or Claude CLI access
- Sufficient token quota for the full pipeline (approximately 18,000 tokens per study)
- No external network access required beyond the Anthropic API endpoint
