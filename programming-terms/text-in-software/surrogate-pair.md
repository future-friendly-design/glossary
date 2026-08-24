---
term: Surrogate pair
slug: surrogate-pair
aliases:
  - surrogates
level: advanced
depth: core
summary: A surrogate pair is two UTF-16 storage slots used together to hold one character that will not fit in a single slot.
related:
  - utf-16
  - plane-bmp
  - code-point
status: voice-passed
version_added: 0.1
updated: 2026-08-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'String: length (MDN)'
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length
    type: code
  - title: Surrogate Pair (Unicode Glossary)
    url: https://www.unicode.org/glossary/#surrogate_pair
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Surrogate pair

## Definition

A surrogate pair is two UTF-16 storage slots used together to hold one character that will not fit in a single slot.<sup>1</sup>

It is a mechanism of [UTF-16](utf-16.md), a way of storing text that gives every slot the same fixed size. Those slots are called [code units](../text-for-digital-products-and-the-web/code-unit.md), and each one can hold a number up to 65,535.

### Why it matters in design systems

Unicode's numbering runs far past 65,535, so a single slot cannot reach every character. Rather than make the slot bigger, UTF-16 sets aside two stretches of numbers that are not characters at all and only ever mean "this is one half of a pair". A character above U+FFFF is stored as a high surrogate, from U+D800 to U+DBFF,<sup>2</sup> followed by a low surrogate, from U+DC00 to U+DFFF.<sup>3</sup> Because those ranges exist for nothing else, a surrogate sitting on its own has no interpretation at all.<sup>4</sup> Split a pair down the middle and you have not produced half a character, you have produced invalid text.

The mechanism belongs to one way of storing text and no other. Surrogate pairs are used only in UTF-16,<sup>5</sup> so this is not a property of Unicode, and not a property of the character either; it is an artifact of how one storage scheme reaches past its own ceiling. The same character stored as [UTF-8](utf-8.md) is simply four bytes long, with no surrogates involved.

Where this reaches a design system is anywhere text gets cut by index. Truncating a string at "20 characters", stepping a cursor, or slicing for a preview will eventually land between the two halves of a pair, and the visible result is a replacement character or an empty box in the middle of someone's content. Stepping through the text one [code point](code-point.md) at a time, one whole character number at a time, avoids splitting a pair, and iterating by [grapheme cluster](grapheme-cluster.md) additionally avoids splitting a character from its marks, which is the behaviour a reader actually expects.

This is not an emoji edge case, though emoji are where teams usually meet it. The supplementary [planes](plane-bmp.md) hold historic scripts and recently encoded ones, so the communities most affected by naive string slicing are often the ones whose scripts arrived in Unicode most recently.

***

### Related terms and mentions

[Character](character.md) · [Code point](code-point.md) · [Code unit](../text-for-digital-products-and-the-web/code-unit.md) · [Grapheme cluster](grapheme-cluster.md) · [Plane / Basic Multilingual Plane](plane-bmp.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Unicode](unicode.md) · [UTF-8](utf-8.md) · [UTF-16](utf-16.md) · [Text in software](./)

### Further reading

* Code & specs: [String: length (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
* Foundations: [Surrogate Pair (Unicode Glossary)](https://www.unicode.org/glossary/#surrogate_pair)

### Sources

1. "A representation for a single abstract character that consists of a sequence of two 16-bit code units, where the first value of the pair is a high-surrogate code unit, and the second is a low-surrogate code unit" - Unicode Glossary: Surrogate Pair [https://www.unicode.org/glossary/#surrogate\_pair](https://www.unicode.org/glossary/#surrogate_pair)
2. "A Unicode code point in the range U+D800 to U+DBFF" - Unicode Glossary: High-Surrogate Code Point [https://www.unicode.org/glossary/#high\_surrogate\_code\_point](https://www.unicode.org/glossary/#high_surrogate_code_point)
3. "A Unicode code point in the range U+DC00 to U+DFFF" - Unicode Glossary: Low-Surrogate Code Point [https://www.unicode.org/glossary/#low\_surrogate\_code\_point](https://www.unicode.org/glossary/#low_surrogate_code_point)
4. "Isolated surrogate code units have no interpretation on their own" - The Unicode Standard, Core Specification, Chapter 3, definition D75 [https://www.unicode.org/versions/latest/core-spec/chapter-3/](https://www.unicode.org/versions/latest/core-spec/chapter-3/)
5. "Surrogate pairs are used only in UTF-16" - The Unicode Standard, Core Specification, Chapter 3, definition D75 [https://www.unicode.org/versions/latest/core-spec/chapter-3/](https://www.unicode.org/versions/latest/core-spec/chapter-3/)
