# 0005. Agent contributor guidance: AGENTS.md canonical, CLAUDE.md pointer

**Status:** Accepted
**Last updated:** 2026-06-20

### What we learned:
Different AI assistants look for different instruction files: Claude Code reads `CLAUDE.md`, while `AGENTS.md` is the emerging cross-tool standard that other assistants read.
We keep the guidance in `AGENTS.md` as the canonical file and make `CLAUDE.md` a one-line pointer to it, so every assistant finds the same rules.
The alternative, maintaining the content in `CLAUDE.md` alone, would have left non-Claude tools without guidance.

### Why it matters:
Contributors increasingly use AI assistants, and an assistant without the operational rules will reintroduce the exact issues this project just fixed: unsafe frontmatter, wiki-links, asserting unverified facts.
Giving every agent the rules, regardless of tool, protects the content quality at the point where edits are actually made.
The file defers to CONTRIBUTING.md for the human-facing format and carries no internal IDs.

### Implementation notes:
`AGENTS.md` holds the rules: GitBook-safe formatting, verify-and-flag accuracy, status caps, and a pointer to `skill.md` for GitBook custom-block syntax.
`CLAUDE.md` is a single line pointing to `AGENTS.md`.
Both are public-clean.

### Documented in:
AGENTS.md; CLAUDE.md.
