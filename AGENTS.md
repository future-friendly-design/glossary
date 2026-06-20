# Working in this repo with an AI agent

This file is for contributors using an AI coding assistant (Claude Code or similar).
The human-facing guide is [CONTRIBUTING.md](CONTRIBUTING.md), and it is the source of
truth for the entry format and how to propose or edit a term. Read it first. The notes
below are the operational rules an agent most often gets wrong.

## Source of truth
- Each term is one markdown file under `terms/{slug}.md`; the filename is the slug.
- `terms/*.md` is the content source of truth. Do not rewrite an entry's meaning to make
  an unrelated change.

## Frontmatter must be strict-YAML-safe (the sync depends on it)
This content publishes through GitBook Git Sync, which parses strictly. One malformed
file fails the entire sync, not just that page.
- **Quote any frontmatter value** containing a colon-space (`: `), a leading special
  character (`@ \` # ! & * | > % ?`), or a wrapping quote. Double quotes, escape interior
  `"`. The usual culprit is `summary` (prose, often has a colon).
- **Validate before opening a PR:** every file's frontmatter parses under a strict YAML
  loader, no `[[` remains in any body, and every `(slug.md)` link resolves to a real file.
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
- Use relative markdown links, never Obsidian-style `[[wiki-links]]` (GitBook renders
  those as literal text). Link a sibling entry by filename: `[Display](slug.md)`.
- In the `Key terms` and `Related terms` lists, use the target entry's display name,
  e.g. `[Code point](code-point.md)`. In inline prose, use the wording that reads
  naturally in the sentence, e.g. `the work that makes [localization](localization.md) possible`.

## Accuracy and honesty
- Verify every fact and URL against a primary source before adding it. Prefer Unicode,
  W3C, MDN, type foundries, and recognized references over aggregators.
- If something is uncertain or data-sensitive (speaker counts, endangerment status,
  contested classifications), state the concept plainly and flag it with an
  `<!-- NEEDS EXPERT REVIEW: ... -->` comment rather than asserting a shaky fact.
- Do not attribute a characterization to a named authority unless you have seen that
  authority say it. Otherwise state the property plainly and flag it.
- This is a v0.1 draft under expert review. Do not mark an entry as expert-reviewed or
  published; that is a human decision.

## No em dashes
Use commas, semicolons, colons, or periods.
