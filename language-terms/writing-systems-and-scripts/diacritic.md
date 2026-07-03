---
term: Diacritic
slug: diacritic
aliases:
  - diacritical mark
  - accent
level: foundational
depth: core
summary: A diacritic is a small mark added to a symbol to change its pronunciation or meaning.
related:
  - mark
  - tone-mark
  - combining-mark
  - character
  - precomposed-character
  - normalization
  - font
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Diacritic (Wikipedia)
    url: https://en.wikipedia.org/wiki/Diacritic
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Diacritic

## Definition

A diacritic is a small mark added to a symbol to change its pronunciation or meaning.<sup>1</sup>

For example, the cedilla mark under the `c` in `façade` is a diacritic.

### Why it matters in design systems

A diacritic is a kind of [mark](mark.md), it attaches to a [symbol](symbol.md) within a [script](script.md) rather than standing on its own. Placed above, below, or through the symbol, it can signal stress, a different vowel sound, or [tone](tone-mark.md), and it can tell apart two words that would otherwise look the same.

Like all marks, when a diacritic is added to a symbol, the individual piece of text takes up more space. When working with digital text, [fonts](../../terms/font.md) supporting symbols with diacritic marks may require larger [line height](../../terms/line-height.md) values to avoid clipping.

For software, there are known issues with the way accented text is stored. [Unicode](../../terms/unicode.md), the standard that gives every [character](../../terms/character.md) (their term for a symbol) a unique number, describes accented text as being stored as a [precomposed character](../../terms/precomposed-character.md), or as the plain letter plus a separate [combining mark](../../programming-terms/combining-mark.md).

So `café` can be stored two different ways that look identical on screen. Getting accented text to match and count correctly comes back to [normalization](../../terms/normalization.md), where the computer rewrites the text into one standard form.<sup>2</sup>

***

### Related terms and mentions

[Character](../../terms/character.md) · [Combining mark](../../programming-terms/combining-mark.md) · [Font](../../terms/font.md) · [Line height](../../terms/line-height.md) · [Mark](mark.md) · [Normalization](../../terms/normalization.md) · [Precomposed character](../../terms/precomposed-character.md) · [Script](script.md) · [Symbol](symbol.md) · [Tone mark](tone-mark.md) · [Unicode](../../terms/unicode.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Diacritic (Wikipedia)](https://en.wikipedia.org/wiki/Diacritic)

### Sources

1. Unicode defines a diacritic as a mark applied to a symbol, not only a letter - Unicode Glossary: Diacritic [https://www.unicode.org/glossary/#diacritic](https://www.unicode.org/glossary/#diacritic)
2. Normalization is a process of removing alternate representations of equivalent sequences from text, converting it into a form that can be binary-compared for equivalence - Unicode Glossary: Normalization [https://www.unicode.org/glossary/#normalization](https://www.unicode.org/glossary/#normalization)
