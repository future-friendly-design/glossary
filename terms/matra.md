---
term: Matra
slug: matra
aliases: [dependent vowel sign, vowel sign]
tags: [shaping-layout]
level: advanced
depth: core
summary: A matra is a vowel sign in Indic scripts that attaches to a consonant to show its vowel.
related: [reordering, conjunct, reph, complex-text-layout]
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
A matra is a vowel sign in Indic scripts that attaches to a consonant to show its vowel.

## Why it matters
In abugida scripts like Devanagari, a consonant carries an inherent vowel and a matra modifies it. Matras can sit to the left, right, above, or below the base consonant. The point that matters most for software: a matra typed after its consonant in logical order may display before it, so the shaper has to move it into the correct visual position. That [[reordering]] is a hallmark of [[complex-text-layout]] and a reason typed order cannot be assumed to equal display order.

## Example
The i-matra in Devanagari "कि" (ki) is typed after क but displays to its left.

## Related terms
[[reordering]] · [[conjunct]] · [[reph]] · [[complex-text-layout]]

## Further reading
- Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
