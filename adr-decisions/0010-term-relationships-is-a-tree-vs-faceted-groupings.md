# 0010. Term relationships: Parent/Child is the is-a tree; Groupings are faceted views

**Status:** Accepted
**Last updated:** 2026-06-22

### What we learned:
The tracker needs to express how terms relate, and two different relationships kept getting tangled into one field, which made the structure hard to learn and to navigate.
We separated them.
The Terms table's Parent/Child self-link holds a single strict is-a taxonomy: a term's parent is the broader category it is a kind of (Cyrillic is-a Alphabet is-a Script; Arabic is-a Abjad is-a Script), one parent per term.
The Groupings table ("Groupings in Glossary Pages") holds faceted, cross-cutting views of the same terms (anatomy, rules, classifications, examples, reference/measurement), where a term can belong to several groupings and a grouping can pull terms from any topic.
The rejected alternative is using Parent/Child for everything, mixing is-a with part-of, membership, and classification, which is the entangled pattern that makes this domain hard to understand in the first place.
Flattening classification into Parent/Child as intermediate levels was also considered and rejected: it buries the concrete entities (the actual scripts) as leaves and leaves no single findable list of them.

### Why it matters:
One field, one meaning.
Parent/Child answers exactly one question, "what kind of thing is this?", so it stays clean and linear.
Everything else (the parts, the behaviors, the instances, the measurements) is a facet, and facets live in the Groupings table, where they can overlap and cross topic boundaries without distorting the tree.
This keeps the is-a tree legible while still letting us arrange the same terms many ways for different reader needs ("show me all the scripts" versus "show me the kinds of script").
The two structures are complementary, not competing: the tree is the canonical type lineage, the groupings are presentational arrangements.

### Implementation notes:
Terms table: "Child of" (parent = the kind it belongs to) and "Parent of" (the inverse) are a paired self-link, so setting one populates the other. Example chain: Script -> Abjad -> Arabic.
Groupings table: one row per page-section, named "{Cluster} {facet}" (for example "Script classifications", "Language rules"); the "Terms" link lists members and is cross-cutting (for example "Script anatomy" includes Mark, which is tagged Characters/encoding).
Facets in use: anatomy (the parts), rules (behaviors and how you must handle it), classifications (the kinds; is/is-not lists), examples (instances; may be empty where there are no instance entries, as with Language), reference/measurement (identify, count, grade).
Short versions of these definitions live in the Airtable field descriptions, so the model is self-documenting in the base.
Alternate hierarchies (other ways to arrange the same terms) are explored in the Groupings table, not by re-pointing Parent/Child.

### Documented in:
Airtable base `appkuyo4Qxd4JpbO4`: Terms table "Child of" / "Parent of" fields and the "Groupings in Glossary Pages" table, plus the field descriptions there.
