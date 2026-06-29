---
term: Conjunct
slug: conjunct
aliases:
  - conjunct consonant
  - ligature consonant
level: advanced
depth: core
summary: >-
  A conjunct is a combined consonant cluster glyph in Indic scripts, formed when
  consonants join without a vowel between them.
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

For example, in [Devanagari](devanagari.md), क (ka) plus a [virama](../language-terms/writing-systems-and-scripts/virama.md) plus ष (sha) forms the single conjunct क्ष (kṣa).

### Why it matters in design systems

In scripts like Devanagari, when two or more consonants meet with no vowel between them (the absence is marked by a [virama](../language-terms/writing-systems-and-scripts/virama.md), the mark that cancels a consonant's built-in vowel), they merge into a single conjunct form instead of standing as separate letters.<sup>1</sup>

To a font, that merge is drawn by rendering the first consonant in a reduced half-form and attaching the next, sometimes stacking them vertically. A [shaping engine](shaping-engine.md) selects which conjuncts form through OpenType rules, and which clusters join is language- and font-dependent.<sup>1</sup>

So for a design system, a font that contains the consonants is necessary but not sufficient. Producing the right conjunct needs the cluster forms and the shaping logic to pick them, which is why conjuncts are a core piece of [complex text layout](complex-text-layout.md) and not something an app can fake by placing glyphs in typed order.

***

### Related terms and mentions

[Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Reph](../language-terms/writing-systems-and-scripts/reph.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Shaping engine](shaping-engine.md) · [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) · [Stacking script](../language-terms/writing-systems-and-scripts/stacking-script.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. A consonant followed by a halant (virama) with no vowel forms a half form or conjunct; the Indic shaping engine selects these forms through OpenType features, and the set of conjuncts is font-dependent - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
