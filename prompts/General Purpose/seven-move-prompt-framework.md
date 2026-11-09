---
title: The 7-Move Prompt Framework
category: General Purpose
subcategory: Meta / Framework
tags: [claude, prompting, meta, framework, self-check, planning, craft, reusable]
model: any
difficulty: intermediate
author: "@Gustafssonkotte"
source_url: https://x.com/Gustafssonkotte/status/2074010747361779715
added: 2026-11-09
---

# The 7-Move Prompt Framework

A reusable "prompt within a prompt." Paste it ahead of *any* task to make a
model behave like a careful coworker instead of a generic answer-machine. It is
built from the 7 high-signal prompting moves @Gustafssonkotte distilled from
Anthropic's own prompting guidance (see source). The 7 moves are quoted verbatim
from the post; the prompt below operationalizes them into a fill-in-the-blanks
template you can reuse for coding, writing, analysis, planning, or research.

## Prompt
```
You are working with me on the task below. Apply these 7 moves every time:

1. OUTCOME, NOT STEPS — I describe the result I want; you figure out the steps.
   If my stated outcome is unclear or unachievable, tell me and propose a better
   target before working.
2. SELF-CHECK — Before you finish, verify your own work: state your assumptions,
   check your reasoning, and flag anything you're unsure about or can't verify.
3. EXAMPLES OVER ADJECTIVES — Instead of vague taste ("make it better",
   "more professional"), match the concrete example/reference I give you.
4. AUDIENCE + SHAPE — Answer for the audience I name, in the format/length/shape
   I ask for. If I didn't, ask me or state the assumption you're making.
5. RAW MATERIAL, NOT MY SUMMARY — I hand over the source material. Work from it
   directly; don't rely on a paraphrase. If the material is missing or thin, say so.
6. PLAN BEFORE ACTING — First produce a short plan or outline and get my ok (or
   state it clearly) before producing the full result.
7. LEARN FROM REPEATED CORRECTIONS — If I correct the same thing more than once,
   name the rule explicitly and hold it for the rest of the conversation.

Here are the details:
- Outcome I want: [RESULT]
- Audience & shape/format/length: [WHO + WHAT IT LOOKS LIKE]
- Raw material / reference / example: [PASTE MATERIAL OR LINK]
- Constraints or must-avoid: [ANY RULES]

Start by listing your assumptions and a 1-line plan, then proceed.
```

## How to use
Fill the four bracketed fields, then paste before any real task. It works
across models and domains — coding, writing, analysis, planning, research —
because the moves are about *how you ask*, not a subject-specific trick.
Move #6 (plan first) is the single biggest quality lever; move #2 (self-check)
is the one most people skip.

## Notes / Tips
- Distilled from @Gustafssonkotte's "You Are Using Claude Wrong. 7 Prompts Fix
  It" post. The 7 moves are quoted verbatim from the post body; the templated
  prompt is this curator's operationalization of those moves, since the author's
  exact copy-paste versions live in a login-walled pinned article.
- The craft here is the pairing of each move with a *failure mode it prevents*:
  outcome-not-steps → no barking up the wrong tree; self-check → no unverified
  claims; examples-over-adjectives → no vague output; audience+shape → no
  mismatched tone; raw-material → no drift from a summary; plan-first → no
  wasted full-draft work; repeated-correction → no re-teaching the same thing.
- Combine with the repo's `Plan-Guard (96% Confidence)` prompt when the task is
  a coding plan: use that one to gate confidence *before* the plan, and move #6
  here to structure the plan itself.

## Source
@Gustafssonkotte · https://x.com/Gustafssonkotte/status/2074010747361779715 · added 2026-11-09
