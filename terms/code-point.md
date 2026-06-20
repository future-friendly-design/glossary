---
term: Code point
slug: code-point
aliases: [codepoint]
tags: [characters-encoding]
level: foundational
depth: core
summary: A code point is the number Unicode assigns to a character.
related: [character, unicode, character-encoding, plane-bmp]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Code Point (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#code_point
    type: authority
license: CC-BY-4.0
---

## Definition
A code point is the number Unicode assigns to a character.

## Why it matters
A code point is a position in the Unicode code space, written as "U+" followed by hexadecimal digits, from U+0000 to U+10FFFF. Code points are assigned to abstract [character](character.md)s; they are not the bytes stored on disk (that is the job of a [character-encoding](character-encoding.md)) and not the visible [glyph](glyph.md)s a font draws. Worth knowing: not every code point is a printable character. Some are control codes, and some are reserved or unassigned.

## Example
The character "A" is code point U+0041; the snowman "☃" is U+2603.

## Related terms
[character](character.md) · [unicode](unicode.md) · [character-encoding](character-encoding.md) · [plane-bmp](plane-bmp.md)

## Further reading
- Foundations: [Code Point (Unicode Glossary)](https://www.unicode.org/glossary/#code_point)
