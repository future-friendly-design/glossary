---
term: Unicode
slug: unicode
aliases: []
level: foundational
depth: core
summary: >-
  Unicode is the standard that gives every character in the world's writing
  systems a unique number.
related:
  - code-point
  - character-encoding
  - utf-8
  - plane-bmp
status: voice-passed
version_added: 0.1
updated: 2026-08-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Unicode (Unicode Glossary)
    url: https://www.unicode.org/glossary/#unicode
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Unicode

## Definition

Unicode is the standard that gives every [character](character.md) in the world's writing systems a unique number.<sup>1</sup>

### Why it matters in design systems

A computer can only store numbers, so somewhere there has to be a list saying which number means which character. Before Unicode, different language communities worked from different lists, and text moved between systems by luck: open a file with the wrong list loaded and the wrong characters come out. Unicode's contribution is a single agreement: one number per character, the same number everywhere, providing a uniform means for storing, searching, and interchanging text in any language.<sup>2</sup> That number is a [code point](code-point.md), and the full range runs from 0 to 10FFFF, about 1.1 million positions.<sup>3</sup>

What Unicode does not do is just as important, and skipping it causes most of the confusion in this area. Unicode assigns the numbers; it does not say how those numbers get written into a file, which is the job of a [character encoding](character-encoding.md) such as [UTF-8](utf-8.md). It does not draw anything either: the shapes on screen come from a [font](../text-for-digital-products-and-the-web/font.md), and a font covers only the characters it was drawn for. So "we support Unicode" is a claim about your data model, not about whether a person's name will render. Text can be encoded perfectly and still show as empty boxes because the font has no [glyph](../text-for-digital-products-and-the-web/glyph.md) for it.

For a design system, Unicode is the layer that makes the rest of the work possible rather than the layer that finishes it. Deciding to store text as Unicode is table stakes. The decisions that follow, which fonts cover which scripts, how text is counted and sorted, whether [shaping](../text-for-digital-products-and-the-web/text-shaping.md) is required, are the ones with visible consequences, and Unicode is what lets you reason about them at all.

Unicode is developed and maintained by the Unicode Consortium.<sup>4</sup> The published specification, its versions, and the annexes this glossary cites throughout are covered separately under [Unicode Standard](unicode-standard.md).

***

### Related terms and mentions

[Character](character.md) · [Character encoding](character-encoding.md) · [Code point](code-point.md) · [Font](../text-for-digital-products-and-the-web/font.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [Language](../../language-terms/linguistics/language.md) · [Plane / Basic Multilingual Plane](plane-bmp.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Text shaping](../text-for-digital-products-and-the-web/text-shaping.md) · [Unicode Standard](unicode-standard.md) · [UTF-8](utf-8.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Text in software](./)

### Further reading

* Foundations: [Unicode (Unicode Glossary)](https://www.unicode.org/glossary/#unicode)

### Sources

1. "The standard for digital representation of the characters used in writing all of the world's languages" - Unicode Glossary: Unicode, sense 1 [https://www.unicode.org/glossary/#unicode](https://www.unicode.org/glossary/#unicode)
2. "Unicode provides a uniform means for storing, searching, and interchanging text in any language" - Unicode Glossary: Unicode [https://www.unicode.org/glossary/#unicode](https://www.unicode.org/glossary/#unicode)
3. "the codespace consists of the integers from 0 to 10FFFF16, comprising 1,114,112 code points available for assigning the repertoire of abstract characters" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/latest/core-spec/chapter-2/](https://www.unicode.org/versions/latest/core-spec/chapter-2/)
4. "Unicode is developed and maintained by the Unicode Consortium" - Unicode Glossary: Unicode [https://www.unicode.org/glossary/#unicode](https://www.unicode.org/glossary/#unicode)
