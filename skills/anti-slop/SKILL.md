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
3. Do not trust one pass. Run at least these passes in order:
   - lexical and diction pass
   - sentence-structure pass
   - paragraph and formatting pass
   - document-scale repetition pass
4. Use the parity checklist in `references/slop-patterns.md` to cross-check obvious misses against the denser Slop Cop rule inventory.
5. Distinguish sentence-level tells from document-level repetition.
6. Preserve facts, argument, citations, and intended audience throughout.
7. If the target is a directory or the mode is manuscript-level, read the draft files in order and look for recurrence across the full work.
8. For `revise` or `global-revise`, do a second verification pass before finishing and remove any obvious surviving triggers.
9. Prefer small local edits over wholesale rewrites unless the draft is saturated with the same pattern.

## Global Rules

- Be conservative. Flag only clear cases.
- Do not treat ordinary competent prose as AI slop just because it is clean.
- Remove patterns, not personality.
- Preserve factual content, named entities, chronology, quotations, and level of certainty.
- Prefer deletion, simplification, or a concrete verb over a fancy synonym.
- Rewrite only the matched span when a local fix is enough.
- If a sentence is structurally sound but uses one weak tell, fix the tell and keep the sentence.
- Avoid replacing one canned pattern with another.
- If a deletion solves the problem cleanly, delete instead of paraphrasing.
- Pay special attention to high-yield misses from Slop Cop such as `overused-intensifiers`, `important-to-note`, `connector-addiction`, `negation-pivot`, `question-then-answer`, `balanced-take`, `unnecessary-elaboration`, `vague-attribution`, `one-point-dilution`, and `fractal-summaries`.

## Mode: `scan`

Use this mode when the user wants diagnosis before rewriting.

- Identify high-confidence sentence-level tells.
- Identify document-level repetition such as repeated framing, repeated cadence, repeated conclusions, or repeated analogy patterns.
- Call out density, not just existence. Three uses of one trope matter more than one use of three different tropes.
- Check for anything the parity checklist would flag even if it feels boring: filler openers, throat-clearing, empty concessions, overused connectors, and sentence-overrun.
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
- Keep a running mental checklist of already-fixed rule families so you do not leave the same pattern elsewhere in the same piece.
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
- Cross-check for rule families that often survive first-pass revision, especially `connector-addiction`, `balanced-take`, `unnecessary-elaboration`, `pivot-paragraph`, and `fractal-summaries`.

Output headings:

- `Recurring sentence-level tells`
- `Manuscript-scale repetition`
- `Highest-value cleanup passes`

## Mode: `global-revise`

Use this mode when the user wants slop removed across a full draft directory.

- Revise the manuscript in order, keeping a running list of repeated tells already seen.
- Remove repeated rhetorical templates, not just their loudest individual example.
- Vary sentence openings, transitions, and paragraph endings when repetition is the problem.
- Re-scan each revised file for obvious surviving parity-check violations before moving on.
- Keep chapter identity intact; do not force every section into the same stripped cadence.
- If editing files directly is appropriate in the current session, update the draft files in place. Otherwise return the revised manuscript in a clearly segmented form.

Output:

- Revised manuscript only, unless the user explicitly asks for notes.
