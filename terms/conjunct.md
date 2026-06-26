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
  - shaping-layout
---

# Conjunct

## Definition

A conjunct is a combined consonant cluster glyph in Indic scripts, formed when consonants join without a vowel between them.

## Why it matters

In scripts like Devanagari, when two or more consonants meet with no vowel between them (the absence is marked by a [virama](virama.md), the sign that cancels a consonant's built-in vowel), they merge into a single conjunct form rather than standing as separate letters. This is often drawn by rendering the first consonant in a reduced "half-form" and attaching the next, sometimes stacking them vertically. A [shaping-engine](shaping-engine.md) selects conjuncts through OpenType rules, and which clusters form conjuncts is language- and font-dependent, so it is a core piece of [complex-text-layout](complex-text-layout.md) rather than something an app can fake.

## Example

In Devanagari, क (ka) + [virama](virama.md) + ष (sha) forms the conjunct क्ष (kṣa).

## Related terms

[Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Reph](reph.md) · [Shirorekha](shirorekha.md) · [Stacking script](stacking-script.md) · [Complex text layout](complex-text-layout.md) · [Virama](virama.md)

## Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
