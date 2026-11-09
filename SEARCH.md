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
