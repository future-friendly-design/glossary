---
term: Character
slug: character
aliases: [abstract character]
tags: [characters-encoding]
level: foundational
depth: core
summary: A character is the smallest meaningful unit of written text, like a letter, digit, or punctuation mark.
related: [glyph, code-point, grapheme-cluster, unicode]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Character (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#character
    type: authority
license: CC-BY-4.0
---

## Definition
A character is the smallest meaningful unit of written text, like a letter, digit, or punctuation mark.

## Why it matters
In Unicode terms a character is an abstract unit, not a picture: it is the thing a [code-point](code-point.md) names. The everyday confusion is mixing it up with the [glyph](glyph.md) (the visible shape a font draws for it) or with the bytes it is stored as (the job of a [character-encoding](character-encoding.md)). On top of that, one thing a reader counts as a single character can actually be several Unicode characters combined, which Unicode calls a [grapheme-cluster](grapheme-cluster.md). Keeping these layers straight, character versus glyph versus byte, is what heads off a whole class of text bugs.

## Example
The letter "A", the digit "7", and the comma "," are each one character.

## Related terms
[Glyph](glyph.md) · [Code point](code-point.md) · [Grapheme cluster](grapheme-cluster.md) · [Unicode](unicode.md)

## Further reading
- Foundations: [Character (Unicode Glossary)](https://www.unicode.org/glossary/#character)
