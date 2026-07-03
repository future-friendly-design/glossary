# Working in this repo with an AI agent

This file is for contributors using an AI coding assistant (Claude Code or similar).
The human-facing guide is [CONTRIBUTING.md](CONTRIBUTING.md), and it is the source of truth for the entry format and how to propose or edit a term.
Read it first.
The notes below are the operational rules an agent most often gets wrong.

## Source of truth
- Each term is one markdown file under `terms/{slug}.md`; the filename is the slug.
- `terms/*.md` is the content source of truth.
  Do not rewrite an entry's meaning to make an unrelated change.
- Layout is hybrid: most entries are flat in `terms/`, but reviewed linguistic clusters move into topic subfolders (for example `language-terms/writing-systems-and-scripts/`) with a `README.md` landing page; see [adr-decisions/0011](adr-decisions/0011-linguistic-clusters-as-dedicated-sections.md) and `agent-progress-handover.md`.
  The slug stays stable when a file moves.

## Frontmatter must be strict-YAML-safe (the sync depends on it)
This content publishes through GitBook Git Sync, which parses strictly.
One malformed file fails the entire sync, not just that page.
- **Quote any frontmatter value** containing a colon-space (`: `), a leading special character (`@ \` # ! & * | > % ?`), or a wrapping quote.
  Double quotes, escape interior `"`.
  The usual culprit is `summary` (prose, often has a colon).
- **Author frontmatter values on one line** (especially `summary`).
  Note: GitBook itself re-folds `summary` into a `>-` block scalar on every editor save, and those pages render and register fine, so a folded `>-` summary is harmless and not worth chasing (flattening it just gets undone on the next GitBook edit).
  What to still avoid is a genuinely multi-line *literal* (`|`) value or a folded value that a strict YAML loader can't parse; keep the value semantically single-line.
- **Validate before opening a PR:** every file's frontmatter parses under a strict YAML loader, no `[[` remains in any body, and every `(slug.md)` link resolves to a real file.
  ```bash
  python3 - <<'PY'
  import glob, re, os, yaml
  files={os.path.basename(p) for p in glob.glob("terms/*.md")}
  for p in glob.glob("terms/*.md"):
      s=open(p,encoding="utf-8").read()
      try: yaml.safe_load(s[3:s.find(chr(10)+'---',3)])
      except Exception as e: print("YAML FAIL", p, e)
      if "[[" in s: print("WIKILINK LEFT", p)
      for m in re.finditer(r'\]\(([a-z0-9-]+\.md)\)', s):
          if m.group(1) not in files: print("BROKEN LINK", p, m.group(1))
  PY
  ```

## Links between entries
- Use relative markdown links, never Obsidian-style `[[wiki-links]]` (GitBook renders those as literal text).
  Link a sibling entry by filename: `[Display](slug.md)`.
- In the `Key terms` and `Related terms` lists, use the target entry's display name, e.g. `[Code point](code-point.md)`.
  In inline prose, use the wording that reads naturally in the sentence, e.g. `the work that makes [localization](localization.md) possible`.

## GitBook syntax (custom blocks)
Entries are plain markdown today.
If you add GitBook custom blocks (hints, tabs, cards, content-refs, includes) or touch `.gitbook.yaml` / `SUMMARY.md` config, read `skill.md` in the repo root for the correct GitBook-flavored syntax before authoring them.

> Maintainers: `skill.md` is GitBook's official, maintained syntax reference.
> Keep a copy committed in the repo root and refresh it from GitBook's docs (https://gitbook.com/docs/creating-content/ai-coding-assistants-and-skillmd) when GitBook ships new block types.
> Do not hand-write or paraphrase it; the file stays verbatim, so this note carries the date instead.
> Last refreshed: 2026-06-20.

- **Content-ref cards re-bind on edit, not on every git change.**
  When you edit a term file that a content-ref card points to, the card may show "Broken link" in GitBook's synced/view mode until GitBook re-resolves; opening the edit branch or re-syncing fixes it.
  The file is not broken, so do not chase it with commits.
  For sync-proof cross-references, plain relative markdown links resolve by path with no page-binding to go stale.

## Accuracy and honesty
- Verify every fact and URL against a primary source before adding it.
  Prefer Unicode, W3C, MDN, type foundries, and recognized references over aggregators.
- If something is uncertain or data-sensitive (speaker counts, endangerment status, contested classifications), state the concept plainly and flag it with an `<!-- NEEDS EXPERT REVIEW: ... -->` comment rather than asserting a shaky fact.
- Do not attribute a characterization to a named authority unless you have seen that authority say it.
  Otherwise state the property plainly and flag it.
- This is a v0.1 draft under expert review.
  Do not mark an entry as expert-reviewed or published; that is a human decision.

## Tracker relationships (Airtable)
The tracker records how terms relate, using two structures that must stay separate; see [adr-decisions/0010](adr-decisions/0010-term-relationships-is-a-tree-vs-faceted-groupings.md).
Parent/Child in the Terms table is a single nesting hierarchy: a term's parent is what it is nested under, one parent per term (Cyrillic under Alphabet under Script; Ethnologue under Language). This is broader/narrower in the thesaurus sense, usually "is a kind of" but also "belongs under / is scoped to".
The Groupings table holds faceted, cross-cutting views of the same terms (anatomy, rules, classifications, examples, reference/measurement); a term can be in several, and a grouping can pull terms from any topic.
Do not tangle the two: classifications, parts, and instances are facets (Groupings), not parent edges.
The Airtable field descriptions carry the short version of these rules.
Entry-structure exceptions (disambiguation hubs may swap the middle beats for custom sections) are in [adr-decisions/0009](adr-decisions/0009-disambiguation-hub-entries-may-use-custom-sections.md).

## Prose wrapping
Docs in this repo use semantic line breaks (one sentence per line); see [adr-decisions/0006](adr-decisions/0006-semantic-line-breaks-in-docs.md).

## No em dashes
Use commas, semicolons, colons, or periods.
