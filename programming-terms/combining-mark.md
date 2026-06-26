---
term: Combining mark
slug: combining-mark
aliases:
  - combining character
level: intermediate
depth: core
summary: >-
  A combining mark is a character that attaches to the one before it, such as an
  accent.
related:
  - mark
  - diacritic
  - precomposed-character
  - normalization
  - grapheme-cluster
  - spacing-combining-mark
  - enclosing-mark
  - unicode
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Combining Character (Unicode Glossary)
    url: https://www.unicode.org/glossary/#combining_character
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Combining mark

## Definition

A combining mark is a character that attaches to the one before it, such as an accent.

For example, the letter `n` followed by a combining tilde displays as `ñ`.

### Why it matters in design systems

A combining mark is how [Unicode](../terms/unicode.md) encodes a [mark](../language-terms/writing-systems-and-scripts/mark.md) that attaches to a base character instead of standing on its own. It is the encoding view of what a reader sees as a [diacritic](../language-terms/writing-systems-and-scripts/diacritic.md): the accent on `ñ` is a diacritic to a person, and a combining mark to the computer.

Unicode's Mark category has three kinds: nonspacing marks that sit on the base without taking width (most accents), [spacing combining marks](spacing-combining-mark.md) that do take width (some Indic vowel marks), and [enclosing marks](enclosing-mark.md) that wrap around the base.<sup>1</sup>

The point that matters for software: the same accented letter can be stored as one [precomposed character](../terms/precomposed-character.md) or as a base letter plus a combining mark, so `ñ` can exist in two forms that look identical. A base plus its combining marks counts as one [grapheme cluster](../terms/grapheme-cluster.md) on screen even though it is several characters underneath, and [normalization](../terms/normalization.md) is what makes the two storage forms compare as equal.<sup>2</sup>

***

### Related terms and mentions

[Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Diacritic](../language-terms/writing-systems-and-scripts/diacritic.md) · [Spacing combining mark](spacing-combining-mark.md) · [Enclosing mark](enclosing-mark.md) · [Precomposed character](../terms/precomposed-character.md) · [Grapheme cluster](../terms/grapheme-cluster.md) · [Normalization](../terms/normalization.md) · [Unicode](../terms/unicode.md)

### Further reading

* Foundations: [Combining Character (Unicode Glossary)](https://www.unicode.org/glossary/#combining_character)

### Sources

1. Unicode's Mark category (M) splits into nonspacing (Mn), spacing combining (Mc), and enclosing (Me) marks - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
2. A precomposed character and a base plus a combining mark are canonically equivalent, and normalization removes the difference for comparison - Unicode Glossary: Canonical Equivalence [https://www.unicode.org/glossary/#canonical\_equivalence](https://www.unicode.org/glossary/#canonical_equivalence)
