---
term: Combining mark
slug: combining-mark
aliases: [combining character, nonspacing mark]
tags: [characters-encoding]
level: intermediate
depth: core
summary: A combining mark is a code point that attaches to the preceding character, such as an accent.
related: [precomposed-character, diacritic, normalization, grapheme-cluster]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Combining Character (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#combining_character
    type: authority
license: CC-BY-4.0
---

## Definition
A combining mark is a code point that attaches to the preceding character, such as an accent.

## Why it matters
Combining marks have no width of their own; they render on, above, below, or around a base character. A base letter plus one or more combining marks forms a single [grapheme-cluster](grapheme-cluster.md), which is why "one character" on screen can be several code points underneath. The same visible result can often be produced either with a combining mark or with a single [precomposed-character](precomposed-character.md), and that ambiguity is exactly why [normalization](normalization.md) exists.

## Example
"n" followed by U+0303 (combining tilde) displays as "ñ".

## Related terms
[Precomposed character](precomposed-character.md) · [Diacritic](diacritic.md) · [Normalization](normalization.md) · [Grapheme cluster](grapheme-cluster.md)

## Further reading
- Foundations: [Combining Character (Unicode Glossary)](https://www.unicode.org/glossary/#combining_character)
