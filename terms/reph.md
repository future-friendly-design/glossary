---
term: Reph
slug: reph
aliases: []
tags: [shaping-layout]
level: advanced
depth: core
summary: A reph is the special mark form that the consonant "ra" takes when it begins a cluster in Indic scripts.
related: [conjunct, matra, reordering, shirorekha, virama]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Developing OpenType Fonts for Devanagari Script (Microsoft)"
    url: https://learn.microsoft.com/en-us/typography/script-development/devanagari
    type: authority
license: CC-BY-4.0
---

## Definition
A reph is the special mark form that the consonant "ra" takes when it begins a cluster in Indic scripts.

## Why it matters
When "ra" is the first consonant of a cluster (a syllable-initial ra followed by a [virama](virama.md), the mark that cancels its inherent vowel), it is not written as a full letter. Instead the shaper reorders it to the end of the cluster and draws it as a small hook-like mark above the following consonant. Producing a reph takes both a glyph substitution and a move into position, which makes it one of the clearest examples of Indic [reordering](reordering.md) and why [complex-text-layout](complex-text-layout.md) cannot be done by placing glyphs in typed order.

## Example
In Devanagari "कर्म" (karma), the "ra" before "ma" becomes a reph drawn above it.

## Related terms
[conjunct](conjunct.md) · [matra](matra.md) · [reordering](reordering.md) · [shirorekha](shirorekha.md) · [virama](virama.md)

## Further reading
- Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
