---
name: anti-slop
description: Detect and remove common LLM prose tells in essays, articles, chapters, newsletters, and README-style non-fiction. Use when a draft or full manuscript feels generic, over-signposted, inflated, or suspiciously AI-shaped and needs conservative cleanup without changing factual meaning.
argument-hint: <scan|revise|global-scan|global-revise> <draft-file-or-drafts-dir>
disable-model-invocation: true
---

Treat the human as the author. Your job is to identify clear AI-style rhetoric and remove it without flattening genuine voice.

Parse the invocation arguments like this:

- Mode: `$0`
- Target draft file or drafts directory: `$1`

If either is missing, ask one short clarifying question and stop.
If the mode is not `scan`, `revise`, `global-scan`, or `global-revise`, explain the valid modes briefly and stop.

## Workflow

1. Read the target draft first.
2. Read `references/slop-patterns.md`.
3. Scan for repeated or high-confidence patterns. One isolated instance may be fine; clusters matter more than single uses.
4. Distinguish sentence-level tells from document-level repetition.
5. Preserve facts, argument, citations, and intended audience throughout.
6. If the target is a directory or the mode is manuscript-level, read the draft files in order and look for recurrence across the full work.
7. Prefer small local edits over wholesale rewrites unless the draft is saturated with the same pattern.

## Global Rules

- Be conservative. Flag only clear cases.
- Do not treat ordinary competent prose as AI slop just because it is clean.
- Remove patterns, not personality.
- Preserve factual content, named entities, chronology, quotations, and level of certainty.
- Prefer deletion, simplification, or a concrete verb over a fancy synonym.
- Rewrite only the matched span when a local fix is enough.
- If a sentence is structurally sound but uses one weak tell, fix the tell and keep the sentence.
- Avoid replacing one canned pattern with another.

## Mode: `scan`

Use this mode when the user wants diagnosis before rewriting.

- Identify high-confidence sentence-level tells.
- Identify document-level repetition such as repeated framing, repeated cadence, repeated conclusions, or repeated analogy patterns.
- Call out density, not just existence. Three uses of one trope matter more than one use of three different tropes.
- Cite concrete spans when possible.

Output headings:

- `High-confidence tells`
- `Document-level patterns`
- `Revision priorities`

## Mode: `revise`

Use this mode when the user wants the prose cleaned directly.

- Remove inflated diction, false suspense, rhetorical scaffolding, and generic transitions.
- Break repeated cadence patterns.
- Cut summary that merely restates the previous paragraph.
- Replace teacher-mode explanation with direct prose suited to the draft's actual audience.
- Keep the piece human, varied, and specific.
- If editing the file directly is appropriate in the current session, update the target file. Otherwise return the revised text only.

Output:

- Revised text only, unless the user explicitly asks for notes.

## Mode: `global-scan`

Use this mode when the user wants a manuscript-level slop diagnosis.

- Read the full draft directory in order.
- Identify repeated rhetorical scaffolds that become visible only across long work.
- Pay special attention to self-repetition such as recurring `not X but Y`, `this is not ... it is ...`, or `what matters is ...` turns that make the argument feel pre-confirmed.
- Note whether the manuscript reuses the same paragraph arc, same conclusion rhythm, or same explanatory stance across sections.

Output headings:

- `Recurring sentence-level tells`
- `Manuscript-scale repetition`
- `Highest-value cleanup passes`

## Mode: `global-revise`

Use this mode when the user wants slop removed across a full draft directory.

- Revise the manuscript in order, keeping a running list of repeated tells already seen.
- Remove repeated rhetorical templates, not just their loudest individual example.
- Vary sentence openings, transitions, and paragraph endings when repetition is the problem.
- Keep chapter identity intact; do not force every section into the same stripped cadence.
- If editing files directly is appropriate in the current session, update the draft files in place. Otherwise return the revised manuscript in a clearly segmented form.

Output:

- Revised manuscript only, unless the user explicitly asks for notes.
