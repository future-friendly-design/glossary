# 0011. Linguistic clusters move into dedicated sub-sections; the main glossary stays design-systems-scoped

**Status:** Accepted
**Last updated:** 2026-06-23

### What we learned:
The glossary's primary audience is design-systems and typography practitioners, but the term set grew to include deep linguistics and writing-systems material (scripts, marks, orthography, language classification) that is valuable but is not what most readers come for.
Keeping every term in one flat A-Z browse made the main navigation read like a linguistics reference rather than a design-systems glossary.
We are reorganizing the information architecture so the main glossary stays scoped to design-systems and typography terms, and the linguistic material lives in its own dedicated sub-sections.
The first is "Writing systems & scripts" under a "language and linguistics terms" group; "Language" is the next planned one.
Sam reviews, clarifies, and rewrites each cluster's terms before moving them into its sub-section, so the move is a content-review gate, not a bulk file shuffle.
The rejected alternative is leaving everything flat in `terms/` and separating only via topic tags and groupings, which gives the linguistic material no navigable home of its own and leaves the main IA unfocused.

### Why it matters:
Readers get a main glossary that matches the site's purpose, with the linguistics depth available but not dominating the front door.
Each linguistic cluster gets a curated landing page that introduces the cluster and links its terms by facet, rather than a flat list.
Because the relationship scaffolding (ADR 0010 Parent/Child tree plus Groupings) is independent of file location, the move does not disturb the graph; only navigation and file paths change.

### Implementation notes:
File layout is now hybrid: most entries stay flat in `terms/{slug}.md`; a reviewed cluster moves into a topic subfolder, for example `language-terms/writing-systems-and-scripts/{slug}.md`, with a `README.md` landing page.
The landing page groups members by facet (Anatomy of a writing system, Anatomy of a script, Symbol terms, Mark terms, Script rule terms, Script classification terms, Scripts to explore) using GitBook content-ref cards; lists are alphabetized and script groups are labeled and alphabetized by type.
GitBook owns this reorg: it is authored in the GitBook editor and arrives over Git Sync as `GITBOOK-*` commits, so agents should expect the layout to keep shifting cluster by cluster and should not re-impose the old flat-only convention.
Caveat: editing a term file in git breaks any GitBook content-ref card pointing at it until GitBook re-resolves (opening the edit branch or re-syncing rebinds the cards, the file is fine), and frontmatter must never use folded or literal block scalars; see `agent-progress-handover.md`.
This broadens, it does not replace, ADR 0008 (A-Z letter folders as the canonical browse): the A-Z backbone remains for the design-systems set, and the linguistic clusters add a curated, sectioned home on top.

### Documented in:
`SUMMARY.md` (the "language and linguistics terms" section and the `language-terms/.../` paths); `language-terms/writing-systems-and-scripts/README.md` (the first cluster landing page); `agent-progress-handover.md` (current direction and pending work).
