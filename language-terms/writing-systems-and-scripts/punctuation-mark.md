---
term: Punctuation mark
slug: punctuation-mark
aliases: []
level: foundational
depth: core
summary: >-
  A punctuation mark is a symbol such as a comma, period, or question mark that
  structures written text rather than representing a sound.
related:
  - mark
  - symbol
  - diacritic
  - combining-mark
  - glyph
  - orthography
  - script
  - character
  - unicode
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Standard Annex #44: General Category Values'
    url: https://www.unicode.org/reports/tr44/#General_Category_Values
    type: code
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Punctuation mark

## Definition

A punctuation mark is a [symbol](symbol.md) such as a comma, period, or question mark that structures written text rather than representing a sound.

For example, Spanish opens a question with an inverted `¿` and closes it with `?`.

### Why it matters in design systems

Punctuation shares the word "[mark](mark.md)" but not the sense: unlike a [combining mark](../../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) or a [diacritic](diacritic.md), a punctuation mark does not modify another symbol, it stands alone. The reason it matters: punctuation is genuinely language and script specific, which is easy to forget when English defaults are baked into a product. Which symbols are used, how quotation marks look, whether a question mark is reversed or a sentence-ender is a different [glyph](../../terms/glyph.md): these are part of a language's [orthography](orthography.md), not universal constants. Greek even marks a question with a different symbol, and many scripts have their own quotation conventions, so punctuation is not one fixed set. [Unicode](../../terms/unicode.md), the standard that gives every [character](../../terms/character.md) a number, sorts punctuation into its own group, kept separate from letters and from the marks that attach to other symbols.<sup>1</sup>

***

### Related terms and mentions

[Character](../../terms/character.md) · [Combining mark](../../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) · [Diacritic](diacritic.md) · [Glyph](../../terms/glyph.md) · [Language](../linguistics/language.md) · [Mark](mark.md) · [Orthography](orthography.md) · [Script](script.md) · [Symbol](symbol.md) · [Unicode](../../terms/unicode.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Unicode Standard Annex #44: General Category Values](https://www.unicode.org/reports/tr44/#General_Category_Values)

### Sources

1. Unicode sorts punctuation into its own General Category group (P), separate from letters (L) and marks (M) - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
