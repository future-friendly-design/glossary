# Contributing

Thank you for helping improve the Future Friendly Glossary.
This is a v0.1 draft under expert review, so corrections and fact-checks are especially valuable, above all from people who speak, write, and work with the languages and scripts covered here.

There are two ways to help:

- **Propose a correction or edit** to an existing term.
  Open an issue, or edit the term's file and open a pull request.
- **Propose a new term.**
  Open an issue describing the term and why it belongs, or draft the entry following the format below and open a pull request.

## How terms are organized

Each term is its own markdown file under [`terms/`](terms/).
The filename is the term's **slug** (lowercase, hyphenated): `line-height.md`, `grapheme-cluster.md`.
The slug is permanent, so it can be linked to as a stable address.
One concept, one file.

A term belongs to one or more of seven categories (typography; characters & encoding; shaping & layout; internationalization; reference sources; writing systems & scripts; language & linguistics).
Each category also has an **overview** entry that introduces the area and links its member terms.

## Entry format

An entry has two parts: machine-readable frontmatter at the top, then the human-readable body.

### Frontmatter

```yaml
---
term: Line height            # canonical display name
slug: line-height            # equals the filename, lowercase and hyphenated
aliases: []                  # other names for the same thing; [] if none
tags: [typography]           # broader concepts this term is "about"
level: foundational          # foundational | intermediate | advanced
depth: deep                  # core | deep (see "Two depths" below)
summary: >                   # one standalone sentence; this is the Definition
  Line height is the distance from one baseline to the next in a block of text.
related: [leading, baseline] # peer terms, by slug
status: drafted              # drafted | voice-passed | expert-reviewed | published
further_reading:             # typed list; see "Further reading" below
  - title: "line-height (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/line-height
    type: code
license: CC-BY-4.0
---
```

**Tags and related must be defined terms.**
Both `tags` and `related` point to other entries by slug.
If you want to tag or relate a term to a concept that does not yet have its own entry, note it in your pull request so it can be added rather than left dangling.

### Body

Sections run in this fixed order.
The first three plus the two closing sections are on every entry; the last two ("Common mistake" and "In practice") are added only for **deep** entries that have real practitioner value to add.

```markdown
## Definition
One or two sentences. Neutral, self-contained, and quotable. Matches `summary`.

## Why it matters
Where this shows up in real design or engineering work and why a practitioner cares.

## Example
Concrete and specific. Briefly gloss any jargon you name.

## Also called          (only when a design tool or spec has its own name for it)
What tools and specs call this, e.g. "Figma: Line height. CSS: line-height."

## Common mistake        (deep entries only)
The pitfall practitioners actually hit.

## In practice           (deep entries only)
What this means for the reader's work: connections to design tools, design tokens,
accessibility, and language or script support. Link a source that shows it, not just
tells it.

## Related terms         (every entry)
Links to the related terms.

## Further reading        (every entry)
The typed source links from frontmatter, rendered out.
```

**Related terms** and **Further reading** are mandatory on every entry.
An entry without them is incomplete.

### Two depths

- **core** has Definition, Why it matters, Example, and Also called where it applies.
  This is enough: a core entry is complete and lookup-ready.
- **deep** adds Common mistake and In practice.
  Use it only when there is genuine practitioner value to add (a tool or token connection, an accessibility or language consideration, a real pitfall).
  Do not pad the deep sections with filler.

### Further reading

Keep it curated, not exhaustive: at most one link per type, and only types that genuinely apply.
Not every term has a code or design-tool source, and that is fine.
Never invent a link, and never add a generic hub as filler; an empty slot beats a forced one.
The types:

| `type`        | Covers                          | Rendered label    |
|---------------|---------------------------------|-------------------|
| `code`        | implementation and specs        | Code & specs      |
| `design-tool` | design-tool documentation       | Design tools      |
| `authority`   | the subject-matter side         | Foundations       |
| `resource`    | a curated guide, talk, or book  | Resource library  |

Cite verifiable primary sources (Unicode, W3C, MDN, type foundries, recognized typography references) over aggregators.
Verify that every URL resolves before adding it.

## Writing rules

- **Self-contained.** Every entry should answer the question read cold, with nothing around it.
  Do not assume the reader knows referenced jargon; gloss it in a few words or link it.
  "Helvetica, a sans-serif typeface" beats a bare "Helvetica."
- **Reader-value voice.** Frame guidance as "what this means for your work," not "what I do."
  Warm and plain, but not a personal diary.
- **Show, don't just tell.** When a section describes doing something in a tool, link a source that demonstrates it.
- **Concrete over vague.** "45 to 75 characters" beats "a comfortable line length."
- **No em dashes.** Use commas, semicolons, colons, or periods.
- **Be honest about status.** Do not mark a term beyond what has actually been verified.

## Status pipeline

The `status` field tracks how far an entry has come:

```
drafted  ->  voice-passed  ->  expert-reviewed  ->  published
```

Most entries are currently at `drafted` or `voice-passed`.
`expert-reviewed` means a subject-matter expert has checked the facts.
Only `published` is safe to treat as final.

## Why things are the way they are

The reasoning behind non-obvious project decisions (licensing, how the content is formatted for GitBook, how cross-references work) is recorded as short decision records in [`adr-decisions/`](adr-decisions/).
If you are wondering why a convention exists before proposing a change to it, start there.

## License

By contributing, you agree that your contributions are licensed under [CC BY 4.0](LICENSE), the same license as the rest of the project.
