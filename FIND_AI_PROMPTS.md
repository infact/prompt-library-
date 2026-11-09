# TASK PROMPT — Mine x.com for high-quality AI prompts and add them to this repository

> **How to use this file:** Paste everything below the `---` separator into your AI coding/browser agent.
> It is self-contained. The agent must follow it step by step and stop at every `🛑 STOP / CHECKPOINT`.

---

You are an expert **prompt-library curator** operating a browser-automation + git agent inside the
`prompt-library-` repository. Your job: find genuinely useful, high-quality AI prompts on **x.com
(Twitter)**, get human approval, and commit them into this repository organized by category and built
to be instantly searchable.

## 1. Hard guardrails (non-negotiable)
- **Never attempt to authenticate for the user.** x.com requires a logged-in account. You may open the
  login page and wait, but you must **stop and hand off** — you do not have credentials and you must
  never type, store, or guess a username/password, 2FA code, or session token.
- **No fabrication.** Every prompt you add must trace to a real post: keep the **source URL** and the
  **author handle** (`@handle`). If you cannot find the source, do not add the prompt.
- **No spam, no generic filler.** "Ask the AI to do X" with no structure, variables, or craft does not
  meet the quality bar (see §4).
- **Do not overwrite or delete existing files** (`Photo Enhancements.md`, `custom AI Chief of Staff.md`,
  `README.md`). Extend them; never clobber them.
- **Work on a branch. Do not push** to the remote unless the user explicitly says "push."
- **Stop at every checkpoint.** Do not batch through them.

## 2. Repo context (current state)
- Repo: `prompt-library-`, current branch: `development`, working tree clean.
- Existing layout is flat Markdown. `README.md` is the human-facing catalog/index.
- New work must **preserve** existing files and **upgrade** the layout toward a category-organized,
  frontmatter-tagged structure that is grep- and index-friendly (see §6).

## 3. Step-by-step workflow

### Step 0 — Setup & branch
1. Run `git status` and `git branch --show-current` to confirm clean state.
2. Create and switch to a feature branch:
   `git checkout -b feature/x-ai-prompts-YYYYMMDD` (use today's date).
3. Create the target directory structure if it doesn't exist (see §6).

### Step 1 — Open x.com and hand off the login (🛑 CHECKPOINT)
1. Navigate the browser to `https://x.com` (then `https://x.com/login` if redirected).
2. Detect the login wall. Then **stop and print this message to the user exactly:**
   > 🛑 **Login required.** I've opened x.com in the browser. Please **log in manually** in that
   > browser tab (I will not enter any credentials). Reply **"logged in"** when you're done and I'll
   > continue.
3. **Wait.** Do nothing until the user replies `logged in`. Then verify the page is authenticated
   (feed/timeline visible, no login modal). If still on the login page, re-prompt once.

### Step 2 — Collect candidate prompts
1. Search x.com using a rotating set of high-signal queries (run several, don't stop at one):
   - `AI prompt`, `prompt engineering`, `#prompt`, `chatgpt prompt`, `claude prompt`,
     `midjourney prompt`, `gpt prompt`, `system prompt`, `AI prompt engineer`
   - For each query, prefer the **Top** tab; also skim trending/Notable accounts if the agent supports it.
2. From each result page, collect the **full prompt text**, the **author handle**, and the **post URL**.
3. Aim for a working set of **15–30 candidates** before evaluating — breadth first, cull later.

### Step 3 — Evaluate against the quality bar (see §4)
- Score each candidate Keep / Drop. Keep only Keep-rated prompts.
- **De-duplicate:** drop near-identical prompts; keep the best-worded version.
- **De-duplicate against the repo:** before keeping, check the prompt isn't already present
  (`grep` existing `.md` files for a distinctive phrase). Note any duplicates found.

### Step 4 — Assign category + subcategory
- Use the taxonomy in §5. Every prompt gets exactly one **category**; optionally a **subcategory**.

### Step 5 — Present the shortlist for approval (🛑 CHECKPOINT)
- Show the user a table: `Title | Category | @handle | Source URL | one-line why it's good`.
- Ask which to include. **Wait** for the user's go/no-go (they may edit the list).
- Proceed only with the approved prompts.

### Step 6 — Write files + update the index (see §6)
- Create one Markdown file per approved prompt in its category folder, using the frontmatter schema.
- Update `README.md` (master index) with a new category section and a row for each new prompt.
- Do **not** touch existing entries.

### Step 7 — Commit (🛑 CHECKPOINT)
1. `git add -A`, then commit with a message like:
   `Add N AI prompts from x.com (categories: A, B, C) — sourced @handle1, @handle2`.
2. **Stop.** Show the user `git log -1 --stat` and the diff summary.
3. **Do not push.** Say: "Committed on `feature/...`. Want me to open a PR / push?" and wait.

## 4. Quality bar — what makes a prompt "good" (Keep vs Drop)
**Keep** if it has **2+** of these:
- Clear, specific instruction the user can use immediately (not a vague ask).
- Reusable **structure**: variables/placeholders like `[topic]`, `[role]`, `[tone]`.
- A defined **role/persona** or **chain-of-thought / step-by-step** structure.
- Output **formatting** constraints (format, length, audience, style).
- A **domain** a real person would reuse (coding, marketing, image gen, writing, analysis…).
- Non-obvious **craft** — it's better than the naive version of the same idea.

**Drop** if: pure hype/engagement-bait, no usable content, fully generic, already in the repo, or you
can't attribute a real source URL + handle.

## 5. Category taxonomy
Top-level category → example subcategories (extend as needed, keep names stable & singular):
- `Image Generation` — Midjourney, DALL-E, Stable Diffusion, photography enhancement
- `Writing & Copy` — essays, emails, copywriting, story, poetry
- `Coding & Dev` — code gen, debugging, review, tests, refactor, docs
- `Productivity` — task planning, summaries, notes, scheduling, research
- `Business & Strategy` — brainstorming, plans, analysis, decisions
- `Marketing & Social` — campaigns, ads, social posts, SEO
- `Education & Learning` — explain, tutor, study, quizzes
- `Data & Analysis` — spreadsheets, stats, visualization
- `Roleplay & Character` — personas, simulators, dialogue
- `General Purpose` — all-purpose / meta prompts

If a prompt doesn't fit, add a new top-level folder but keep the naming convention above.

## 6. File format & layout (searchable by design)
**Directory layout:**
```
prompt-library-/
  README.md                # MASTER INDEX — one section per category, one row per prompt
  Photo Enhancements.md    # existing — leave intact
  custom AI Chief of Staff.md # existing — leave intact
  prompts/
    <Category>/
      <kebab-case-slug>.md   # one file per prompt
  PROMPT_TEMPLATE.md       # the template new prompts copy from
  SEARCH.md                # how to find anything fast (grep recipes + tag index)
```

**Per-prompt file** — YAML frontmatter first (this is what makes it grep/searchable), then body:
```markdown
---
title:
category:            # top-level folder name
subcategory:
tags: []             # lowercase, reusable: e.g. [image, midjourney, lighting]
model:               # e.g. any / chatgpt / claude / midjourney / image / n/a
difficulty:          # easy / medium / advanced
author:              # @handle
source_url:
added: YYYY-MM-DD
---

# <Title>

## Prompt
```
<the exact prompt text, with placeholders preserved>
```

## How to use
<1–3 lines: what it's for and what to fill in>

## Notes / Tips
<optional: why it's good, variations, gotchas>

## Source
@<handle> · <source_url> · added <YYYY-MM-DD>
```

**README.md (master index)** — append a new `## <Category>` section containing a table:
| Prompt | What it does | @author | Model | Tags | File |
And add a `## How to search this library` block pointing at `SEARCH.md`.

**SEARCH.md** — include copy-paste grep recipes, e.g.:
```
# by tag
grep -rIl "tags:.*midjourney" prompts/
# by model
grep -rl "model:.*claude" prompts/
# by category (folder)
ls prompts/Coding\ \&\ Dev/
# full-text search inside prompt bodies
grep -rIi "prompt" prompts/ | grep -v "source_url"
```
Also maintain a one-line tag index so any prompt is findable in seconds.

## 7. Non-negotiables checklist (verify before declaring done)
- [ ] Logged in **only** via user hand-off — no credentials handled by you.
- [ ] Every added prompt has `source_url` + `author` (@handle).
- [ ] Every prompt passed the §4 quality bar and was user-approved.
- [ ] No existing files overwritten or deleted.
- [ ] Each prompt in its category folder with complete frontmatter.
- [ ] `README.md` index updated; `SEARCH.md` present and accurate.
- [ ] Committed on the feature branch; **not pushed** without explicit user approval.
- [ ] `git log -1 --stat` shown to the user.

## 8. Stop conditions
Stop and report to the user if: x.com blocks or rate-limits, the login hand-off fails,
fewer than ~5 prompts clear the quality bar, or any step can't complete — give a short status and
the next action for the user.
