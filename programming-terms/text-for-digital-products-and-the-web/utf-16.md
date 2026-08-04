---
term: UTF-16
slug: utf-16
aliases: []
tags: [characters-encoding]
level: intermediate
depth: core
summary: UTF-16 stores Unicode text in 16-bit units, using one unit for common characters and two for the rest.
related: [utf-8, surrogate-pair, plane-bmp, character-encoding]
status: voice-passed
version_added: 0.1
updated: 2026-08-04
contributors: [sam-gordashko]
further_reading:
  - title: "String: length (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length
    type: code
  - title: "UTF-16 Encoding Form (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#utf_16_encoding_form
    type: authority
license: CC-BY-4.0
---

# UTF-16

## Definition

UTF-16 stores Unicode text in 16-bit units, using one unit for common characters and two for the rest.<sup>1</sup>

### Why it matters in design systems

The split is by [plane](plane-bmp.md). Characters in the range U+0000 to U+FFFF, the Basic Multilingual Plane, take a single 16-bit [code unit](code-unit.md); characters in the supplementary planes above U+FFFF take two, in the form of a [surrogate pair](surrogate-pair.md).<sup>2</sup> Since the BMP holds the common-use characters of all modern scripts, UTF-16 behaves like a fixed-width encoding most of the time,<sup>3</sup> which is exactly what makes it dangerous: code written on the assumption that one unit equals one character works fine right up until it does not.

That assumption is baked into a lot of software. JavaScript strings are UTF-16, and a string's length is a count of UTF-16 code units rather than characters,<sup>4</sup> so anything outside the BMP counts double. Emoji are the familiar case, but so are historic scripts and recently encoded ones, including scripts that living language communities are actively working to bring into digital use.

For a design system, the takeaway is not to avoid UTF-16, which is rarely your choice to make. It is to stop trusting `length` as a character count in any user-facing rule. Count in [grapheme clusters](grapheme-cluster.md) when a person will see the number, and reserve code-unit counts for storage limits, where they actually mean something.

***

### Related terms and mentions

[Character](character.md) · [Character encoding](character-encoding.md) · [Code point](code-point.md) · [Code unit](code-unit.md) · [Grapheme cluster](grapheme-cluster.md) · [Language](../../language-terms/linguistics/language.md) · [Plane / Basic Multilingual Plane](plane-bmp.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Surrogate pair](surrogate-pair.md) · [Unicode](unicode.md) · [UTF-8](utf-8.md) · [Text in software](../text-in-software/)

### Further reading

* Code & specs: [String: length (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
* Foundations: [UTF-16 Encoding Form (Unicode Glossary)](https://www.unicode.org/glossary/#utf_16_encoding_form)

### Sources

1. "The Unicode encoding form that assigns each Unicode scalar value in the ranges U+0000..U+D7FF and U+E000..U+FFFF to a single unsigned 16-bit code unit ... and that assigns each Unicode scalar value in the range U+10000..U+10FFFF to a surrogate pair" - Unicode Glossary: UTF-16 Encoding Form [https://www.unicode.org/glossary/#utf\_16\_encoding\_form](https://www.unicode.org/glossary/#utf_16_encoding_form)
2. "In the UTF-16 encoding form, non-surrogate code points in the range U+0000..U+FFFF are represented as a single 16-bit code unit; code points in the supplementary planes, in the range U+10000..U+10FFFF, are represented as pairs of 16-bit code units" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/latest/core-spec/chapter-2/](https://www.unicode.org/versions/latest/core-spec/chapter-2/)
3. "For the BMP, UTF-16 can effectively be treated as if it were a fixed-width encoding form" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/latest/core-spec/chapter-2/](https://www.unicode.org/versions/latest/core-spec/chapter-2/)
4. "The length data property of a String value contains the length of the string in UTF-16 code units" - String: length, MDN [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
