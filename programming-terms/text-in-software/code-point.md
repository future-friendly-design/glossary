---
term: Code point
slug: code-point
aliases:
  - codepoint
level: foundational
depth: core
summary: A code point is the number Unicode assigns to a character.
related:
  - character
  - unicode
  - character-encoding
  - plane-bmp
status: voice-passed
version_added: 0.1
updated: 2026-08-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Code Point (Unicode Glossary)
    url: https://www.unicode.org/glossary/#code_point
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Code point

## Definition

A code point is the number [Unicode](unicode.md) assigns to a [character](character.md).

For example, the code point for the symbol `á` is 225 in decimal, or E1 in hexadecimal,<sup>1</sup> which is written `U+00E1`.

### Why it matters in design systems

Code points are written as `U+` followed by hexadecimal digits, and they live in a fixed range. Unicode's codespace runs from 0 to 10FFFF, which is 1,114,112 possible code points, or roughly 1.1 million.<sup>2</sup> That range is the whole budget for every script Unicode has encoded and every one it has yet to encode.

The code point is what makes text portable: the same number identifies the same character in every system that follows the [Unicode Standard](unicode-standard.md).&#x20;

Storing a code point requires a [character encoding](character-encoding.md) to turn it into bytes, the data actually written to a file or a database. Visualizing the character in software requires a [font](../text-for-digital-products-and-the-web/font.md) that contains the correct [glyph](../text-for-digital-products-and-the-web/glyph.md) to represent it.&#x20;

Two things surprise people. Not every code point is assigned to a character,<sup>3</sup> so a valid-looking number may be reserved, unassigned, or a control code that renders as nothing. And one code point is not reliably one character on screen: an accented symbol may be built from two, and an emoji from several, which is the difference between a code point and a [grapheme cluster](grapheme-cluster.md). If you are counting text for a limit, a truncation, or a cursor step, the code point is almost never the unit your reader is using.

***

### Related terms and mentions

[Character](character.md) · [Character encoding](character-encoding.md) · [Font](../text-for-digital-products-and-the-web/font.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [Grapheme cluster](grapheme-cluster.md) · [Plane / Basic Multilingual Plane](plane-bmp.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Surrogate pair](surrogate-pair.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](unicode.md) · [Unicode Standard](unicode-standard.md) · [Text in software](./)

### Further reading

* Foundations: [Code Point (Unicode Glossary)](https://www.unicode.org/glossary/#code_point)

### Sources

1. "For example, the code point for the letter á in the Unicode coded character set is 225 in decimal, or 0xE1 in hexadecimal notation" - Character encodings: Essential concepts, W3C Internationalization [https://www.w3.org/International/articles/definitions-characters/](https://www.w3.org/International/articles/definitions-characters/)
2. "the codespace consists of the integers from 0 to 10FFFF16, comprising 1,114,112 code points available for assigning the repertoire of abstract characters" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/latest/core-spec/chapter-2/](https://www.unicode.org/versions/latest/core-spec/chapter-2/)
3. "Not all code points are assigned to encoded characters" - Unicode Glossary: Code Point [https://www.unicode.org/glossary/#code\_point](https://www.unicode.org/glossary/#code_point)
