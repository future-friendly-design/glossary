---
term: Matra
slug: matra
aliases:
  - dependent vowel
level: advanced
depth: core
summary: A matra is a mark added to a consonant in a Brahmic script to write the vowel that goes with it.
related:
  - mark
  - reordering
  - conjunct
  - reph
  - complex-text-layout
  - abugida
  - brahmic-scripts
  - devanagari
  - unicode
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Devanagari Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/devanagari
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# Matra

## Definition

A matra is a mark added to a consonant in a [Brahmic script](../../terms/brahmic-scripts.md) to write the vowel that goes with it.

For example, the i-matra in [Devanagari](../../terms/devanagari.md) `कि` (ki) is typed after `क` but displays to its left.

### Why it matters in design systems

A matra is a kind of [mark](mark.md): it attaches to a consonant rather than standing on its own. In an [abugida](../../terms/abugida.md) such as Devanagari, each consonant already carries a built-in vowel, and a matra changes it to a different one. A matra can sit to the left, right, above, or below the consonant.

"Matra" is the word from the Devanagari tradition. [Unicode](../../terms/unicode.md) calls the same thing a dependent vowel.<sup>1</sup> Other Brahmic scripts have their own names for it.

For software, the key point is order. A matra is typed after its consonant but may display before it, so the program laying out the text has to move it into the right visual spot. That [reordering](../../programming-terms/reordering.md) is a hallmark of [complex text layout](../../terms/complex-text-layout.md): typed order cannot be assumed to equal display order.<sup>2</sup>

***

### Related terms and mentions

[Abugida](../../terms/abugida.md) · [Brahmic scripts](../../terms/brahmic-scripts.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Conjunct](conjunct.md) · [Devanagari](../../terms/devanagari.md) · [Mark](mark.md) · [Reordering](../../programming-terms/reordering.md) · [Reph](reph.md) · [Script](script.md) · [Symbol](symbol.md) · [Unicode](../../terms/unicode.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. Unicode's neutral term for a matra is "dependent vowel" - Unicode Glossary: Dependent Vowel [https://www.unicode.org/glossary/#dependent\_vowel](https://www.unicode.org/glossary/#dependent_vowel)
2. In Devanagari the i-matra is stored after its consonant but displayed to its left, so it must be reordered for display - Microsoft: Developing OpenType Fonts for Devanagari Script [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
