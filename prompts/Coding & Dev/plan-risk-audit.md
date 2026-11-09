---
title: Plan Risk Audit
category: Coding & Dev
subcategory: Review
tags: [risk, audit, plan, claude-code, security, claude]
model: claude
difficulty: intermediate
author: "@sunaiuse"
source_url: https://x.com/sunaiuse/status/2069906980278317454
added: 2026-11-09
---

# Plan Risk Audit

## Prompt
```
Review the plan you just created. Identify every item that introduces product risk. List them from most risky to least risky. Then create a plan to de-risk each one.
```

## How to use
Run this right after Claude delivers a plan (and after the Plan-Guard step, ideally). It surfaces hidden risks — a DB migration that breaks users, an auth flow that opens a security gap, a feature that conflicts with existing work — and produces a de-risking plan for each.

## Notes / Tips
Part 2 of `@sunaiuse`'s three-prompt sequence. A plan can sound reasonable on the surface and quietly carry critical risk underneath; this forces the risks out and ranked. Pair with Plan-Guard, then finish with Senior Code Review.

## Source
@sunaiuse · https://x.com/sunaiuse/status/2069906980278317454 · added 2026-11-09
