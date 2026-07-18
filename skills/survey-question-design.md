---
type: skill
id: survey-question-design
title: Survey Question Design
description: "Deriving survey questions from the research plan, with proper response scales, bias mitigation, and logical flow"
tags: [Production, Research, Audience]
connections:
  - target: llm-service
    type: runs_on
metadata:
  estimated_duration: "3 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Survey Question Design

This skill turns an approved research plan into a complete, distributable survey questionnaire, where every question serves a clear analytical purpose and is free of common measurement biases.

### Core Capability

Given the research plan — its objectives, participant criteria, and hypotheses — this skill produces screening questions, objective-mapped core questions with appropriate question types and response scales, demographic questions, open-ended questions, survey flow and skip logic, and an estimated completion time.

### Method

1. **Objective mapping:** Read the research plan and derive 3-5 questions per objective, each with a stated purpose and analysis plan.
2. **Bias mitigation:** Apply survey methodology rules — one concept per question, no leading language, no assumed knowledge, balanced Likert scales, exhaustive and mutually exclusive options.
3. **Flow and length:** Order questions general to specific, add skip logic where useful, and keep total completion time within the stated maximum.

### Output Structure

A complete questionnaire document with section headings, numbered questions, response options, and skip-logic notation. It derives from the research plan and stands alongside the interview guide as a research instrument.
