---
term: Shaping engine
slug: shaping-engine
aliases: [shaper, HarfBuzz]
tags: [shaping-layout]
level: intermediate
depth: core
summary: A shaping engine is the software that performs text shaping; HarfBuzz is the most widely used one.
related: [text-shaping, gsub, gpos, opentype, complex-text-layout]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "What is HarfBuzz? (HarfBuzz)"
    url: https://harfbuzz.github.io/what-is-harfbuzz.html
    type: authority
license: CC-BY-4.0
---

## Definition
A shaping engine is the software that performs text shaping; HarfBuzz is the most widely used one.

## Why it matters
A shaping engine takes Unicode text, a font, and script and language information, then returns glyph IDs with positions for a renderer to draw. It implements the per-script rules and reads the font's [gsub](gsub.md) and [gpos](gpos.md) tables, so it is the piece that actually carries out [text-shaping](text-shaping.md). HarfBuzz, the open-source engine, powers text on Android, Chrome, Firefox, LibreOffice, and many other platforms, which means it shapes much of the text you see on screen every day.

## Example
Chrome uses HarfBuzz to shape this sentence before it is painted on screen.

## Related terms
[Text shaping](text-shaping.md) · [GSUB](gsub.md) · [GPOS](gpos.md) · [OpenType](opentype.md) · [Complex text layout](complex-text-layout.md)

## Further reading
- Foundations: [What is HarfBuzz? (HarfBuzz)](https://harfbuzz.github.io/what-is-harfbuzz.html)
