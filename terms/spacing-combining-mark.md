---
term: Spacing combining mark
slug: spacing-combining-mark
aliases:
  - spacing mark
level: advanced
depth: core
summary: >-
  A spacing combining mark is a combining character that takes up its own
  horizontal width while still belonging to the base character it attaches to.
related:
  - combining-mark
  - mark
  - enclosing-mark
  - matra
  - grapheme-cluster
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Spacing Mark (Unicode Glossary)
    url: https://www.unicode.org/glossary/#spacing_mark
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Spacing combining mark

## Definition

A spacing combining mark is a combining character that takes up its own horizontal width while still belonging to the base character it attaches to.

## Why it matters

The [combining mark](combining-mark.md) entry covers the nonspacing case, marks that add no width and stack on top of a base. The spacing combining mark is the second member of Unicode's Mark category, General Category Mc. Unlike a nonspacing mark, it advances the text by its own width, yet it still forms a single unit with its base. These are common in [Brahmic scripts](brahmic-scripts.md), where many vowel signs ([matra](matra.md)s) sit beside the consonant and occupy real horizontal space. Knowing the distinction matters because code that assumes "combining means zero width" will mishandle them, and because the base plus its spacing mark count as one [grapheme cluster](grapheme-cluster.md), not two.

## Example

A Devanagari consonant followed by a right-side vowel sign forms one unit, but the vowel sign occupies its own width, which makes it a spacing combining mark rather than a nonspacing one.

## Related terms

[Combining mark](combining-mark.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Enclosing mark](enclosing-mark.md) · [Matra](matra.md) · [Grapheme cluster](grapheme-cluster.md)

## Further reading

* Foundations: [Spacing Mark (Unicode Glossary)](https://www.unicode.org/glossary/#spacing_mark)
