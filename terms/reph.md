---
term: Reph
slug: reph
aliases: []
level: advanced
depth: core
summary: >-
  A reph is the special mark form that the consonant "ra" takes when it begins a
  cluster in Indic scripts.
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

A reph is the special mark form that the consonant "ra" takes when it begins a cluster in Indic scripts.

For example, in Devanagari `कर्म` (karma), the "ra" before "ma" is drawn not as a full letter but as a small hook-like mark above the following consonant.

### Why it matters in design systems

When "ra" is the first consonant of a cluster, a syllable-initial ra followed by a [virama](../language-terms/writing-systems-and-scripts/virama.md) (the mark that cancels its inherent vowel), it is not written as a full letter. The shaper moves it to a new position in the cluster and substitutes a small above-base mark in its place.<sup>1</sup>

That is the point for a design system. Producing a reph takes both a glyph substitution and a move into position, so it is one of the clearest cases of Indic [reordering](reordering.md): the order the letters are stored in is not the order they are drawn in.

So placing [Devanagari](devanagari.md) glyphs in the order they are typed is necessary but not sufficient. A reph only appears correctly when the font carries the reph form and the shaper reorders the cluster, which is why [complex text layout](complex-text-layout.md) cannot be done by setting glyphs in stored order.

***

### Related terms and mentions

[Complex text layout](complex-text-layout.md) · [Conjunct](conjunct.md) · [Devanagari](devanagari.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Reordering](reordering.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. The reph is the above-base form of the letter "Ra", used when Ra is the first consonant in the syllable and is not the base consonant; the shaping engine reorders the cluster before positioning it - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
