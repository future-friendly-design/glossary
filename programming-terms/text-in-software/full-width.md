---
term: Full-width
slug: full-width
aliases:
  - fullwidth
  - zenkaku
level: advanced
depth: deep
summary: A full-width character fills one full square cell, the same width as a typical Chinese, Japanese, or Korean character, while a half-width character takes about half of it.
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

Chinese, Japanese, and Korean text is traditionally set on a grid: each character sits in its own square cell, and the cells line up down the column and across the line. The two widths come out of that grid. A full-width character fills the cell, which in typographic terms is one em, the full width of the type size; a half-width character takes about half of it.<sup>2</sup> Anything mixed into that text, such as Latin letters, digits, or punctuation, has to be one or the other, or the grid stops lining up.

[Unicode](unicode.md) includes a Halfwidth and Fullwidth Forms block (U+FF00 to U+FFEF) that holds full-width Latin letters and punctuation plus half-width Katakana. Those exist mainly so that text from older character lists, the ones that predate Unicode, could be converted into Unicode and back without losing anything. For live layout, the width is normally selected through [OpenType features](../../design-terms/typography/opentype-features.md) (`fwid`, `hwid`) or CSS, not by reaching for those compatibility characters.

### Example

A full-width comma in Japanese text takes up the same square cell as a kanji, while its half-width version is narrower.

### Common mistake

Treating the Halfwidth and Fullwidth Forms block as the normal way to set width in Chinese, Japanese, and Korean text. Those characters exist largely for compatibility with the older character lists; using them as content can break search and matching, because a full-width `A` (U+FF21) is a different character, with a different number, from a regular `A` (U+0041). The two widths are a relationship between a pair of characters rather than a property either one carries on its own.<sup>3</sup> [Normalization](normalization.md) in its NFKC form folds the two together, which is something to account for in search, deduplication, and input handling.

<!-- NEEDS EXPERT REVIEW: confirm the recommended handling of NFKC folding for full-width forms in search and deduplication. -->

### In practice

* **CSS and OpenType:** `font-variant-east-asian: full-width` (OpenType `fwid`) selects full-width forms at the rendering layer, keeping the underlying text as ordinary [code points](code-point.md). See [font-variant-east-asian (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian).
* **Engineering:** when text mixes full-width and half-width forms, decide deliberately whether to normalize (NFKC) before storing, indexing, or comparing it, so the two widths do not split what users think of as the same string.
* **Languages:** this is an East-Asian-specific model; the conventions for when full-width versus half-width is expected are best confirmed by the language experts rather than assumed.

***

### Related terms and mentions

[Character](character.md) · [CJK](../../language-terms/writing-systems-and-scripts/cjk.md) · [Code point](code-point.md) · [Font coverage](../text-for-digital-products-and-the-web/font-coverage.md) · [Normalization](normalization.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Tategaki](../../language-terms/writing-systems-and-scripts/tategaki.md) · [Unicode](unicode.md) · [Text in software](./)

### Further reading

* Code & specs: [font-variant-east-asian (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian)
* Foundations: [Halfwidth and Fullwidth Forms, U+FF00-FFEF (Unicode chart)](https://www.unicode.org/charts/PDF/UFF00.pdf)

### Sources

1. "Characters of East Asian character sets whose glyph image extends across the entire character display cell... The Japanese term for fullwidth characters is zenkaku" - Unicode Glossary: Fullwidth [https://www.unicode.org/glossary/#fullwidth](https://www.unicode.org/glossary/#fullwidth)
2. "By convention, 1/2 Em wide characters of East Asian legacy encodings are called \"halfwidth\" (or hankaku characters in Japanese); the others are called correspondingly \"fullwidth\" (or zenkaku) characters" - Unicode Standard Annex #11: East Asian Width [https://www.unicode.org/reports/tr11/](https://www.unicode.org/reports/tr11/)
3. "the \"halfwidth\" and \"fullwidth\" properties are not unitary character properties in the same sense as \"space\" or \"combining\" or \"alphabetic.\" They are, instead, relational properties of a pair of characters" - Unicode Standard Annex #11: East Asian Width [https://www.unicode.org/reports/tr11/](https://www.unicode.org/reports/tr11/)
