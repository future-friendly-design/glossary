---
term: Reph
slug: reph
aliases: []
level: advanced
depth: core
summary: >-
  A reph is the form the consonant ra takes when it begins a consonant cluster in
  some Indic scripts, drawn as a small mark above a later consonant instead of as
  a full consonant.
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

A reph is the form the consonant ra takes when it begins a consonant cluster in some Indic scripts, drawn as a small mark above a later consonant instead of as a full consonant.

For example, in Devanagari `कर्म` (karma), the ra that begins the cluster र्म is not drawn as a full consonant but as a small hook-like mark, the reph, sitting above the next consonant ma.<sup>1</sup>

### Why it matters in design systems

A cluster is two or more consonants written together with no vowel between them. When ra is the first consonant of a cluster, a [virama](../language-terms/writing-systems-and-scripts/virama.md) follows it (the mark that removes the default "a" vowel a consonant carries on its own), and another consonant comes after, ra is not drawn in full. The [shaping engine](shaping-engine.md) moves it and replaces it with the reph, a small glyph above the next consonant.<sup>1</sup>

That is the point for a design system. Producing a reph takes both a [glyph](glyph.md) substitution and a move into position, so it is one of the clearest cases of Indic [reordering](reordering.md): the order the [symbols](../language-terms/writing-systems-and-scripts/symbol.md) are stored in is not the order they are drawn in.

So placing [Devanagari](devanagari.md) glyphs in the order they are typed is necessary but not sufficient. A reph only appears correctly when the [font](font.md) carries the reph form and the shaping engine reorders the cluster, which is why [complex text layout](complex-text-layout.md) cannot be done by setting glyphs in stored order.

Reph comes from reordering, one of several [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) a script can have; each language that uses the script also has its own [orthography](../language-terms/writing-systems-and-scripts/orthography.md), its spelling and punctuation conventions.

***

### Related terms and mentions

[Complex text layout](complex-text-layout.md) · [Conjunct](conjunct.md) · [Devanagari](devanagari.md) · [Font](font.md) · [Glyph](glyph.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](reordering.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Shaping engine](shaping-engine.md) · [Shirorekha](../language-terms/writing-systems-and-scripts/shirorekha.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)

### Sources

1. The reph is the above-base form of the consonant "Ra", used when Ra is the first consonant in the syllable and is not the base consonant; the shaping engine reorders the cluster before positioning it - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
