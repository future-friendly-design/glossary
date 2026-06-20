# 0004. GitBook-safe markdown: strict-YAML frontmatter and relative links

**Status:** Accepted
**Last updated:** 2026-06-20

### What we learned:
GitBook parses content strictly, and a single malformed file fails the entire space sync, not just that page.
Two rules emerged, both learned the hard way on the first sync:

- **Quote YAML-hostile frontmatter values.**
  A scalar containing a colon-space (`: `), a leading special character, or a wrapping quote must be quoted.
  The recurring culprit is `summary`, which is prose and often contains a colon.
- **Use relative markdown links, not Obsidian `[[wiki-links]]`.**
  GitBook renders `[[slug]]` as literal text.
  Sibling entries are linked as `[Display](slug.md)`.

For link display text we settled a convention.
In the `Key terms` and `Related terms` reference lists, use the target entry's display name (`[Code point](code-point.md)`).
In inline prose, use the lowercase or aliased wording that reads naturally in the sentence (`the work that makes [localization](localization.md) possible`).

### Why it matters:
These are not style preferences; breaking either rule blocks publishing for the whole glossary.
Stating them as conventions, with a validation step, means new and edited entries sync on the first try instead of failing one file at a time.
The display-text split keeps reference lists scannable while keeping prose readable.

### Implementation notes:
Validate before committing: every file's frontmatter parses under a strict YAML loader, no `[[` remains in any body, and every `(slug.md)` link resolves to a real file.
In the initial pass, 819 wiki-links were converted to relative links and two `summary` values were quoted.

### Documented in:
AGENTS.md (GitBook-ready formatting); CONTRIBUTING.md; the entry files in `terms/`.
