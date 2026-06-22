# 0009. Disambiguation-hub entries may replace the middle beats with custom sections

**Status:** Accepted
**Last updated:** 2026-06-22

### What we learned:
The canonical entry scaffold (Definition, Why it matters, Example, optional Common mistake and In practice for deep entries, Related terms, Further reading) assumes a term that names one thing.
A few terms are polysemous hubs whose job is not to define one concept but to name several distinct senses of a word and route the reader to the right entry for each.
Forcing the standard middle beats onto such a hub produces contrived content, because a single Example or Common mistake cannot speak to several unrelated senses at once.
We allow a disambiguation-hub entry to replace the middle teaching beats (Example, and for deep entries Common mistake and In practice) with custom sections that serve the disambiguation, while keeping the opening (Definition, Why it matters) and the closing (Related terms, Further reading) exactly as the standard requires.
The rejected alternatives: forcing the canonical beats, which pads the entry with contrived examples; and promoting hubs to the `entry_type: overview` type, which is reserved for the seven topic categories and carries different frontmatter and a Key terms tour, heavier than a within-cluster disambiguation needs.

### Why it matters:
This keeps consistency where it helps and allows flexibility where the standard fights the content.
A reader who lands on an overloaded word gets its senses sorted out immediately and a link to the precise entry for the sense they meant, which is the whole value of a hub.
Holding Definition, Related terms, and Further reading invariant means retrieval (the Definition is still the quotable line an AI returns) and graph wiring (related and tags still resolve normally) stay uniform across every entry, hub or not.
It is a narrow, named exception rather than a loosening of the scaffold, so most entries still follow the seven-beat pattern unchanged.

### Implementation notes:
`terms/mark.md` is the reference example: it keeps Definition, Why it matters, Related terms, and Further reading, and replaces the middle beats with `## The four senses of "mark"` and `## In Unicode`.
A disambiguation hub is still an ordinary term, not an overview: it declares `depth` (mark is `deep`), tags to its topic term, and is not `entry_type: overview`.
Use the exception sparingly, only when a term genuinely carries multiple independent senses that each have, or warrant, their own entry; a term with a single sense uses the standard beats.
The custom sections should still read in voice and gloss their jargon like any other beat.

### Documented in:
`terms/mark.md` (exemplar); `glossary-canonical-entry-format.md`; the `glossary-entry` authoring standard.
