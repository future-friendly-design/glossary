---
term: Conjunct
slug: conjunct
aliases:
  - conjunct consonant
  - ligature consonant
level: advanced
depth: core
summary: A conjunct is a combined consonant cluster glyph in Indic scripts, formed when consonants join without a vowel between them.
related:
  - matra
  - reph
  - shirorekha
  - stacking-script
  - complex-text-layout
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

# Conjunct

## Definition

A conjunct is a combined consonant cluster glyph in Indic scripts, formed when consonants join without a vowel between them.

For example, in [Devanagari](../../terms/devanagari.md), क (ka) plus a [virama](virama.md) plus ष (sha) forms the single conjunct क्ष (kṣa).

### Why it matters in design systems

In scripts like Devanagari, when two or more consonants meet with no vowel between them (the absence is marked by a [virama](virama.md), the mark that cancels a consonant's built-in vowel), they merge into a single conjunct form instead of standing as separate letters.<sup>1</sup>

To a font, that merge is drawn by rendering the first consonant in a reduced half-form and attaching the next, sometimes stacking them vertically. A [shaping engine](../../terms/shaping-engine.md) selects which conjuncts form through OpenType rules, and which clusters join is language- and font-dependent.<sup>2</sup>

So for a design system, a font that contains the consonants is necessary but not sufficient. Producing the right conjunct needs the cluster forms and the shaping logic to pick them, which is why conjuncts are a core piece of [complex text layout](../../terms/complex-text-layout.md) and not something an app can fake by placing glyphs in typed order.

***

### Related terms and mentions

[Brahmic scripts](../../terms/brahmic-scripts.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Devanagari](../../terms/devanagari.md) · [Glyph](../../terms/glyph.md) · [Ligature](../../terms/ligature.md) · [Matra](matra.md) · [Reph](reph.md) · [Script rules](script-rules.md) · [Shaping engine](../../terms/shaping-engine.md) · [Shirorekha](shirorekha.md) · [Stacking script](stacking-script.md) · [Virama](virama.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. Consonant conjuncts are ligatures of two or more consonants, formed via the halant (virama) that strips a consonant's inherent vowel - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
2. The Indic shaping engine selects the half-form and conjunct forms through OpenType features, and the set of conjuncts is font-dependent - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
