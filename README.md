# Non-Fiction Workbench

LLM agent skills for long-form non-fiction writing and revision.

- `/non-fiction-workbench` for drafting, rewriting, and critiquing non-fiction against a brief, source set, and house style.
- `/anti-slop` for detecting and removing common LLM prose tells without changing factual meaning.

## Why This Exists

AI-assisted non-fiction usually fails in predictable ways:

- claims get stronger than the evidence
- structure drifts away from the brief
- paragraphs bloat with transitions, summary, and throat-clearing
- rewrites flatten voice and introduce generic "smart" phrasing

This repo gives agents a tighter workflow for essays, articles, reported features, newsletters, and book chapters. It does not replace authorship or reporting. It gives the model a disciplined way to read the draft, inspect the brief and source material, and revise without hallucinating or padding.

The anti-slop skill is informed by common LLM prose-tell catalogs, including the public taxonomy at [tropes.fyi](https://tropes.fyi/tropes-md), then distilled into rewrite-oriented rules for actual editorial use.

## What's Included

```text
non-fiction-workbench/
├── README.md
├── LICENSE
└── skills/
    ├── non-fiction-workbench/
    │   ├── SKILL.md
    │   ├── agents/
    │   │   └── openai.yaml
    │   └── references/
    │       └── project-shape.md
    └── anti-slop/
        ├── SKILL.md
        ├── agents/
        │   └── openai.yaml
        └── references/
            └── slop-patterns.md
```

## Install

Install the core writing skill:

```bash
npx skills add https://github.com/0plus1/non-fiction-workbench --skill non-fiction-workbench
```

Install the anti-slop skill:

```bash
npx skills add https://github.com/0plus1/non-fiction-workbench --skill anti-slop
```

## Usage

Invoke the core skill manually:

```text
/non-fiction-workbench write drafts/article.md
/non-fiction-workbench rewrite drafts/article.md
/non-fiction-workbench critique drafts/article.md
```

Invoke the anti-slop skill manually:

```text
/anti-slop scan drafts/article.md
/anti-slop revise drafts/article.md
```

## Modes

`non-fiction-workbench`

- `write`: draft or expand a non-fiction piece from the brief, outline, and source material
- `rewrite`: improve an existing draft while preserving thesis, facts, and structure
- `critique`: return editorial feedback on argument, evidence, structure, and prose

`anti-slop`

- `scan`: flag clear AI-style rhetoric and document-level repetition
- `revise`: rewrite to remove AI tells while preserving factual content and argument

## Expected Project Shape

The skills are opinionated about project structure. They work best when your project looks roughly like this:

```text
your-book-or-essay/
├── brief/
│   ├── thesis.md
│   ├── audience.md
│   ├── constraints.md
│   └── outline.md
├── research/
│   ├── source-index.md
│   ├── notes/
│   └── excerpts/
├── style/
│   ├── voice.md
│   └── house-style.md
└── drafts/
    ├── chapter-1.md
    ├── essay-1.md
    └── article-x.md
```

The core skill reads the target draft first, then consults the relevant brief, style, and source files. The anti-slop skill reads the target draft and applies a conservative rule set for common LLM prose patterns.

## How They Behave

Both skills are deliberately manual. They use `disable-model-invocation: true`.

They tell agents to:

- read the target draft first
- inspect the relevant brief, style, and source files before changing claims or structure
- preserve the author's thesis, evidence, and level of certainty
- avoid inventing facts, sources, examples, chronology, or causal claims
- cut generic LLM phrasing, padding, and rhetorical scaffolding
- keep the human in charge of judgment, reporting, and final wording

For `write` and `rewrite`, the core skill is intended to revise the target draft directly when appropriate. For `critique` and `scan`, it should usually return notes unless you explicitly ask it to write those notes into project files.

## Philosophy

This repo is not an autopilot content generator.

The author still owns:

- thesis
- reporting
- structure
- taste
- final language

The agents' role here is narrower:

- reduce factual drift
- keep the brief and source material in view
- make revision more disciplined
- remove generic AI prose habits before publication
