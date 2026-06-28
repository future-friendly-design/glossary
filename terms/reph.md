---
term: Reph
slug: reph
aliases: []
level: advanced
depth: core
summary: >-
  A reph is the form the consonant ra takes when it begins a consonant cluster
  in some Indic scripts, drawn as a small mark above a later consonant instead
  of as a full consonant.
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

In some South Asian (Indic) Brahmic scripts, a reph is the above-base form the consonant ra takes when it is the initial symbol in a consonant cluster (two or more consonants that come together with no vowel between them).<sup>1</sup> It's a common example of a script's reordering rule in action.

For example, in Devanagari `कर्म` (karma), the ra that begins the cluster र्म is not drawn as a full consonant but as a small hook-like shape, the reph, sitting above the next consonant, ma.<sup>2</sup>

### Why it matters in design systems

On a multi-language website, a Devanagari word is stored in the order its characters are typed (क, र, virama, म), but it is not shown in that order: the reph moves up to sit above म. So a design system supporting Devanagari can't treat the stored order of text as the displayed order of text.

Displaying a reph correctly on a website requires both a font that includes the reph form of the ra symbol and a shaping engine that performs the glyph substitution and reorders the cluster of symbols to position the reph.

It's important to remember that supporting another language in a design system isn't limited to translation. Some writing systems have script rules, such as reordering (reph is one example), joining, and stacking, that require the system to handle complex text layout, not just translated strings. Even among languages that share the same script, each adds its own language-specific rules, defined in its orthography, that can place further requirements on the design system.

***

### Related terms and mentions

[Complex text layout](complex-text-layout.md) · [Conjunct](conjunct.md) · [Devanagari](devanagari.md) · [Font](font.md) · [Glyph](glyph.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](reordering.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Shaping engine](shaping-engine.md) · [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. In Devanagari and other scripts of India, the above-base form of RA used at the start of a cluster is a nonspacing combining-mark glyph form of the consonant RA, also known as "repha"; the same cluster-initial RA behaviour occurs in Bengali, Telugu, and Kannada - The Unicode Standard, Version 16.0, Chapter 12 (South Asia-I) [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
2. The reph is the above-base form of the consonant "Ra", used when Ra is the first consonant in the syllable and is not the base consonant; the shaping engine reorders the cluster before positioning it - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
