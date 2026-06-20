---
term: Virama
slug: virama
aliases: [halant, halanta, hasanta, pulli]
tags: [shaping-layout]
level: advanced
depth: core
summary: A virama is a mark in Brahmic scripts that cancels the vowel sound built into a consonant.
related: [conjunct, reph, matra, complex-text-layout]
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
A virama is a mark in Brahmic scripts that cancels the vowel sound built into a consonant.

## Why it matters
In an abugida, each consonant carries an inherent vowel, and the virama (called halant in Hindi) suppresses that vowel to leave a bare consonant. It does double duty in Unicode: placed between two consonants it also acts as the joiner that requests a [[conjunct]] form during shaping. Depending on the font and context it may show as a small visible stroke or be consumed into a combined conjunct shape. That makes the virama the small but pivotal control behind much Indic [[conjunct]] formation and [[reordering]].

## Example
In Devanagari, क (ka) plus virama gives क् (k with no vowel); क् + त then forms the conjunct क्त (kta).

## Related terms
[[conjunct]] · [[reph]] · [[matra]] · [[complex-text-layout]]

## Further reading
- Foundations: [Developing OpenType Fonts for Devanagari Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
