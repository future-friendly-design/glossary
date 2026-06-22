# 0010. Term relationships: Parent/Child is the nesting hierarchy; Groupings are faceted views

**Status:** Accepted
**Last updated:** 2026-06-22

> Revision note: this record originally defined Parent/Child as a strict "is-a" taxonomy. We broadened it to "nested under" (broader/narrower) because strict is-a kept blocking legitimate nestings: a reference source like Ethnologue is not "a kind of language", but it clearly belongs nested under the Language domain. The two-structure decision (one hierarchy in Parent/Child, facets in Groupings) is unchanged; only the meaning of the hierarchy edge is broadened.

> Revision note (2026-06-22b): the nesting tree should be as complete as the concepts allow.
> Every term has a parent unless it is a genuine top-level concept within its domain (for example Character, Character encoding, Typeface).
> Leaving facet terms (anatomy parts, behaviors, marks) unparented is not required, and should not be the default: a term's grouping membership and its parent are independent, so a term can and usually should have both.
> Where a clean parent exists, nest to it; accept a small number of genuine roots; mint an intermediate concept term only where it earns its place.
> This does not change the two-structure model, it just stops the tree from being left sparse.

> Revision note (2026-06-22c): the seven topic anchors now serve as the roots of the nesting tree.
> Each cluster's top concept(s) are nested under its topic anchor (Typography -> Typeface, Tracking, Line height, Measure; Characters -> Character, Unicode, Character encoding; Shaping -> OpenType, Complex text layout, Ligature; Language & linguistics -> Language; Writing systems & scripts -> Writing system; Internationalization & engineering -> Internationalization; Reference sources -> Noto fonts, SIL).
> So every topic has children and every term traces up to a topic root, giving one rooted tree per cluster.
> Tags / "Terms in this topic" still records topic membership as before; Parent/Child now additionally roots each tree at its topic anchor, so the anchor rows participate in both structures.
> Side effect: Writing system moved from under Language to under the Writing systems & scripts topic, severing the earlier Language -> Writing system edge (a language and its writing system now sit in sibling topic trees).

### What we learned:
The tracker needs to express how terms relate, and several different relationships kept getting tangled into one field, which made the structure hard to learn and to navigate.
We separated them into two structures.
The Terms table's Parent/Child self-link holds a single nesting hierarchy: a term's parent is what it is nested under, one level up, one parent per term (Cyrillic under Alphabet under Script; Ethnologue under Language).
This is broader/narrower in the thesaurus sense: usually "is a kind of" (Arabic is a kind of abjad), but it also covers "is scoped under / belongs to" (Ethnologue is a reference source that belongs under the Language domain).
The Groupings table ("Groupings in Glossary Pages") holds faceted, cross-cutting views of the same terms (anatomy, rules, classifications, examples, reference/measurement), where a term can belong to several groupings and a grouping can pull terms from any topic.
The rejected alternative is using Parent/Child for several unrelated relationships at once (mixing the nesting with the facets), which is the entangled pattern that makes this domain hard to understand; the facets belong in the Groupings table instead.

### Why it matters:
One field, one meaning: "what is this nested under?"
Holding it to that single question keeps the hierarchy clean and linear, one parent per term.
Everything else (the parts, the behaviors, the instances, the measurements, and any other way to slice the same terms) is a facet, and facets live in the Groupings table, where they can overlap and cross topic boundaries without distorting the hierarchy.
This keeps the nesting tree legible while still letting us arrange the same terms many ways for different reader needs ("show me all the scripts" versus "show me the kinds of script").
The two structures are complementary, not competing: the tree is the canonical nesting, the groupings are presentational arrangements.

### Implementation notes:
Terms table: "Child of" (the parent it is nested under) and "Parent of" (the inverse) are a paired self-link, so setting one populates the other. Example chains: Script -> Abjad -> Arabic (is-a); Language -> Ethnologue (belongs-under).
Groupings table: one row per page-section, named "{Cluster} {facet}" (for example "Script classifications", "Language rules"); the "Terms" link lists members and is cross-cutting (for example "Script anatomy" includes Mark, which is tagged Characters/encoding).
Facets in use: anatomy (the parts), rules (behaviors and how you must handle it), classifications (the kinds; is/is-not lists), examples (instances; may be empty where there are no instance entries, as with Language), reference/measurement (identify, count, grade).
Short versions of these definitions live in the Airtable field descriptions, so the model is self-documenting in the base.
Other ways to arrange the same terms are explored in the Groupings table, not by re-pointing Parent/Child.

### Documented in:
Airtable base `appkuyo4Qxd4JpbO4`: Terms table "Child of" / "Parent of" fields and the "Groupings in Glossary Pages" table, plus the field descriptions there.
