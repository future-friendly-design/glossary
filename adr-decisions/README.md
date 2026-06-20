# Architecture Decisions

The reasoning behind non-obvious decisions in this project, so the "why" survives and settled choices are not relitigated.
Each decision is one numbered file.
A decision is superseded, never deleted; a later record links back to the one it replaces.

These records are for contributors and maintainers.
They are intentionally kept out of `SUMMARY.md`, so they live in the repo but not in the published glossary navigation.

## Template

```markdown
# NNNN. Decision name

**Status:** Accepted          (Proposed | Accepted | Superseded by NNNN)
**Last updated:** YYYY-MM-DD

### What we learned:
The pattern, principle, or choice, stated plainly. For a decision with a real
alternative, name what was rejected and why.

### Why it matters:
The impact on consistency, clarity, or implementation, and how it affects the team
or contributors.

### Implementation notes:
Specifics, edge cases, and examples. What this looks like in practice.

### Documented in:
Where the decision lives or is enforced: a file, a config, a tracker, a tool setting.
```

Prose in these records uses semantic line breaks (one sentence per line); see
[0006](0006-semantic-line-breaks-in-docs.md).

## Records

- [0001. Keep internal process artifacts out of the public repo](0001-internal-artifacts-stay-local.md)
- [0002. LICENSE holds the canonical CC BY 4.0 text; attribution lives in the README](0002-license-canonical-text-attribution-in-readme.md)
- [0003. GitBook Git Sync runs GitHub to GitBook](0003-gitbook-sync-direction.md)
- [0004. GitBook-safe markdown: strict-YAML frontmatter and relative links](0004-gitbook-safe-markdown.md)
- [0005. Agent contributor guidance: AGENTS.md canonical, CLAUDE.md pointer](0005-agents-md-canonical-claude-md-pointer.md)
- [0006. Prose in repo docs uses semantic line breaks](0006-semantic-line-breaks-in-docs.md)
