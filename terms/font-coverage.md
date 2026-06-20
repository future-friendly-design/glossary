---
term: Font coverage
slug: font-coverage
aliases: [character coverage, language support, glyph coverage]
tags: [typography]
level: intermediate
depth: deep
summary: Font coverage is the set of characters and languages a font can actually render.
related: [fallback-font, font-subsetting, full-width]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Language support in fonts (Google Fonts Knowledge)"
    url: https://fonts.google.com/knowledge/using_type/language_support_in_fonts
    type: resource
license: CC-BY-4.0
---

## Definition
Font coverage is the set of characters and languages a font can actually render.

## Why it matters
A font supports a language only when it includes the glyphs that language needs and, for many scripts, the correct shaping behavior, not just the matching code points. Google Fonts defines required glyphsets (such as GF Latin Core) so families cover common languages, and projects like Google's Noto extend coverage across 150-plus scripts to eliminate missing-glyph boxes. Wherever coverage runs out is exactly where [fallback-font](fallback-font.md)s have to step in.

## Example
A Latin-only font lacks coverage for Cyrillic, so Russian text falls back to another font.

## Common mistake
Assuming "the font has the code points" means "the font supports the language." Complex scripts need more than glyphs: Arabic letters have to join and change form, Indic clusters have to reorder and form conjuncts, and that logic lives in the font's shaping rules. A font can contain every code point and still render the script wrong. Check actual shaping, not just whether the characters are present.

## In practice
- **Selection and tokens:** when choosing a typeface for a multilingual product, verify coverage for every script you ship, including correct shaping, and treat it as a real selection criterion alongside things like [x-height](x-height.md). A beautiful typeface that cannot set your languages is the wrong choice.
- **Fallbacks and subsetting:** pair primary fonts with script-appropriate [fallback-font](fallback-font.md)s for the gaps, and make sure [font-subsetting](font-subsetting.md) does not quietly cut the coverage you promised users.
- **Languages:** confirm coverage claims against the actual languages and scripts in scope rather than a generic "supports Latin" label; the language experts can confirm what a given script genuinely requires.

## Related terms
[fallback-font](fallback-font.md) · [font-subsetting](font-subsetting.md) · [full-width](full-width.md)

## Further reading
- Resource library: [Language support in fonts (Google Fonts Knowledge)](https://fonts.google.com/knowledge/using_type/language_support_in_fonts)
