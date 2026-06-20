---
term: Tsheg
slug: tsheg
aliases: [tsek, syllable dot]
tags: [shaping-layout]
level: intermediate
depth: core
summary: The tsheg is a small dot used in Tibetan script to separate syllables.
related: [complex-text-layout, stacking-script]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Requirements for Tibetan Text Layout (W3C)"
    url: https://www.w3.org/TR/tlreq/
    type: authority
license: CC-BY-4.0
---

## Definition
The tsheg is a small dot used in Tibetan script to separate syllables.

## Why it matters
Tibetan does not put spaces between words. Instead a tsheg (U+0F0B) marks the boundary between syllables, and the unit of text between two tshegs is called a tsheg-bar. Because many Tibetan words are a single syllable, the tsheg often behaves much like a space, which makes it important for finding line-break and reading boundaries. A non-breaking variant exists at U+0F0C, so line-breaking logic has to treat the two differently.

## Example
The dot between syllables in Tibetan "བོད་ཡིག" is a tsheg.

## Related terms
[complex-text-layout](complex-text-layout.md) · [stacking-script](stacking-script.md)

## Further reading
- Foundations: [Requirements for Tibetan Text Layout (W3C)](https://www.w3.org/TR/tlreq/)
