---
term: Full-width
slug: full-width
aliases: [fullwidth, zenkaku]
tags: [typography]
level: advanced
depth: deep
summary: Full-width characters occupy one full em square, the same width as a typical CJK character, unlike narrower half-width forms.
related: [tategaki, font-coverage]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "font-variant-east-asian (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian
    type: code
  - title: "Halfwidth and Fullwidth Forms, U+FF00–FFEF (Unicode chart)"
    url: https://www.unicode.org/charts/PDF/UFF00.pdf
    type: authority
license: CC-BY-4.0
---

## Definition
Full-width characters occupy one full em square, the same width as a typical CJK character, unlike narrower half-width forms.

## Why it matters
In Chinese, Japanese, and Korean typesetting, characters are traditionally classed as full-width (one em) or half-width (about half an em) so that text lines up in a uniform grid. Unicode includes a Halfwidth and Fullwidth Forms block (U+FF00 to U+FFEF) that holds full-width Latin letters and punctuation plus half-width Katakana, provided mainly for round-tripping older encodings. For live layout, the width is normally selected through OpenType features (`fwid`, `hwid`) or CSS, not by reaching for those compatibility characters.

## Example
A full-width comma in Japanese text takes up the same square cell as a kanji, while its half-width version is narrower.

## Common mistake
Treating the Halfwidth and Fullwidth Forms block as the normal way to set CJK width. Those code points exist largely for compatibility with legacy encodings; using them as content can break search and matching, because a full-width "A" (U+FF21) is a different code point from a regular "A" (U+0041). Unicode normalization (NFKC) folds the two together, which is something to account for in search, deduplication, and input handling. *(Flag for language and i18n experts to confirm the recommended handling.)*

## In practice
- **CSS and OpenType:** `font-variant-east-asian: full-width` (OpenType `fwid`) selects full-width forms at the rendering layer, keeping the underlying text as ordinary code points. See [font-variant-east-asian (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian).
- **Engineering:** when text mixes full-width and half-width forms, decide deliberately whether to normalize (NFKC) before storing, indexing, or comparing it, so the two widths do not split what users think of as the same string. *(Defer the specifics to the i18n experts.)*
- **Languages:** this is an East-Asian-specific model; the conventions for when full-width versus half-width is expected are best confirmed by the language experts rather than assumed.

## Related terms
[Tategaki](tategaki.md) · [Font coverage](font-coverage.md)

## Further reading
- Code & specs: [font-variant-east-asian (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian)
- Foundations: [Halfwidth and Fullwidth Forms, U+FF00–FFEF (Unicode chart)](https://www.unicode.org/charts/PDF/UFF00.pdf)
