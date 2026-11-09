---
title: Senior Code Review
category: Coding & Dev
subcategory: Review
tags: [code-review, debugging, quality, claude-code, claude]
model: claude
difficulty: intermediate
author: "@sunaiuse"
source_url: https://x.com/sunaiuse/status/2069906980278317454
added: 2026-11-09
---

# Senior Code Review

## Prompt
```
Act as a senior engineer. Code review everything you just wrote. Look for inconsistent logic, inefficiencies, and anything that can cause bugs. List everything from most critical to least critical. Then create a plan to fix it.
```

## How to use
Run this after implementation, right before you commit. Claude reviews its own output for logic inconsistencies, inefficiencies, and latent bugs, ranked critical→least critical, plus a fix plan.

## Notes / Tips
Part 3 of `@sunaiuse`'s sequence and the highest-leverage of the three — it catches issues that would surface as production bugs later. The "list from most critical to least critical" ranking keeps the output actionable.

## Source
@sunaiuse · https://x.com/sunaiuse/status/2069906980278317454 · added 2026-11-09
