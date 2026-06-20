# 0003. GitBook Git Sync runs GitHub to GitBook

**Status:** Accepted
**Last updated:** 2026-06-20

### What we learned:
GitBook Git Sync is one-directional on the first synchronization.
With a populated repo and an empty GitBook space, the "GitBook to GitHub" direction would have overwritten the repo with the empty space content.
We chose "GitHub to GitBook", so content flows from Git into the space and Git stays the source of truth.
The rejected alternative, authoring in GitBook and pushing out, would have made GitBook a second source that drifts from the repo.

### Why it matters:
The repository is the canonical store: one file per term, versioned, diffable, and reviewable through pull requests.
Making GitBook the downstream consumer keeps authoring and history in Git, keeps contributions flowing through PRs, and prevents two competing sources of truth.

### Implementation notes:
Initial sync direction is GitHub to GitBook; the project directory is the repo root; the branch is `main`.
Re-confirm the direction on any re-link, since the default can flip.
`SUMMARY.md` drives the published navigation.

### Documented in:
The GitBook space Git Sync settings (external); this decisions log; the `setup-gitbook-project` setup procedure.
