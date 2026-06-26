---
term: Matra
slug: matra
aliases: [dependent vowel sign, vowel sign]
tags: [shaping-layout]
level: advanced
depth: core
summary: A matra is a vowel sign in Indic scripts that attaches to a consonant to show its vowel.
related: [mark, reordering, conjunct, reph, complex-text-layout, abugida, unicode]
status: voice-passed
version_added: 0.1
updated: 2026-06-25
contributors: [sam-gordashko]
further_reading:
  - title: "Developing OpenType Fonts for Devanagari Script (Microsoft)"
    url: https://learn.microsoft.com/en-us/typography/script-development/devanagari
    type: authority
license: CC-BY-4.0
---

# Matra

## Definition

A matra is a vowel sign in Indic scripts that attaches to a consonant to show its vowel.

For example, the i-matra in Devanagari `कि` (ki) is typed after `क` but displays to its left. Unicode names that sign `DEVANAGARI VOWEL SIGN I`.

### Why it matters in design systems

A matra is a kind of [mark](../language-terms/writing-systems-and-scripts/mark.md): a vowel sign that attaches to a consonant rather than standing on its own. In an [abugida](abugida.md) such as Devanagari, each consonant already carries a built-in vowel, and a matra changes it to a different one. A matra can sit to the left, right, above, or below the consonant.

"Matra" is the word from the Devanagari tradition. [Unicode](unicode.md) calls the same thing a dependent vowel, or a "vowel sign" in its character names.<sup>1</sup> Other Brahmic scripts have their own names for it.

For software, the key point is order. A matra is typed after its consonant but may display before it, so the program laying out the text has to move it into the right visual spot. That [reordering](reordering.md) is a hallmark of [complex text layout](complex-text-layout.md): typed order cannot be assumed to equal display order.<sup>2</sup>

***

### Related terms and mentions

[Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Reordering](reordering.md) · [Conjunct](conjunct.md) · [Reph](reph.md) · [Complex text layout](complex-text-layout.md) · [Abugida](abugida.md) · [Unicode](unicode.md)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. Unicode's neutral term for a matra is "dependent vowel"; its character names call these "vowel signs" - Unicode Glossary: Dependent Vowel [https://www.unicode.org/glossary/#dependent_vowel](https://www.unicode.org/glossary/#dependent_vowel)
2. In Devanagari the vowel sign I is stored after its consonant but displayed to its left, so it must be reordered for display - Microsoft: Developing OpenType Fonts for Devanagari Script [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
