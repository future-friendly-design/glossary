---
term: Diacritic
slug: diacritic
aliases: [diacritical mark, accent]
tags: [characters-encoding]
level: foundational
depth: core
summary: A diacritic is a small mark added to a letter to change its pronunciation or meaning.
related: [mark, tone-mark, combining-mark, precomposed-character, normalization]
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

# Diacritic

## Definition
A diacritic is a small mark added to a letter to change its pronunciation or meaning.

## Why it matters
A diacritic is a kind of [mark](../language-terms/writing-systems-and-scripts/mark.md): it attaches to a letter rather than standing on its own. Placed above, below, or through the letter, it can signal stress, a different vowel sound, or tone, and it can tell apart two words that would otherwise look the same.

For software, the catch is in storage. A computer can hold the same accented letter in more than one way: as a single [precomposed character](precomposed-character.md), or as the plain letter plus a separate [combining mark](combining-mark.md). So `café` can be stored two different ways that look identical on screen. Getting accented text to match and count correctly comes back to [normalization](normalization.md), where the computer rewrites the text into one standard form.

## Example
The cedilla under the `c` in `façade` is a diacritic.

## Related terms
[Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Tone mark](tone-mark.md) · [Combining mark](combining-mark.md) · [Precomposed character](precomposed-character.md) · [Normalization](normalization.md)

## Further reading
- Foundations: [Diacritic (Wikipedia)](https://en.wikipedia.org/wiki/Diacritic)
