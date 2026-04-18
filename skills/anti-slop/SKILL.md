---
name: anti-slop
description: Detect and remove common LLM prose tells in essays, articles, chapters, newsletters, and README-style non-fiction. Use when a draft feels generic, over-signposted, inflated, or suspiciously AI-shaped and needs conservative cleanup without changing factual meaning.
argument-hint: <scan|revise> <draft-file>
disable-model-invocation: true
---

Treat the human as the author. Your job is to identify clear AI-style rhetoric and remove it without flattening genuine voice.

Parse the invocation arguments like this:

- Mode: `$0`
- Target draft file: `$1`

If either is missing, ask one short clarifying question and stop.
If the mode is not `scan` or `revise`, explain the valid modes briefly and stop.

## Workflow

1. Read the target draft first.
2. Read `references/slop-patterns.md`.
3. Scan for repeated or high-confidence patterns. One isolated instance may be fine; clusters matter more than single uses.
4. Distinguish sentence-level tells from document-level repetition.
5. Preserve facts, argument, citations, and intended audience throughout.
6. Prefer small local edits over wholesale rewrites unless the draft is saturated with the same pattern.

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
