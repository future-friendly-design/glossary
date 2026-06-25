---
term: Grapheme
slug: grapheme
aliases: []
level: intermediate
depth: core
summary: >-
  A grapheme is the smallest unit of a writing system that distinguishes
  meaning, such as a letter, a digit, or a punctuation mark.
related:
  - grapheme-cluster
  - glyph
  - character
  - code-point
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Grapheme (Unicode Glossary)
    url: https://www.unicode.org/glossary/#grapheme
    type: authority
license: CC-BY-4.0
tags:
  - language-linguistics
---

# Grapheme

## Definition

A grapheme is the smallest unit of a writing system that distinguishes meaning, such as a letter, a digit, or a punctuation mark. TEST

## Why it matters

A grapheme is the abstract "letter": the unit a writing system treats as meaningfully distinct, the way a phoneme is the unit of sound. It is worth separating from three things it gets confused with. A [glyph](../../terms/glyph.md) is how a grapheme is drawn, and one grapheme can have many glyphs (the same "a" across fonts, or a letter's initial and final forms). A [character](../../terms/character.md) in Unicode is a [code point](../../terms/code-point.md), and graphemes do not map to code points one to one: the single grapheme "é" can be one code point or two (an "e" plus a combining accent). Because of that gap, Unicode uses [grapheme cluster](../../terms/grapheme-cluster.md) for what a reader perceives as one character. Keeping grapheme (the unit of writing), glyph (the drawn shape), and code point (the stored value) distinct is what prevents the classic counting and rendering bugs.

## Example

The letter "b" is one grapheme; it can be set in countless glyphs across typefaces, and in Unicode it is a single code point. The accented "é" is also one grapheme, but it can be stored as two code points.

## Related terms

[Grapheme cluster](../../terms/grapheme-cluster.md) · [Glyph](../../terms/glyph.md) · [Character](../../terms/character.md) · [Code point](../../terms/code-point.md)

## Further reading

* Foundations: [Grapheme (Unicode Glossary)](https://www.unicode.org/glossary/#grapheme)
