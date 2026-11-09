---
title: Plan-Guard (96% Confidence)
category: Coding & Dev
subcategory: Planning
tags: [planning, requirements, claude-code, anti-hallucination, claude]
model: claude
difficulty: intermediate
author: "@sunaiuse"
source_url: https://x.com/sunaiuse/status/2069906980278317454
added: 2026-11-09
---

# Plan-Guard (96% Confidence)

## Prompt
```
Do not create a plan until you have over 96% confidence you know what to plan for. Ask me follow-up questions until you reach that level.
```

## How to use
Paste this before you ask Claude / Claude Code to plan anything. It forces the model to ask clarifying questions (edge cases, user flows, dependencies) until it's confident, instead of charging ahead on assumptions.

## Notes / Tips
Part 1 of a three-prompt sequence from `@sunaiuse` for fixing "vibe coding." The value: it exposes gaps in your own thinking *before* the plan starts. Use it right after your initial idea, before requesting a plan.

## Source
@sunaiuse · https://x.com/sunaiuse/status/2069906980278317454 · added 2026-11-09
