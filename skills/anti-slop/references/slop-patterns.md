# Slop Patterns

Use this file when scanning or revising text for common LLM prose tells. Apply the rules conservatively. A single instance can be fine. Repetition, clustering, and needless theatrics are the actual problem.

This rule set is adapted for editorial use from common AI-writing-tell lists, including tropes.fyi, and from practical rewrite heuristics that focus on local fixes over theatrical diagnosis.

## Sentence-level patterns

### Inflated word choice

- `magic-adverbs`: Adverbs such as `quietly`, `deeply`, `fundamentally`, `remarkably`, or `arguably` that inject false significance.
  Rewrite move: delete the adverb or replace it with a concrete description.
- `delve-vocab`: AI-favored vocabulary such as `delve`, `certainly`, `utilize`, `leverage` as a verb, `robust`, `streamline`, or `harness`.
  Rewrite move: use the plain word the sentence actually needs.
- `ornate-abstractions`: Grand nouns such as `tapestry`, `landscape`, `paradigm`, `synergy`, `ecosystem`, or `framework` when the sentence could name the actual thing.
  Rewrite move: replace the abstraction with the concrete domain, system, or practice being discussed.
- `serves-as-dodge`: Fancier copulas such as `serves as`, `stands as`, `marks`, or `represents` where `is` or `are` would be cleaner.
  Rewrite move: use the simple verb unless the stronger verb is literally necessary.

### Formulaic sentence structures

- `negative-parallelism`: `not X but Y`, `it's not X. It's Y.`, or em-dash dismissals used for false profundity.
  Rewrite move: state the point directly once.
- `dramatic-countdown`: `Not X. Not Y. Just Z.` or similar staged negation.
  Rewrite move: say `Z` directly.
- `self-posed-reveal`: `The result?`, `The problem?`, `The scary part?` and similar question-answer pivots.
  Rewrite move: fold the answer into a normal sentence.
- `anaphora-abuse`: Several consecutive sentences opening the same way.
  Rewrite move: vary openings or compress the repeated sequence.
- `tricolon-abuse`: repeated rule-of-three phrasing or stacked rhythmic lists.
  Rewrite move: break the cadence; keep only the list items that add information.
- `empty-transition`: fillers such as `It's worth noting`, `Importantly`, `Interestingly`, `Notably`, or `It bears mentioning`.
  Rewrite move: delete the transition and let the point carry itself.
- `superficial-analysis-tail`: trailing `-ing` phrases that pretend to add significance, such as `highlighting`, `underscoring`, `reflecting`, or `contributing`.
  Rewrite move: cut the tail unless it adds specific information.
- `false-range`: `from X to Y` constructions where X and Y are not points on a real spectrum.
  Rewrite move: list the items plainly or define the actual range.

### Tone and stance

- `false-suspense`: `Here's the kicker`, `Here's the thing`, `Here's where it gets interesting`, `Here's what most people miss`.
  Rewrite move: delete the setup and state the point.
- `patronizing-analogy`: `Think of it as` or `It's like` when the analogy adds less clarity than the original.
  Rewrite move: explain the idea directly unless the analogy genuinely clarifies it.
- `imagine-a-world`: speculative invitation language used to sell a premise through mood rather than argument.
  Rewrite move: make the claim directly and support it.
- `false-vulnerability`: polished confessions or stage-managed honesty that perform authenticity without risk.
  Rewrite move: either be specific and necessary or cut it.
- `truth-is-simple`: phrases that assert clarity, simplicity, or obviousness instead of proving the point.
  Rewrite move: remove the assertion and strengthen the argument itself.
- `grandiose-stakes`: world-historical framing for modest claims.
  Rewrite move: scale the claim to the evidence.
- `teacher-voice`: `Let's break this down`, `Let's unpack`, `Let's dive in`, `Let's explore`.
  Rewrite move: start with the substance, not the tutorial framing.
- `vague-attribution`: `experts say`, `observers note`, `industry reports suggest` without naming the source.
  Rewrite move: name the source or remove the attribution.
- `invented-label`: ad hoc analytical tags such as `acceleration trap`, `supervision paradox`, or `workload creep` presented as if established.
  Rewrite move: describe the actual mechanism instead of coining a label.

### Formatting tells

- `em-dash-addiction`: dramatic overuse of em dashes for pivots, asides, and reveals.
  Rewrite move: replace with a period, comma, colon, or nothing.
- `bold-first-bullets`: every bullet starts with a bolded keyword or clause.
  Rewrite move: use plain bullets unless emphasis is genuinely useful.
- `unicode-decoration`: arrows, curly quotes, or ornamental Unicode where plain ASCII would be more natural for the document.
  Rewrite move: use ordinary punctuation unless house style requires otherwise.

## Document-level patterns

- `fractal-summary`: repeated mini-summaries at section and document level.
  Rewrite move: keep only the summary that earns its place.
- `dead-metaphor`: one metaphor repeated across the whole piece long after it stops helping.
  Rewrite move: use the metaphor once, then return to literal language.
- `historical-analogy-stacking`: rapid-fire lists of historical examples to borrow authority without adding analysis.
  Rewrite move: keep the best example or explain why each example matters.
- `one-point-dilution`: one thesis stretched across many paragraphs with little net new information.
  Rewrite move: compress repeated claims and keep only the paragraph that advances the argument.
- `content-duplication`: repeated paragraphs or near-repeated sections.
  Rewrite move: delete the duplicate and preserve the stronger version.
- `rhetorical-self-repetition`: the manuscript repeatedly reaches for the same argumentative hinge, especially patterns like `not X but Y`, `this is not ... it is ...`, or `what matters is ...`.
  Rewrite move: keep the strongest instance, then restate later points without the same reveal scaffold.
- `signposted-conclusion`: `In conclusion`, `To sum up`, `In summary`.
  Rewrite move: conclude without announcing the conclusion.
- `despite-its-challenges`: formulaic concession structure that acknowledges problems only to swat them away.
  Rewrite move: either engage with the challenge concretely or remove the ritual concession.
- `short-punchy-fragments`: many fragment paragraphs used for fake emphasis.
  Rewrite move: recombine them into normal prose unless one fragment is doing real work.
- `listicle-in-a-trench-coat`: disguised list structure in prose with repeated `first`, `second`, `third` framing.
  Rewrite move: either use a real list or write continuous prose without ordinal scaffolding.

## Revision priorities

When several patterns appear together, prioritize fixes in this order:

1. Remove factual overstatement, vague attribution, and unsupported certainty.
2. Remove repeated structural gimmicks such as negative parallelism, self-posed reveals, and countdown sentences.
3. Cut filler transitions, summary, and teacher-mode framing.
4. Replace inflated diction with concrete words.
5. Break document-level repetition by compressing or deleting redundant paragraphs.

## Slop Cop parity checklist

Use this checklist as a second-pass audit when the prose still feels suspiciously AI-shaped after an initial cleanup. These rule IDs come from the detector app and are worth checking explicitly because they are easy to miss in a looser editorial pass.

### Lexical and opener checks

- `overused-intensifiers`: words such as `crucial`, `vital`, `robust`, `nuanced`, `unprecedented`.
  Rewrite move: delete or prove the intensity.
- `almost-hedge`: phrases such as `almost always`, `almost never`, `almost certainly`.
  Rewrite move: commit to the claim or use a precise qualifier like `usually`.
- `era-opener`: `In an era of...`, `In a world where...`.
  Rewrite move: delete the opener and start at the point.
- `broader-implications`: `broader implications`, `wider implications`.
  Rewrite move: name the actual implication or cut the phrase.
- `important-to-note`: `it is important to note`, `it's worth noting`, `it should be noted`.
  Rewrite move: delete the preamble and say the thing.
- `connector-addiction`: paragraph-openers such as `Furthermore`, `Moreover`, `Additionally`, `However`, `That said`.
  Rewrite move: let the paragraph connect through content, not connector words.
- `sycophantic-frame`: `Great question`, `This is fascinating`, or other flattering setup.
  Rewrite move: delete it and start with content.

### Sentence-structure checks

- `colon-elaboration`: a short clause followed by a colon and an overlong explanation.
  Rewrite move: merge into one sentence or split into two normal ones.
- `staccato-burst`: several very short sentences in the same rhythm.
  Rewrite move: vary cadence by combining or expanding.
- `parenthetical-qualifier`: `(of course)`, `(to be fair)`, `(admittedly)` style qualifiers.
  Rewrite move: integrate if essential, delete otherwise.
- `unnecessary-contrast`: `whereas`, `as opposed to`, `unlike`, `in contrast to` when the contrast adds nothing.
  Rewrite move: state the claim directly.
- `listicle-instinct`: magic-number lists with exactly 3, 5, 7, or 10 items.
  Rewrite move: use the natural number of items or rewrite as prose.
- `balanced-take`: a point immediately softened into nothing by reflexive concession.
  Rewrite move: state the argument cleanly, then address real counterarguments separately.
- `unnecessary-elaboration`: the sentence makes its point, then keeps restating it.
  Rewrite move: stop when the sentence is done.
- `pivot-paragraph`: a one-sentence paragraph that does no work except transition.
  Rewrite move: delete it or absorb it into neighboring prose.

### Paragraph and formatting checks

- `metaphor-crutch`: tired metaphors such as `double-edged sword`, `tip of the iceberg`, `north star`, `game-changer`.
  Rewrite move: use plain language or a specific image.
- `dramatic-fragment`: a standalone paragraph with four words or fewer used for fake emphasis.
  Rewrite move: absorb it into surrounding prose.
- `bold-first-bullets`: markdown bullets that begin with a bolded label.
  Rewrite move: write the bullet plainly or turn it into prose.
- `unicode-arrows`: the `->` or `→` style arrow used decoratively in prose.
  Rewrite move: write out the relationship directly.

### Document-scale checks

- `historical-analogy`: stacked references to famous companies, eras, or revolutions used as borrowed authority.
  Rewrite move: keep one developed analogy or remove them.
- `dead-metaphor`: the same metaphor repeated throughout the piece.
  Rewrite move: keep the best use and strip the rest.
- `one-point-dilution`: the same thesis restated across multiple paragraphs.
  Rewrite move: cut the redundant restatement.
- `fractal-summaries`: meta-commentary that previews or recaps instead of advancing.
  Rewrite move: delete the preview/recap and deliver the content.
