---
term: Full-width
slug: full-width
aliases:
  - fullwidth
  - zenkaku
level: advanced
depth: deep
summary: >-
  A full-width character fills one full square cell, the same width as a typical
  Chinese, Japanese, or Korean character, while a half-width character takes
  about half of it.
related:
  - tategaki
  - font-coverage
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: font-variant-east-asian (MDN)
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian
    type: code
  - title: Halfwidth and Fullwidth Forms, U+FF00-FFEF (Unicode chart)
    url: https://www.unicode.org/charts/PDF/UFF00.pdf
    type: authority
license: CC-BY-4.0
tags:
  - typography
---

# Full-width

## Definition

A full-width character fills one full square cell, the same width as a typical Chinese, Japanese, or Korean character, while a half-width character takes about half of it.<sup>1</sup>

### Why it matters in design systems

Chinese<sup>2</sup> and Japanese<sup>3</sup> text is traditionally set on a grid: each character sits in its own square cell, and the cells line up down the column and across the line. The two widths come out of that grid. A full-width character fills the cell, which in typographic terms is one em, the full width of the type size; a half-width character takes about half of it.<sup>4</sup> Anything mixed into that text, such as Latin letters, digits, or punctuation, has to be one or the other, or the grid stops lining up.

[Unicode](unicode.md) includes a Halfwidth and Fullwidth Forms block (U+FF00 to U+FFEF) that holds full-width Latin letters, digits, and punctuation, plus half-width Katakana and half-width Hangul, the Korean script.<sup>5</sup> Those exist mainly so that text from older character lists, the ones that predate Unicode, could be converted into Unicode and back without losing anything.<sup>6</sup> For live layout, the width is normally selected through [OpenType features](../fonts/opentype-features.md) (`fwid`, `hwid`) or CSS, not by reaching for those compatibility characters.

### Example

A full-width comma `，` (U+FF0C), used in Chinese text, takes up the same square cell as a Han character such as `漢` (U+6F22), while the ordinary comma `,` (U+002C) is narrower.

### Common mistake

Treating the Halfwidth and Fullwidth Forms block as the normal way to set width in Chinese, Japanese, and Korean text. Those characters exist largely for compatibility with the older character lists; using them as content can break search and matching, because a full-width `A` (U+FF21) is a different character, with a different number, from a regular `A` (U+0041). The two widths are a relationship between a pair of characters rather than a property either one carries on its own.<sup>7</sup> [Normalization](normalization.md) in its NFKC form folds the two together, which is something to account for in search, deduplication, and input handling.

### In practice

* **CSS and OpenType:** `font-variant-east-asian: full-width` (OpenType `fwid`) selects full-width forms at the rendering layer, keeping the underlying text as ordinary [code points](code-point.md). See [font-variant-east-asian (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian).
* **Engineering:** when text mixes full-width and half-width forms, decide deliberately whether to normalize (NFKC) before indexing or comparing it, so the two widths do not split what users think of as the same string.
* **Languages:** this is an East-Asian-specific model; the conventions for when full-width versus half-width is expected are best confirmed by the language experts rather than assumed.

***

### Related terms and mentions

[Character](character.md) · [CJK](../../language-terms/writing-systems-and-scripts/cjk.md) · [Code point](code-point.md) · [Font coverage](../fonts/font-coverage.md) · [Han characters script](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Hangul script](../../language-terms/writing-systems-and-scripts/hangul.md) · [Katakana script](../../language-terms/writing-systems-and-scripts/katakana.md) · [Language](../../language-terms/linguistics/language.md) · [Latin script](../../language-terms/writing-systems-and-scripts/latin-script.md) · [Normalization](normalization.md) · [OpenType](../fonts/opentype.md) · [OpenType features](../fonts/opentype-features.md) · [Punctuation mark](../../language-terms/writing-systems-and-scripts/punctuation-mark.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Tategaki](../../language-terms/writing-systems-and-scripts/tategaki.md) · [Unicode](unicode.md) · [Text encoding & character terms](./)

### Further reading

* Code & specs: [font-variant-east-asian (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian)
* Foundations: [Halfwidth and Fullwidth Forms, U+FF00-FFEF (Unicode chart)](https://www.unicode.org/charts/PDF/UFF00.pdf)

### Sources

1. "Characters of East Asian character sets whose glyph image extends across the entire character display cell... The Japanese term for fullwidth characters is zenkaku" - Unicode Glossary: Fullwidth [https://www.unicode.org/glossary/#fullwidth](https://www.unicode.org/glossary/#fullwidth)
2. "In principle, the characters, including Han characters (Hanzi) and punctuation, used in Chinese composition are squares with the ratio of 1:1, and are seamlessly arranged with one another" - Requirements for Chinese Text Layout, W3C [https://www.w3.org/TR/clreq/](https://www.w3.org/TR/clreq/)
3. "In principle, all character frames of ideographic (cl-19), hiragana (cl-15) and katakana (cl-16) characters used in Japanese composition are designed in a square box, and these characters are composed without intervening spacing" - Requirements for Japanese Text Layout, W3C [https://www.w3.org/TR/jlreq/](https://www.w3.org/TR/jlreq/)
4. "By convention, 1/2 Em wide characters of East Asian legacy encodings are called "halfwidth" (or hankaku characters in Japanese); the others are called correspondingly "fullwidth" (or zenkaku) characters" - Unicode Standard Annex #11: East Asian Width [https://www.unicode.org/reports/tr11/](https://www.unicode.org/reports/tr11/)
5. "The characters in this block consist of fullwidth forms of the ASCII block (except SPACE), certain characters of the Latin-1 Supplement, and some currency symbols. In addition, this block contains halfwidth forms of the Katakana and Hangul Compatibility Jamo characters" - The Unicode Standard, Core Specification, Chapter 18, section 18.5 [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-18/)
6. "To achieve round-trip conversion compatibility with such mixed-width encoding systems, it is necessary to encode both fullwidth and halfwidth forms of certain characters" - The Unicode Standard, Core Specification, Chapter 18, section 18.5 [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-18/)
7. "the "halfwidth" and "fullwidth" properties are not unitary character properties in the same sense as "space" or "combining" or "alphabetic." They are, instead, relational properties of a pair of characters" - Unicode Standard Annex #11: East Asian Width [https://www.unicode.org/reports/tr11/](https://www.unicode.org/reports/tr11/)
