---
term: Grapheme
slug: grapheme
aliases: []
tags: [characters-encoding]
level: intermediate
depth: core
summary: "A grapheme is the smallest unit of a writing system that distinguishes meaning, such as a letter, a digit, or a punctuation mark."
related: [grapheme-cluster, glyph, character, code-point]
status: voice-passed
version_added: 0.1
updated: 2026-06-22
contributors: [sam-gordashko]
further_reading:
  - title: "Grapheme (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#grapheme
    type: authority
license: CC-BY-4.0
---

# Grapheme

## Definition
A grapheme is the smallest unit of a writing system that distinguishes meaning, such as a letter, a digit, or a punctuation mark.

## Why it matters
A grapheme is the abstract "letter": the unit a writing system treats as meaningfully distinct, the way a phoneme is the unit of sound. It is worth separating from three things it gets confused with. A [glyph](glyph.md) is how a grapheme is drawn, and one grapheme can have many glyphs (the same "a" across fonts, or a letter's initial and final forms). A [character](character.md) in Unicode is a [code point](code-point.md), and graphemes do not map to code points one to one: the single grapheme "é" can be one code point or two (an "e" plus a combining accent). Because of that gap, Unicode uses [grapheme cluster](grapheme-cluster.md) for what a reader perceives as one character. Keeping grapheme (the unit of writing), glyph (the drawn shape), and code point (the stored value) distinct is what prevents the classic counting and rendering bugs.

## Example
The letter "b" is one grapheme; it can be set in countless glyphs across typefaces, and in Unicode it is a single code point. The accented "é" is also one grapheme, but it can be stored as two code points.

## Related terms
[Grapheme cluster](grapheme-cluster.md) · [Glyph](glyph.md) · [Character](character.md) · [Code point](code-point.md)

## Further reading
- Foundations: [Grapheme (Unicode Glossary)](https://www.unicode.org/glossary/#grapheme)

<!-- NEEDS EXPERT REVIEW: source is the Unicode glossary (confirm the #grapheme anchor resolves). The grapheme / glyph / character / grapheme-cluster distinctions are standard but should be confirmed by the cohort; "grapheme" also has a stricter linguistics sense (a minimally distinctive unit within a specific writing system) worth noting. -->
