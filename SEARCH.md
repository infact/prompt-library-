# SEARCH.md — find any prompt in seconds

Every prompt lives at `prompts/<Category>/<kebab-case-slug>.md` with YAML frontmatter
(`title`, `category`, `subcategory`, `tags`, `model`, `difficulty`, `author`, `source_url`, `added`).
That structure makes the whole library grep-able. All recipes below run from the repo root.

## 1. Browse by category
```bash
ls "prompts/Image Generation/"
ls prompts/Coding\ \&\ Dev/        # & must be escaped in zsh
find prompts -maxdepth 1 -type d
```

## 2. Search by tag
```bash
# prompts whose tags include "midjourney"
grep -rIl "tags:.*midjourney" prompts/

# several tags at once (OR)
grep -rIl -e "tags:.*lighting" -e "tags:.*cinematic" prompts/
```

## 3. Search by model / difficulty
```bash
grep -rl "model:.*claude"     prompts/
grep -rl "model:.*midjourney" prompts/
grep -rl "difficulty:.*advanced" prompts/
```

## 4. Full-text search inside prompt bodies
```bash
# case-insensitive, ignore binary, show filename + match
grep -rIi "prompt" prompts/

# search only the Prompt section bodies (skip frontmatter/source lines)
grep -rIi --exclude-dir=.git "chain-of-thought" prompts/ | grep -v "source_url"
```

## 5. Find a prompt by a distinctive phrase
```bash
grep -rIl "soft directional key light" prompts/
```

## 6. What's new / who contributed
```bash
# newest prompts by added date
ls -1t prompts/**/*/*.md 2>/dev/null || find prompts -name '*.md' -newer PROMPT_TEMPLATE.md

# everything a given author contributed
grep -rl "@handle" prompts/
```

## 7. Index of categories
| Category | Folder | What's in it |
| --- | --- | --- |
| Image Generation | `prompts/Image Generation/` | Midjourney, DALL-E, Stable Diffusion, photography |
| Writing & Copy | `prompts/Writing & Copy/` | essays, emails, copy, story, poetry |
| Coding & Dev | `prompts/Coding & Dev/` | code gen, debugging, review, tests, refactor |
| Productivity | `prompts/Productivity/` | planning, summaries, notes, research |
| Business & Strategy | `prompts/Business & Strategy/` | brainstorming, plans, analysis, decisions |
| Marketing & Social | `prompts/Marketing & Social/` | campaigns, ads, social posts, SEO |
| Education & Learning | `prompts/Education & Learning/` | explain, tutor, study, quizzes |
| Data & Analysis | `prompts/Data & Analysis/` | spreadsheets, stats, visualization |
| Roleplay & Character | `prompts/Roleplay & Character/` | personas, simulators, dialogue |
| General Purpose | `prompts/General Purpose/` | all-purpose / meta prompts |

## Adding a new prompt
1. Copy `PROMPT_TEMPLATE.md` to `prompts/<Category>/<kebab-case-slug>.md`.
2. Fill in every frontmatter field (esp. `tags`, `model`, `author`, `source_url`).
3. Add a row for it under its category section in `README.md`.
4. `git add -A && git commit`.

---

## 8. Recently added from x.com (2026-11-09)
23 prompts sourced from x.com (x.com / X). Two authors: `@AnatoliKopadze`
(20 general-purpose / productivity / writing / education / roleplay / marketing /
business / data prompts, one post) and `@sunaiuse` (3 coding prompts from a
"3 prompts that fix 90% of vibe coding mistakes" post). Find a whole author's
contributions:

```bash
grep -rl "@AnatoliKopadze" prompts/
grep -rl "@sunaiuse" prompts/
```

### 8a. Tag index (x.com batch, 2026-11-09)
| Tag | Recipes |
| --- | --- |
| `writing` | `grep -rl "tags:.*writing" prompts/` |
| `learning` | `grep -rl "tags:.*learning" prompts/` |
| `strategy` | `grep -rl "tags:.*strategy" prompts/` |
| `roleplay` | `grep -rl "tags:.*roleplay" prompts/` |
| `career` | `grep -rl "tags:.*career" prompts/` |
| `claude-code` | `grep -rl "tags:.*claude-code" prompts/` |
| `planning` | `grep -rl "tags:.*planning" prompts/` |

### 8b. Quick "what's in each folder" after this batch
| Folder | New prompts this batch |
| --- | --- |
| `prompts/Writing & Copy/` | Style Mimic, The Brutal Editor, One Text Five Audiences, Bullets to Article |
| `prompts/Coding & Dev/` | Plan-Guard (96% Confidence), Plan Risk Audit, Senior Code Review |
| `prompts/Productivity/` | Weekly Meal Plan with Shopping List, Travel Planner |
| `prompts/Business & Strategy/` | Devil's Advocate Mode, Steelman Any Position, Resume Multiplier |
| `prompts/Marketing & Social/` | LinkedIn Bio Rewrite |
| `prompts/Education & Learning/` | Mental Model Builder, Feynman Tutor, 30-Day Curriculum Builder, Socratic Mode |
| `prompts/Data & Analysis/` | Multi-Source Synthesis, Personal Finance Analyzer |
| `prompts/Roleplay & Character/` | Salary Negotiation Roleplay, Interview Simulator, Difficult Conversation Prep |
| `prompts/General Purpose/` | Legal Document Translator |

`prompts/Image Generation/` still has no prompts — no genuinely reusable image
generation prompt was found on x.com this pass; nothing was fabricated to fill it.

---

## 9. Recently added from x.com (2026-11-09, pass 2)
1 prompt, sourced `@Gustafssonkotte`. The rest of the "prompt" space on x.com
this pass was engagement-bait / commercial (X-flagged), so nothing else cleared
the quality bar — nothing was fabricated.

```bash
grep -rl "@Gustafssonkotte" prompts/
```

### 9a. New tags
| Tag | Recipe |
| --- | --- |
| `meta` | `grep -rl "tags:.*meta" prompts/` |
| `framework` | `grep -rl "tags:.*framework" prompts/` |
| `self-check` | `grep -rl "tags:.*self-check" prompts/` |
| `claude` | `grep -rl "tags:.*claude" prompts/` |
