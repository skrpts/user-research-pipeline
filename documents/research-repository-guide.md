---
type: document
id: research-repository-guide
title: Research Repository Guide
description: "How to maintain a research repository for ongoing reference, avoiding repeated studies and building institutional knowledge"
tags: [Production, Customer-Facing, design:research, analysis:audience]
connections:
  - target: user-research-methods
    type: references
metadata:
  document_type: "guide"
  audience: "product-teams"
---

## Research Repository Guide

A research repository is where your organisation's user research lives after the study is complete. Without one, teams repeat studies, lose insights, and fail to build on previous findings. This guide explains how to set up and maintain a useful research repository.

### Why a Research Repository Matters

**The problem it solves:**
- Different teams commission identical research because they do not know a study already exists
- Insights from six months ago are forgotten because they live in someone's Google Drive
- New team members have no way to access historical research
- Stakeholders ask "do we have any research on X?" and nobody can answer quickly

**What a good repository enables:**
- Any team member can search for existing research on a topic in under 2 minutes
- New research builds on previous findings rather than starting from scratch
- Patterns emerge across studies that individual studies cannot reveal
- Research investment compounds over time

### Repository Structure

Organise entries by study, with each study containing:

**1. Study Metadata**
- Study title (descriptive, searchable)
- Date conducted
- Researcher(s)
- Methodology (interviews, survey, usability test, etc.)
- Participant count and profile
- Product area or feature studied

**2. Research Objectives**
- The original questions the study set out to answer

**3. Key Insights**
- 5-8 insights per study, each with:
  - Insight statement
  - Confidence level (High/Medium/Low)
  - Supporting evidence summary (not the full analysis)
  - Recommended action (and whether it was taken)

**4. Tags**
- Product area (onboarding, billing, dashboard, etc.)
- User segment (new users, power users, enterprise, SMB)
- Theme (usability, satisfaction, workflow, pricing)
- Method (interview, survey, usability test)

**5. Links**
- Full research report
- Presentation deck (if one was created)
- Raw data location (access-controlled)

### Entry Template

When adding a study to the repository, use this structure:

```
Study: [Title]
Date: [YYYY-MM-DD]
Researcher: [Name]
Method: [Interview / Survey / Usability Test / Mixed]
Participants: [Number] [profile description]
Product area: [Area]

Objectives:
1. [Objective]
2. [Objective]

Key Insights:
1. [Insight statement] — Confidence: [H/M/L] — Status: [Actioned / Pending / Deprioritised]
2. [Insight statement] — Confidence: [H/M/L] — Status: [Actioned / Pending / Deprioritised]

Tags: [tag1], [tag2], [tag3]

Full report: [link]
```

### Maintenance Practices

**After every study:**
- Add the study to the repository within one week of completing the report
- Tag it thoroughly — future searchability depends on good tagging
- Link it to related previous studies

**Monthly:**
- Review the "Pending" insight backlog — are there insights that have been pending for more than 3 months? Either action them or explicitly deprioritise them
- Check for studies in progress that have not yet been added

**Quarterly:**
- Review repository coverage — which product areas have strong research coverage and which are under-researched?
- Identify cross-study patterns — do the same themes keep emerging across multiple studies?
- Present a "State of Research" summary to product leadership

**Annually:**
- Archive studies older than 2 years (findings may no longer reflect current users)
- Review and update tags to match current product vocabulary
- Assess whether the repository is being used — if not, investigate why

### Searchability Best Practices

The repository is only as useful as its searchability. Ensure:
- Study titles are descriptive ("Onboarding drop-off analysis for SMB users" not "Research Q3")
- Tags follow a controlled vocabulary (agree on tag names and use them consistently)
- Insights are written as complete sentences (searchable and understandable out of context)
- Each entry includes the product area and user segment prominently

### Common Pitfalls

1. **Over-engineering the system.** A spreadsheet with consistent formatting is better than an elaborate tool that nobody uses. Start simple.
2. **Under-tagging.** If entries have only 1-2 tags, they will not surface in searches. Aim for 4-6 tags per entry.
3. **Insight rot.** Insights from 2 years ago may not reflect current reality. Flag dated insights and recommend refreshes.
4. **Access restrictions.** If only the research team can access the repository, the rest of the organisation will not use it. Make it widely readable with raw data access restricted.
5. **No feedback loop.** If insights are added but never actioned, the repository becomes a graveyard. Track insight status and hold teams accountable for acting on findings.
