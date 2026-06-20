---
term: Diacritic
slug: diacritic
aliases: [diacritical mark, accent]
tags: [characters-encoding]
level: foundational
depth: core
summary: A diacritic is a small mark added to a letter to change its pronunciation or meaning.
related: [tone-mark, combining-mark, precomposed-character]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Diacritic (Wikipedia)"
    url: https://en.wikipedia.org/wiki/Diacritic
    type: authority
license: CC-BY-4.0
---

## Definition
A diacritic is a small mark added to a letter to change its pronunciation or meaning.

## Why it matters
Placed above, below, or through a letter, diacritics signal things like stress, vowel quality, nasalization, or tone, and they can distinguish otherwise identical words. The encoding twist that matters for software: the same diacritic shape may live as a [[combining-mark]] or as part of a [[precomposed-character]], so "café" can be stored two different ways. That is why handling accented text reliably comes back to [[normalization]].

## Example
The cedilla under the "c" in "façade" is a diacritic.

## Related terms
[[tone-mark]] · [[combining-mark]] · [[precomposed-character]]

## Further reading
- Foundations: [Diacritic (Wikipedia)](https://en.wikipedia.org/wiki/Diacritic)
