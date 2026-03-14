---
type: service
id: llm-service
title: LLM Service
description: "Language model service providing research planning, analysis, and synthesis capabilities"
tags: [Production]
connections: []
metadata:
  serviceType: llm
  auth_type: api_key
---

## Service Description

Provides access to a large language model for research planning, instrument design, data analysis, and insight synthesis. Used by all skills in this skrpt.

## Configuration

The LLM provider is configured in the skrptiq app settings. This skrpt works with any supported provider — no specific vendor is required.

## Usage Notes

- All requests include a system prompt tailored to the specific skill being invoked
- Transcript analysis is the most token-intensive stage and may benefit from a model with a large context window
- The service does not retain any data from requests — all analysis is stateless
- Users should ensure their provider's usage terms permit processing of the data types in their study
