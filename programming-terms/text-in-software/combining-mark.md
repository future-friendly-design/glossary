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
  - character
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

A combining mark is a [character](character.md) that attaches to the one before it, such as an accent.

For example, the letter `n` followed by a combining tilde displays as `ñ`.

### Why it matters in design systems

Writing all over the world builds one written unit out of a base plus something added to it: the tilde over `ñ`, the accent over `é`, a vowel mark placed beside a consonant. A computer has two ways to store a unit like that. It can treat the whole thing as a single character. Or it can store two characters, the base and the added piece, and rely on them being read together.

A combining mark is that second, added piece. It is a character that cannot stand on its own: it exists only to attach to the character before it, which is called the base. What a reader sees as a [diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md), a [mark](../../language-terms/writing-systems-and-scripts/mark.md) added to a letter, the computer may be holding as a base character followed by a combining mark.

[Unicode](unicode.md) sorts these attaching characters into three kinds: nonspacing marks, which sit on the base without taking any width of their own (most accents); [spacing combining marks](spacing-combining-mark.md), which do take width (some Indic vowel marks); and [enclosing marks](enclosing-mark.md), which wrap around the base.<sup>1</sup>

The point that matters for software: the same accented letter can be stored either way, as one [precomposed character](precomposed-character.md) or as a base letter plus a combining mark, so `ñ` can exist in two forms that look identical on screen and are not identical underneath.<sup>2</sup> A base plus its combining marks counts as one [grapheme cluster](grapheme-cluster.md), one unit as far as a reader is concerned, even though it is several characters underneath.<sup>3</sup> [Normalization](normalization.md), rewriting text so that both storage forms come out the same way, is what makes them compare as equal.<sup>4</sup>

***

### Related terms and mentions

[Brahmic scripts](../../language-terms/writing-systems-and-scripts/brahmic-scripts.md) · [Character](character.md) · [Diacritic](../../language-terms/writing-systems-and-scripts/diacritic.md) · [Enclosing mark](enclosing-mark.md) · [Grapheme cluster](grapheme-cluster.md) · [Mark](../../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../../language-terms/writing-systems-and-scripts/matra.md) · [Normalization](normalization.md) · [Precomposed character](precomposed-character.md) · [Script rules](../../language-terms/writing-systems-and-scripts/script-rules.md) · [Spacing combining mark](spacing-combining-mark.md) · [Unicode](unicode.md) · [Text in software](./)

### Further reading

* Foundations: [Combining Character (Unicode Glossary)](https://www.unicode.org/glossary/#combining_character)

### Sources

1. Unicode's Mark category (M) splits into nonspacing (Mn), spacing combining (Mc), and enclosing (Me) marks - Unicode Standard Annex #44: General Category Values [https://www.unicode.org/reports/tr44/#General\_Category\_Values](https://www.unicode.org/reports/tr44/#General_Category_Values)
2. Canonical equivalence is the relation between characters or sequences of characters that represent the same abstract character and that, when correctly displayed, should always look and behave the same; the first example given is a single character and its combining sequence - Unicode Standard Annex #15: Unicode Normalization Forms, section 1.1 [https://www.unicode.org/reports/tr15/#Canon\_Compat\_Equivalence](https://www.unicode.org/reports/tr15/#Canon_Compat_Equivalence)
3. A base followed by its combining marks (a combining character sequence) is listed as a grapheme cluster under both the legacy and the extended rules; extended grapheme clusters, the default, also take in spacing marks - Unicode Standard Annex #29: Unicode Text Segmentation [https://www.unicode.org/reports/tr29/#Grapheme\_Cluster\_Boundaries](https://www.unicode.org/reports/tr29/#Grapheme_Cluster_Boundaries)
4. Normalization is a process of removing alternate representations of equivalent sequences from text, converting it into a form that can be binary-compared for equivalence - Unicode Glossary: Normalization [https://www.unicode.org/glossary/#normalization](https://www.unicode.org/glossary/#normalization)
