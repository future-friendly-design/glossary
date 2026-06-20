# 0008. A-Z letter folders are the canonical navigation; topics are presentational views

**Status:** Accepted
**Last updated:** 2026-06-20

### What we learned:
The first navigation used the seven topic categories as the structural backbone, with each term nested under its category.
That forces every term to have one "home" category, which fights the data model (terms carry multi-value tags and belong to several contexts) and fails the reader who knows the term but not its category.
We inverted it: the flat alphabetical index is the canonical backbone, where every term has exactly one home under its first letter, and the topic overviews became presentational views that link into those canonical pages rather than containing them.
The rejected alternative, a topic tree as the primary structure, keeps the multi-category filing problem inside the navigation; a single flat A-Z list was also rejected for the long scroll and lack of progressive disclosure.

### Why it matters:
This separates an unambiguous structure (the alphabet) from flexible curation (topics).
A term that belongs to several topics is referenced from each without being filed in one, so the multi-category problem disappears rather than being mitigated.
It serves both readers: the term-seeker uses search or the A-Z index, and the explorer uses the topic views.
It matches the project's "one source of truth, many derived views" architecture (the term file is the source, the A-Z is the canonical index, topic pages are views), and it is future-proof: as the scope grows toward a full design-system glossary, new terms slot into a letter with no taxonomy decision required.

### Implementation notes:
In `SUMMARY.md`, "Browse all terms" groups the 115 member terms under linkless letter items (`* A` with nested term pages); GitBook renders these as collapsible folders (progressive disclosure), and clicking a letter shows GitBook's auto-generated card index of that letter's terms.
"Browse by topic" lists the seven overview pages flat, with no nested terms.
Each of the 122 files appears exactly once: overviews under topic, terms under their letter.
`SUMMARY.md` is generated from the term files, so the index stays correct as terms are added; GitBook's built-in search is the primary lookup for a known term.
GitBook's default group-page heading ("Here are the articles in this section:") is not customizable through Git Sync.
Illustrated topic card galleries are a planned future enhancement on top of this structure, not part of this decision.

### Documented in:
`SUMMARY.md`; the GitBook published navigation.
