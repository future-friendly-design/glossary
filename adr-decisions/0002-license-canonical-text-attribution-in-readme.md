# 0002. LICENSE holds the canonical CC BY 4.0 text; attribution lives in the README

**Status:** Accepted
**Last updated:** 2026-06-20

### What we learned:
GitHub auto-detects a license by matching the `LICENSE` file against the canonical text of a known license.
Prepending a copyright header into the CC BY 4.0 legal code breaks that match, so the repository shows no detected license.
We keep `LICENSE` as the unmodified canonical CC BY 4.0 text and put the copyright and attribution marking in the README.
The marking is the copyright line (2026 Future Friendly Designs Inc.), the CC BY 4.0 name, and the canonical license URL.
That is also where Creative Commons recommends a work's marking live, since the legal code itself is meant to be verbatim.

### Why it matters:
The license badge is how a reader and a tool confirm the terms at a glance.
Detection only works against the unmodified text, and the CC legal code is not meant to be edited.
Separating "the license" (verbatim, in `LICENSE`) from "who holds it and how to credit" (the marking, in the README and per-entry frontmatter) satisfies both correctness and discoverability.

### Implementation notes:
`LICENSE` is the canonical CC BY 4.0 text with no edits.
The README license section carries the copyright line, the CC BY 4.0 name, and the canonical URL.
Each entry's frontmatter also carries `license: CC-BY-4.0`.
Detection was confirmed via `gh api repos/.../license`, which reports `CC-BY-4.0`.

### Documented in:
`LICENSE`; README license section; entry frontmatter (`license`).
