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
  - character
  - enclosing-mark
  - matra
  - grapheme-cluster
  - brahmic-scripts
  - devanagari
  - unicode
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
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

A spacing combining mark is a combining [character](../../terms/character.md) that takes up its own horizontal width while still belonging to the base character it attaches to.

For example, in [Devanagari](../../terms/devanagari.md) the consonant `क` (ka) plus the aa-mark `ा` becomes `का` (kaa); the mark sits to the right and takes its own width.

### Why it matters in design systems

The [combining mark](combining-mark.md) entry covers the nonspacing case, marks that add no width and stack on top of a base. The spacing combining mark is the second member of [Unicode](../../terms/unicode.md)'s Mark category, General Category Mc.<sup>1</sup> Unlike a nonspacing mark, it advances the text by its own width, yet it still forms a single unit with its base.<sup>2</sup> These are common in [Brahmic scripts](../../terms/brahmic-scripts.md), where many vowel marks ([matra](../../language-terms/writing-systems-and-scripts/matra.md)s) sit beside the consonant and occupy real horizontal space. Knowing the distinction matters because code that assumes "combining means zero width" will mishandle them, and because the base plus its spacing mark count as one [grapheme cluster](../../terms/grapheme-cluster.md), not two.

***

### Related terms and mentions

[Brahmic scripts](../../terms/brahmic-scripts.md) · [Character](../../terms/character.md) · [Combining mark](combining-mark.md) · [Devanagari](../../terms/devanagari.md) · [Enclosing mark](enclosing-mark.md) · [Grapheme cluster](../../terms/grapheme-cluster.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [Unicode](../../terms/unicode.md) · [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Spacing Mark (Unicode Glossary)](https://www.unicode.org/glossary/#spacing_mark)

### Sources

1. Unicode's Mark category (M) splits into nonspacing (Mn), spacing combining (Mc), and enclosing (Me) marks - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
2. A spacing mark is a combining character that is not a nonspacing mark - Unicode Glossary: Spacing Mark [https://www.unicode.org/glossary/#spacing\_mark](https://www.unicode.org/glossary/#spacing_mark)
