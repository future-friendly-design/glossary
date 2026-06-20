# 0006. Prose in repo docs uses semantic line breaks

**Status:** Accepted
**Last updated:** 2026-06-20

### What we learned:
Prose in the hand-written docs (this decisions log, README, CONTRIBUTING, AGENTS) is wrapped with semantic line breaks: one sentence per line, with a long sentence broken at a major clause boundary.
This is a middle path between two extremes.
Hard-wrapping every line at a fixed column keeps files narrow, but inserting a word forces a reflow cascade that re-wraps and re-diffs many following lines.
Putting a whole paragraph on one line avoids the cascade, but a one-word edit then re-diffs the entire paragraph and forces horizontal scrolling to read.
Semantic line breaks avoid both: an edit stays on one short line, so diffs are precise and nothing scrolls sideways.
Markdown renders identically either way, since a single newline inside a paragraph collapses to a space.

### Why it matters:
These files live in version control and are reviewed in pull requests.
Line-based diffs and `git blame` are only as readable as the line breaks allow, so a wrapping style that keeps each edit local makes review and history genuinely easier.

### Implementation notes:
Break after each sentence; break a long sentence at a major clause boundary (after a comma joining independent clauses, or after a semicolon or colon).
This applies to the prose docs.
The term entries in `terms/` currently use one line per paragraph; they are not reflowed wholesale, though a new or heavily edited entry may adopt semantic line breaks too.

### Documented in:
This convention, applied across the docs; the `setup-gitbook-project` setup procedure.
