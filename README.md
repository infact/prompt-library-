# prompt-library-

> A searchable, category-organized library of high-quality AI prompts.
> **New here?** → see `SEARCH.md` to find any prompt fast, and `FIND_AI_PROMPTS.md` for how prompts are added.

## How to find a prompt
- **By category:** open `prompts/` (one folder per category, see `prompts/README.md`).
- **By tag / model / difficulty / full-text:** copy a grep recipe from `SEARCH.md`.
- **Add your own:** copy `PROMPT_TEMPLATE.md` into the right `prompts/<Category>/` folder,
  fill the YAML frontmatter, and add a row under its category below.

## Categories (index)
| Category | Folder |
| --- | --- |
| Image Generation | `prompts/Image Generation/` |
| Writing & Copy | `prompts/Writing & Copy/` |
| Coding & Dev | `prompts/Coding & Dev/` |
| Productivity | `prompts/Productivity/` |
| Business & Strategy | `prompts/Business & Strategy/` |
| Marketing & Social | `prompts/Marketing & Social/` |
| Education & Learning | `prompts/Education & Learning/` |
| Data & Analysis | `prompts/Data & Analysis/` |
| Roleplay & Character | `prompts/Roleplay & Character/` |
| General Purpose | `prompts/General Purpose/` |

## Image Generation
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| _none yet — add rows here as prompts are collected_ | | | | | |

## Writing & Copy
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| Style Mimic | Rewrite any text to match a target author's voice and style | @AnatoliKopadze | claude | writing, style, voice, ghostwriting | `prompts/Writing & Copy/style-mimic.md` |
| The Brutal Editor | Ruthlessly cut and tighten a draft | @AnatoliKopadze | claude | writing, editing, critique, review | `prompts/Writing & Copy/brutal-editor.md` |
| One Text, Five Audiences | Adapt one message to five different audiences | @AnatoliKopadze | claude | writing, audience, adaptation, copywriting | `prompts/Writing & Copy/one-text-five-audiences.md` |
| Bullets to Article | Expand bullet notes into a structured article | @AnatoliKopadze | claude | writing, drafting, notes, structure | `prompts/Writing & Copy/bullets-to-article.md` |

## Coding & Dev
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| Plan-Guard (96% Confidence) | Force the model to clarify until it's >96% confident before planning | @sunaiuse | claude | planning, requirements, claude-code, anti-hallucination | `prompts/Coding & Dev/plan-guard-96-confidence.md` |
| Plan Risk Audit | Surface and de-risk every risk in a generated plan | @sunaiuse | claude | risk, audit, plan, claude-code, security | `prompts/Coding & Dev/plan-risk-audit.md` |
| Senior Code Review | Self-review freshly written code, ranked, with a fix plan | @sunaiuse | claude | code-review, debugging, quality, claude-code | `prompts/Coding & Dev/senior-code-review.md` |

## Productivity
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| Weekly Meal Plan with Shopping List | Build a 7-day meal plan with a sectioned shopping list | @AnatoliKopadze | claude | meal-plan, nutrition, planning, shopping-list | `prompts/Productivity/weekly-meal-plan.md` |
| Travel Planner | Build a personalized day-by-day trip itinerary | @AnatoliKopadze | claude | travel, itinerary, planning | `prompts/Productivity/travel-planner.md` |

## Business & Strategy
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| Devil's Advocate Mode | Red-team a plan or idea by making the strongest case against it | @AnatoliKopadze | claude | strategy, critique, red-team, risk, decision | `prompts/Business & Strategy/devils-advocate-mode.md` |
| Steelman Any Position | Build the strongest version of any opposing view before critiquing it | @AnatoliKopadze | claude | strategy, steelman, debate, critical-thinking | `prompts/Business & Strategy/steelman-any-position.md` |
| Resume Multiplier | Tailor one resume to many job descriptions | @AnatoliKopadze | claude | career, resume, job-search, tailoring | `prompts/Business & Strategy/resume-multiplier.md` |

## Marketing & Social
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| LinkedIn Bio Rewrite | Rewrite your LinkedIn headline + summary in 5 styles | @AnatoliKopadze | claude | linkedin, personal-brand, copywriting, bio | `prompts/Marketing & Social/linkedin-bio-rewrite.md` |

## Education & Learning
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| Mental Model Builder | Turn a concept into a reusable mental model | @AnatoliKopadze | claude | learning, mental-models, teaching, understanding | `prompts/Education & Learning/mental-model-builder.md` |
| Feynman Tutor | Teach a topic via the Feynman technique and expose the gaps | @AnatoliKopadze | claude | learning, feynman, teaching, comprehension | `prompts/Education & Learning/feynman-tutor.md` |
| 30-Day Curriculum Builder | Generate a 30-day learning plan for any skill | @AnatoliKopadze | claude | learning, curriculum, skill, planning | `prompts/Education & Learning/30-day-curriculum-builder.md` |
| Socratic Mode | Learn a topic through Socratic questioning instead of direct answers | @AnatoliKopadze | claude | learning, socratic, teaching, dialogue | `prompts/Education & Learning/socratic-mode.md` |

## Data & Analysis
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| Multi-Source Synthesis | Read multiple documents/transcripts and synthesize one shared brief, flagging contradictions | @AnatoliKopadze | claude | research, synthesis, analysis, sources, brief | `prompts/Data & Analysis/multi-source-synthesis.md` |
| Personal Finance Analyzer | Parse spending/transactions and surface budgeting insights, trends, and recommendations | @AnatoliKopadze | claude | finance, budgeting, analysis, expenses | `prompts/Data & Analysis/personal-finance-analyzer.md` |

## Roleplay & Character
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| Salary Negotiation Roleplay | Practice negotiating your salary against a firm roleplay hiring manager | @AnatoliKopadze | claude | roleplay, negotiation, career, simulation | `prompts/Roleplay & Character/salary-negotiation-roleplay.md` |
| Interview Simulator | Run a realistic one-question-at-a-time interview with per-answer grading | @AnatoliKopadze | claude | roleplay, interview, career, simulation | `prompts/Roleplay & Character/interview-simulator.md` |
| Difficult Conversation Prep | Build a playbook for a tough conversation | @AnatoliKopadze | claude | roleplay, communication, planning, conversation | `prompts/Roleplay & Character/difficult-conversation-prep.md` |

## General Purpose
| Prompt | What it does | @author | Model | Tags | File |
| --- | --- | --- | --- | --- | --- |
| Legal Document Translator | Plain-English breakdown of a legal document before you sign it | @AnatoliKopadze | claude | legal, contract, document, understanding | `prompts/General Purpose/legal-document-translator.md` |

---

## Legacy photo-enhancement prompts
_The following prompts predate the folder structure. They are kept verbatim.
New prompts should be added under `prompts/` with frontmatter instead._

1. MAKE IT LOOK LIKE A PROFESSIONAL PHOTOGRAPH
Create a photorealistic image of [subject] as if captured by a professional photographer using a full-frame DSLR.
Use realistic lighting, accurate proportions, natural textures, fine details, authentic shadows, and balanced exposure. Preserve realistic imperfections and avoid artificial skin smoothing, exaggerated sharpness, or the typical AI-generated appearance."

2. MASTER THE LIGHTING AND SHADOWS
Generate [subject] with professional lighting using a soft directional key light, subtle fill light, and natural rim lighting.
Create realistic shadow gradients, accurate light reflections, balanced highlights, and natural depth. Ensure the lighting interacts realistically with the subject and surrounding environment without artificial glow."


3. APPLY A CINEMATIC COLOR GRADE
"Give [subject] a professional cinematic color grade with balanced contrast, rich but natural colors, controlled highlights, and detailed shadows. Preserve accurate skin tones and realistic color
relationships. Use subtle film-inspired tonality without excessive saturation, unnatural color shifts, crushed blacks, or artificial orange-and-teal effects."


4. CREATE A PROFESSIONAL
COMPOSITION
Compose [subject] using professional photography principles. Apply the rule of thirds, intentional framing, balanced negative space, and clear visual hierarchy.
Establish a strong focal point, natural perspective, and realistic depth of field.
Remove distracting background elements while preserving the subject's original proportions and visual identity."

5. CREATE SOFT PROFESSIONAL
STUDIO LIGHTING
iPhotograph [subject] in a professional studio using a large diffused softbox as the key light, gentle fill lighting, and subtle background separation. Produce smooth shadow transitions, realistic skin texture, accurate reflections, and controlled highlights. Maintain natural proportions and avoid flat lighting, harsh shadows, or artificial retouching."


6. CAPTURE REALISTIC
CAMERA DEPTH
"Create [subject] with the optical characteristics of a professional 85mm portrait lens at f/2.8. Keep the main subject sharply focused while producing natural background separation, realistic bokeh, accurate perspective, and gradual depth transitions. Avoid excessive background blur, distorted proportions, or artificially sharpened edges."


7. PRESERVE NATURAL TEXTURES
AND DETAILS
Render [subject] with highly detailed, physically realistic textures. Preserve fine surface details, natural skin pores, individual hair strands, fabric textures, material reflections, and subtle imperfections. Use realistic lighting and accurate material properties. Avoid plastic-looking surfaces, excessive smoothing, artificial details, or oversharpening."


