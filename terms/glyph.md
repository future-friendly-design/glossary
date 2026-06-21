---
term: Glyph
slug: glyph
aliases: []
tags: [characters-encoding]
level: foundational
depth: core
summary: A glyph is the specific visual shape a font draws for a character.
related: [character, font, code-point, ligature]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Unicode Glossary: Glyph"
    url: https://www.unicode.org/glossary/#glyph
    type: authority
license: CC-BY-4.0
---

# Glyph

## Definition
A glyph is the specific visual shape a font draws for a character.

## Why it matters
This is the difference between what text *is* and what text *looks like*. A character, say the lowercase "a", is the abstract unit underneath. The glyph is how one particular font draws that unit. One character can have countless glyphs across different fonts, and sometimes it runs the other way: several characters get drawn as a single glyph (that's a ligature, like the way an "f" and "i" can merge into one shape). It's a handy distinction when you're dealing with fonts, fallbacks, or trying to figure out why a character is showing up as an empty box.

## Example
The lowercase "a" is one character, but a font decides how to draw it. Its glyph looks quite different in a serif typeface (one with small finishing strokes on the letters) than in a sans-serif (one without them).

## Related terms
[Character](character.md) · [Font](font.md) · [Code point](code-point.md) · [Ligature](ligature.md)

## Further reading
- Foundations: [Unicode Glossary: Glyph](https://www.unicode.org/glossary/#glyph)
