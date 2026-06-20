# 0001. Keep internal process artifacts out of the public repo

**Status:** Accepted
**Last updated:** 2026-06-20

### What we learned:
The working folder held two kinds of files: publishable content (the term entries) and internal process artifacts.
The internal set was early drafts, agent handoff and progress notes, and setup prompts, some carrying internal database IDs and unverified content.
We `.gitignore` the internal set, so only the term entries and the public scaffold are ever committed and pushed.
The alternative, sorting it out later or trusting a manual cleanup, risks a one-time leak that cannot be undone.

### Why it matters:
A public repository is permanent and indexed.
An internal ID or an unreliable draft pushed once is effectively published even if deleted afterward.
Drawing the line at the `.gitignore` boundary keeps the public surface clean, keeps provenance trustworthy, and makes the separation checkable rather than a matter of care.

### Implementation notes:
The ignored set covers the drafts, the handoff and progress notes, the setup prompts, and `.DS_Store`.
Verify both before and after pushing: the staged file list (`git status`) shows no internal file, and the remote tree (`gh api .../git/trees/main`) contains none.
Nothing with an internal ID enters even the public docs (CONTRIBUTING, AGENTS).

### Documented in:
`.gitignore`; CONTRIBUTING.md (what is publishable).
