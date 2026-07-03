---
term: Reph
slug: reph
aliases: []
level: advanced
depth: core
summary: >-
  In some South Asian (Indic) Brahmic scripts, a reph is the above-base form the
  consonant ra takes when it is the initial symbol in a consonant cluster.
related:
  - conjunct
  - matra
  - reordering
  - shirorekha
  - virama
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Devanagari Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/devanagari
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Reph

## Definition

In some South Asian (Indic) Brahmic scripts, a reph is the above-base form the consonant ra takes when it is the initial symbol in a consonant cluster.<sup>1</sup> A cluster is two or more consonants that come together with no vowel between them. It's a common example of a script's [reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) rule in action.

For example, in [Devanagari](../../terms/devanagari.md) `कर्म` (karma), the ra that begins the cluster र्म is not drawn as a full consonant but as a small hook-like shape, the reph, sitting above the next consonant, ma.<sup>2</sup>

### Why it matters in design systems

On a multi-language website, a Devanagari word is stored in the order its [characters](../../terms/character.md) are typed (क, र, [virama](virama.md), म), but it is not shown in that order: the reph moves up to sit above म. So a design system supporting Devanagari can't treat the stored order of text as the displayed order of text.

Displaying a reph correctly on a website requires both a [font](../../terms/font.md) that includes the reph form of the ra symbol and a [shaping engine](../../terms/shaping-engine.md) that performs the [glyph](../../terms/glyph.md) substitution and reorders the cluster of [symbols](symbol.md) to position the reph.

It's important to remember that supporting another language in a design system isn't limited to translation. Some [writing systems](writing-system.md) have [script rules](script-rules.md), such as reordering (reph is one example), [joining](joining.md), and [stacking](stacking-script.md), that require the system to handle [complex text layout](../../terms/complex-text-layout.md), not just translated strings. Even among languages that share the same script, each adds its own language-specific rules, defined in its [orthography](orthography.md), that can place further requirements on the design system.

***

### Related terms and mentions

[Character](../../terms/character.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Conjunct](conjunct.md) · [Devanagari](../../terms/devanagari.md) · [Font](../../terms/font.md) · [Glyph](../../terms/glyph.md) · [Joining](joining.md) · [Matra](matra.md) · [Orthography](orthography.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script rules](script-rules.md) · [Shaping engine](../../terms/shaping-engine.md) · [Shirorekha](shirorekha.md) · [Stacking script](stacking-script.md) · [Symbol](symbol.md) · [Virama](virama.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. In Devanagari and other scripts of India, the above-base form of RA used at the start of a cluster is a nonspacing combining-mark glyph form of the consonant RA, also known as "repha"; the same cluster-initial RA behaviour occurs in Bengali, Telugu, and Kannada - The Unicode Standard, Version 16.0, Chapter 12 (South Asia-I) [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
2. The reph is the above-base form of the consonant "Ra", used when Ra is the first consonant in the syllable and is not the base consonant; the shaping engine reorders the cluster before positioning it - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
