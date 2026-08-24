---
term: Spacing combining mark
slug: spacing-combining-mark
aliases:
  - spacing mark
level: advanced
depth: core
summary: A spacing combining mark is a character that attaches to the character before it and takes up its own width on the line rather than sitting on top of it.
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

A spacing combining mark is a [character](character.md) that attaches to the character before it and takes up its own width on the line rather than sitting on top of it.

For example, in [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md) the consonant `क` (ka) plus the aa-mark `ा` becomes `का` (kaa); the mark sits to the right and takes its own width.

### Why it matters in design systems

Not every attaching mark hovers over the letter it belongs to. In much of the world's writing, a vowel mark is written beside the consonant, sitting on the line and taking as much room as a letter does. It is still one part of a single written unit, and the computer still stores it as a separate character attached to the one before it, but it is not invisible the way an accent is.

That is the spacing combining mark. The [combining mark](combining-mark.md) entry covers the nonspacing case, marks that add no width and stack on top of a base; this is the second member of [Unicode](unicode.md)'s Mark category, General Category Mc.<sup>1</sup> Unlike a nonspacing mark, it advances the text by its own width, yet it still forms a single unit with its base.<sup>2</sup> These are common in [Brahmic scripts](../../language-terms/writing-systems-and-scripts/brahmic-scripts.md), where many vowel marks ([matra](../../language-terms/writing-systems-and-scripts/matra.md)s) sit beside the consonant and occupy real horizontal space. Knowing the distinction matters because code that assumes "combining means zero width" will mishandle them, and because the base plus its spacing mark count as one [grapheme cluster](grapheme-cluster.md), one unit as far as a reader is concerned, not two.

***

### Related terms and mentions

[Brahmic scripts](../../language-terms/writing-systems-and-scripts/brahmic-scripts.md) · [Character](character.md) · [Combining mark](combining-mark.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Enclosing mark](enclosing-mark.md) · [Grapheme cluster](grapheme-cluster.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [Unicode](unicode.md) · [Writing systems & scripts](../../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Spacing Mark (Unicode Glossary)](https://www.unicode.org/glossary/#spacing_mark)

### Sources

1. Unicode's Mark category (M) splits into nonspacing (Mn), spacing combining (Mc), and enclosing (Me) marks - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
2. A spacing mark is a combining character that is not a nonspacing mark - Unicode Glossary: Spacing Mark [https://www.unicode.org/glossary/#spacing\_mark](https://www.unicode.org/glossary/#spacing_mark)
