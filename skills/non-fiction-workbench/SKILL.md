---
name: non-fiction-workbench
description: Brief-aware drafting, rewriting, and critique for long-form non-fiction organized around draft files plus brief, research, and style folders. Use when working on an essay, article, chapter, newsletter, or full manuscript and needing to preserve thesis, evidence, structure, and voice.
argument-hint: <write|rewrite|critique|global-critique|global-rewrite> <draft-file-or-drafts-dir>
disable-model-invocation: true
---

Treat the human as the author. Your job is to reduce drift, preserve factual integrity, and improve discipline across a non-fiction project.

Parse the invocation arguments like this:

- Mode: `$0`
- Target draft file or drafts directory: `$1`

If either is missing, ask one short clarifying question and stop.
If the mode is not `write`, `rewrite`, `critique`, `global-critique`, or `global-rewrite`, explain the valid modes briefly and stop.

## Workflow

1. Read the target draft first.
2. Then inspect this project structure when the files exist:
   - `brief/thesis.md`
   - `brief/audience.md`
   - `brief/constraints.md`
   - `brief/outline.md`
   - `style/voice.md`
   - `style/house-style.md`
   - `research/source-index.md`
   - `research/notes/`
   - `research/excerpts/`
   - `drafts/`
3. Read `brief/thesis.md`, `brief/constraints.md`, `style/voice.md`, and `style/house-style.md` when they exist.
4. Read `brief/outline.md` and `brief/audience.md` when structure, ordering, or explanatory depth matters.
5. Read only the research notes and excerpts that are clearly relevant to the claims in the target draft.
6. Read adjacent draft files only when chronology, cross-references, or repeated framing depends on them.
7. Use the reference guide at `references/project-shape.md` when the project layout needs interpretation.
8. If the target is a directory or the mode is manuscript-level, read the draft files in natural order and treat them as one continuous work.
9. Work from the text and sources that exist. Do not invent sourcing, examples, quotations, numbers, or certainty.

## Global Rules

- Preserve the author's thesis, argument, and level of certainty unless the user asks for a substantive change.
- Preserve citations, quotations, markdown structure, and the project's spelling and punctuation conventions.
- Do not introduce facts, chronology, examples, names, statistics, or causal claims that are not supported by the draft or source material.
- When evidence is thin, reduce overclaiming instead of papering over the gap.
- Prefer specific, direct prose over generic explanation.
- Remove throat-clearing, filler transitions, and ornamental abstraction.
- Avoid rhetorical self-repetition across a manuscript. Patterns such as `not X but Y`, `this is not ... it is ...`, or repeated `what matters is ...` can work once but weaken trust when they recur.
- Keep the reader's trust in view. Precision beats flourish.
- Prefer the smallest amount of research lookup needed to do the job well.
- Keep output aligned with the mode requested.

## Mode: `write`

Use this mode to draft, expand, or rewrite a non-fiction piece from the existing brief and source material.

- Follow the thesis, audience, constraints, and outline when they exist.
- Preserve the intended argument, scope, and burden of proof.
- Turn notes into clean prose without laundering speculation into fact.
- Where source support is missing, either keep the language appropriately qualified or leave a tight bracketed note such as `[source needed]`.
- Favor forward argument over summary-heavy setup.
- If editing the file directly is appropriate in the current session, update the target file. Otherwise return the revised draft only.

Output:

- Revised draft only, unless the user explicitly asks for commentary.

## Mode: `rewrite`

Use this mode for full-draft revision without changing the underlying thesis or factual content.

- Improve clarity, compression, sequencing, and paragraph flow.
- Tighten topic sentences, transitions, and endings.
- Cut repetition, inflated diction, and false emphasis.
- Preserve meaning, evidence, and the draft's core structure unless a local move clearly improves readability.
- Do not quietly add sourcing, examples, or certainty.
- If editing the file directly is appropriate in the current session, update the target file. Otherwise return the rewritten text only.

Output:

- Rewritten version only, unless the user explicitly asks for notes.

## Mode: `critique`

Use this mode for editorial feedback only.

- Do not rewrite unless the user explicitly asks for it after the critique.
- Evaluate thesis clarity and argumentative coherence.
- Evaluate whether claims are supported by the available evidence.
- Evaluate structural sequencing, pacing, and reader orientation.
- Evaluate voice consistency and sentence-level drag.
- Identify overclaiming, missing support, repeated points, generic phrasing, and trust-breaking moves.
- Cite concrete problem spots when possible.
- Be specific and direct.

Output headings:

- `What is working`
- `What is weak or overstated`
- `Where support is missing or thin`
- `What to strengthen next`

## Mode: `global-critique`

Use this mode for manuscript-level editorial feedback across a full draft directory.

- Read the draft files in order and evaluate the work as one argument.
- Look for thesis drift, structural repetition, redundant sections, and pressure points where the argument starts to feel pre-confirmed rather than discovered.
- Identify repeated rhetorical moves across chapters or sections, especially recurring reversals, summary cadences, and self-validating transitions.
- Check whether evidence density, tone, and explanatory depth stay calibrated from start to finish.
- Point out where a chapter-level fix will not solve a manuscript-level weakness.

Output headings:

- `Manuscript strengths`
- `Recurring weaknesses`
- `Where the argument repeats or hardens too early`
- `Structural revisions to make next`

## Mode: `global-rewrite`

Use this mode to revise a full draft directory while preserving thesis, evidence, and overall architecture.

- Rewrite chapter by chapter, but keep a running view of repeated framing, repeated conclusions, and repeated rhetorical scaffolds.
- Remove cross-manuscript habits that make the prose feel templated.
- Preserve terminology unless inconsistency itself is the problem.
- Do not normalize every chapter into the same cadence; variation is part of readable long-form work.
- If editing files directly is appropriate in the current session, update the draft files in place. Otherwise return the revised manuscript in a clearly segmented form.

Output:

- Revised manuscript only, unless the user explicitly asks for notes.
