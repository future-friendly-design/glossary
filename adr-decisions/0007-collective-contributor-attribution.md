# 0007. Credit contributors collectively, not with per-entry bylines

**Status:** Accepted
**Last updated:** 2026-06-20

### What we learned:
Glossary entries are living, collaborative reference content: one person drafts, another corrects, an expert reviews, and someone fixes a detail later.
A per-entry author byline goes stale as the entry evolves, and it quietly marks the page as owned, which discourages the community edits the project depends on.
So we credit contributors collectively (Git history plus a maintained CONTRIBUTORS page), not with a byline on each entry.
The rejected alternative, an author line per entry, optimizes for individual recognition at the cost of accuracy and openness.

### Why it matters:
The license obligation and community recognition are separate things.
CC BY requires attributing the licensor (Future Friendly Designs Inc.), which the LICENSE and README already handle; it does not require crediting every individual on every page.
Collective credit keeps recognition accurate as entries change, avoids "owned" pages, and gives the contributions that matter most here (the expert reviewers) a single, visible home.

### Implementation notes:
Git history is the authoritative, granular record, and GitBook surfaces a per-page last-modified author from it automatically.
Each entry's `contributors` frontmatter captures the data per entry without rendering a byline.
[CONTRIBUTORS.md](../CONTRIBUTORS.md) recognizes people by name with their consent; it is kept out of `SUMMARY.md` (so unpublished on the GitBook site) until it is populated.
Expert reviewers are credited only with permission.

### Documented in:
[CONTRIBUTORS.md](../CONTRIBUTORS.md); entry `contributors` frontmatter; this record.
