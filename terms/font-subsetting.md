---
term: Font subsetting
slug: font-subsetting
aliases: [subsetting]
tags: [typography]
level: advanced
depth: deep
summary: Font subsetting reduces a font file's size by keeping only the characters a page actually needs.
related: [font-coverage, fallback-font, variable-font, font]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "unicode-range (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range
    type: code
  - title: "Subsetting (Google Fonts Knowledge)"
    url: https://fonts.google.com/knowledge/glossary/subsetting
    type: resource
license: CC-BY-4.0
---

# Font subsetting

## Definition
Font subsetting reduces a font file's size by keeping only the characters a page actually needs.

## Why it matters
A subset is a font file that carries a limited collection of glyphs rather than the full character set, which is one of the biggest wins available for web font performance. Google Fonts does this automatically, slicing families by `unicode-range` so a browser downloads only the pieces a page uses. The savings are large because most pages use a small fraction of a full font's glyphs.

## Example
A subsetted WOFF2 of Roboto Regular can shrink from about 168KB to roughly 12KB by dropping unused glyphs.

## Common mistake
Subsetting so aggressively that you cut glyphs the product actually needs: accented letters for other languages, currency symbols, punctuation, or whole scripts. The text then quietly falls back to another font or shows empty boxes. Subset to every language and character set you support, not just the characters visible in your test content. This is the direct tension with [font-coverage](font-coverage.md).

## In practice
- **CSS:** `unicode-range` on `@font-face` splits a face into ranges; the browser downloads a range's file only if the page uses at least one character in it, and then downloads that whole slice (not a partial file). See [unicode-range (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range).
- **Build and tokens:** if you self-host, treat subsetting as a deliberate build step (with tools like glyphhanger or fonttools) and keep the subset in sync with the languages you claim to support, so a build change does not silently drop coverage.
- **With variable fonts:** a [variable-font](variable-font.md) cuts file count by packing styles together; subsetting cuts file size by dropping glyphs. The two compose, so you can do both.

## Related terms
[Font coverage](font-coverage.md) · [Fallback font](fallback-font.md) · [Variable font](variable-font.md) · [Font](font.md)

## Further reading
- Code & specs: [unicode-range (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range)
- Resource library: [Subsetting (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/subsetting)
