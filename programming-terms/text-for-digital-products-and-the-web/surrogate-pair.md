---
term: Surrogate pair
slug: surrogate-pair
aliases: [surrogates]
tags: [characters-encoding]
level: advanced
depth: core
summary: A surrogate pair is two UTF-16 code units used together to represent a character beyond the Basic Multilingual Plane.
related: [utf-16, plane-bmp, code-point]
status: voice-passed
version_added: 0.1
updated: 2026-08-04
contributors: [sam-gordashko]
further_reading:
  - title: "String: length (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length
    type: code
  - title: "Surrogate Pair (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#surrogate_pair
    type: authority
license: CC-BY-4.0
---

# Surrogate pair

## Definition

A surrogate pair is two [UTF-16](utf-16.md) [code units](code-unit.md) used together to represent a character beyond the Basic Multilingual Plane.<sup>1</sup>

### Why it matters in design systems

UTF-16 can only reach characters above U+FFFF by pairing a high surrogate, from U+D800 to U+DBFF,<sup>2</sup> with a low surrogate, from U+DC00 to U+DFFF.<sup>3</sup> Those ranges are reserved for exactly this purpose and are not characters in their own right, so a surrogate on its own has no interpretation at all.<sup>4</sup> Split a pair down the middle and you have not produced half a character, you have produced invalid text.

The mechanism belongs to one encoding only. Surrogate pairs are used only in UTF-16,<sup>5</sup> so this is not a property of Unicode or of the character; it is an artifact of how one encoding reaches past its own 16-bit ceiling. The same character in [UTF-8](utf-8.md) is simply four bytes, with no surrogates involved.

Where this reaches a design system is anywhere text gets cut by index. Truncating a string at "20 characters", stepping a cursor, or slicing for a preview will eventually land between the two halves of a pair, and the visible result is a replacement character or an empty box in the middle of someone's content. Iterating by code point avoids splitting a pair, and iterating by [grapheme cluster](grapheme-cluster.md) additionally avoids splitting a character from its marks, which is the behaviour a reader actually expects.

This is not an emoji edge case, though emoji are where teams usually meet it. The supplementary [planes](plane-bmp.md) hold historic scripts and recently encoded ones, so the communities most affected by naive string slicing are often the ones whose scripts arrived in Unicode most recently.

***

### Related terms and mentions

[Character](character.md) · [Code point](code-point.md) · [Code unit](code-unit.md) · [Grapheme cluster](grapheme-cluster.md) · [Plane / Basic Multilingual Plane](plane-bmp.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Unicode](unicode.md) · [UTF-8](utf-8.md) · [UTF-16](utf-16.md) · [Text in software](../text-in-software/)

### Further reading

* Code & specs: [String: length (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
* Foundations: [Surrogate Pair (Unicode Glossary)](https://www.unicode.org/glossary/#surrogate_pair)

### Sources

1. "A representation for a single abstract character that consists of a sequence of two 16-bit code units, where the first value of the pair is a high-surrogate code unit, and the second is a low-surrogate code unit" - Unicode Glossary: Surrogate Pair [https://www.unicode.org/glossary/#surrogate\_pair](https://www.unicode.org/glossary/#surrogate_pair)
2. "A Unicode code point in the range U+D800 to U+DBFF" - Unicode Glossary: High-Surrogate Code Point [https://www.unicode.org/glossary/#high\_surrogate\_code\_point](https://www.unicode.org/glossary/#high_surrogate_code_point)
3. "A Unicode code point in the range U+DC00 to U+DFFF" - Unicode Glossary: Low-Surrogate Code Point [https://www.unicode.org/glossary/#low\_surrogate\_code\_point](https://www.unicode.org/glossary/#low_surrogate_code_point)
4. "Isolated surrogate code units have no interpretation on their own" - The Unicode Standard, Core Specification, Chapter 3, definition D75 [https://www.unicode.org/versions/latest/core-spec/chapter-3/](https://www.unicode.org/versions/latest/core-spec/chapter-3/)
5. "Surrogate pairs are used only in UTF-16" - The Unicode Standard, Core Specification, Chapter 3, definition D75 [https://www.unicode.org/versions/latest/core-spec/chapter-3/](https://www.unicode.org/versions/latest/core-spec/chapter-3/)
