---
term: Virama
slug: virama
aliases:
  - halant
  - halanta
  - hasanta
  - pulli
level: advanced
depth: core
summary: >-
  A virama is a mark in Brahmic scripts that cancels the vowel sound built into
  a consonant.
related:
  - mark
  - conjunct
  - reph
  - matra
  - complex-text-layout
  - abugida
  - devanagari
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

# Virama

## Definition

A virama is a mark in Brahmic scripts that cancels the vowel sound built into a consonant.

For example, in [Devanagari](devanagari.md) `क` (ka) plus a virama gives `क्` (a bare k); `क्` plus `त` (ta) then forms the conjunct `क्त` (kta).

### Why it matters in design systems

A virama is a kind of [mark](../language-terms/writing-systems-and-scripts/mark.md). In an [abugida](abugida.md), each consonant carries a built-in vowel, and the virama (called halant in Hindi) strips that vowel to leave a bare consonant. It also does double duty: placed between two consonants, it asks the shaping software to join them into a [conjunct](conjunct.md) form.<sup>1</sup> Depending on the font and context, the virama may show as a small visible stroke or be absorbed into the combined conjunct shape. That makes it the small but pivotal control behind much Devanagari conjunct formation and [reordering](reordering.md).

***

### Related terms and mentions

[Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Abugida](abugida.md) · [Conjunct](conjunct.md) · [Reph](reph.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. The halant (virama) is the character used after a consonant to strip it of its inherent vowel, and Consonant + Halant sequences drive conjunct (half-form or ligature) formation during shaping - Microsoft: Developing OpenType Fonts for Devanagari Script [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
