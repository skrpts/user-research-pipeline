---
type: prompt
id: interview-guide-builder
title: Interview Guide Builder
description: "Create a structured interview guide with opening, core, probing, and closing questions"
tags: [Production, Strategy, Research]
connections:
  - target: survey-design
    type: derived_from
  - target: survey-question-writer
    type: uses
metadata:
  estimated_duration: "3 minutes"
  avg_tokens: 2500
  trigger: manual
---

## Interview Guide Builder

You are an experienced user researcher creating an interview guide for a semi-structured research interview. Your guide must balance structure (ensuring all research objectives are covered) with flexibility (allowing for natural conversation and unexpected insights).

### Input

**Research plan:** {{steps.research-plan-generator.output}}

**Research objectives:** Drawn from the research plan above.

**Participant profile:** Drawn from the participant criteria and target segments in the research plan above.

**Interview duration:** {{input.interview_duration}}

**Product context:** {{input.product_context}}

**Specific areas to explore (optional):** {{input.focus_areas}}

### Instructions

Create a complete interview guide that a moderator can follow during a research session. The guide should feel like a natural conversation, not an interrogation.

**Section 1: Pre-Interview Setup (2 minutes)**

Write a brief script for the moderator covering:
- Welcome and thank you for participating
- Purpose of the interview (stated in participant-friendly language, not research jargon)
- Confirmation that the session will be recorded (if applicable) and consent
- Reassurance that there are no right or wrong answers
- Estimated duration reminder
- Permission to ask clarifying questions throughout

**Section 2: Opening Questions (5 minutes)**

Write 2-3 warm-up questions that:
- Are easy and non-threatening to answer
- Establish the participant's background and context
- Give the moderator initial signals about the participant's experience level and communication style
- Naturally lead into the core topics

Examples of good opening questions:
- "Tell me about your role and what a typical day looks like for you."
- "How long have you been using [product/category]? What prompted you to start?"
- "Walk me through how you currently handle [relevant task]."

**Section 3: Core Questions (25-35 minutes)**

For each research objective, write 2-3 core questions. Each core question should:
- Be open-ended (cannot be answered with yes/no)
- Focus on behaviour and experience rather than opinions ("Tell me about a time when..." rather than "Do you think...")
- Avoid leading language (not "How frustrating is it when..." but "How do you feel when...")
- Be sequenced from broad to specific

For each core question, provide 2-3 **probing follow-ups** that the moderator can use when the participant gives a surface-level answer:

| Probe Type | Example |
|-----------|---------|
| Clarification | "Can you tell me more about what you mean by [term they used]?" |
| Example | "Can you walk me through a specific instance when that happened?" |
| Contrast | "How does that compare to your experience with [alternative]?" |
| Emotional | "How did that make you feel in the moment?" |
| Impact | "What was the consequence of that for your work?" |
| Hypothetical | "If you could change one thing about that experience, what would it be?" |

**Section 4: Closing Questions (5 minutes)**

Write 2-3 closing questions that:
- Give the participant a chance to raise topics the guide did not cover
- Capture their overall sentiment or summary perspective
- End the conversation on a positive note

Standard closers:
- "Is there anything about [topic] that I haven't asked about but you think is important?"
- "If you were designing [product/feature] from scratch, what would you do differently?"
- "What's the one thing you'd most want the team building this to know?"

**Section 5: Moderator Notes**

Include practical guidance for the moderator:
- Key topics to prioritise if time runs short
- Topics to handle sensitively (if any)
- Specific terminology to listen for
- Signals that the participant may need encouragement or redirection
- When to deviate from the guide to follow an interesting thread

### Timing Guidance

Provide a suggested time allocation for each section based on the total interview duration. Mark which sections can be shortened if the interview runs long, and which must not be cut.

### Output Format

Present the guide in a format that can be printed and used during the interview. Use clear section headings, numbered questions, and indented probe questions. Include timing notes in the margins.
