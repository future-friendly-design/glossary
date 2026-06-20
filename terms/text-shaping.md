---
term: Text shaping
slug: text-shaping
aliases: [shaping]
tags: [shaping-layout]
level: intermediate
depth: deep
summary: Text shaping turns a string of characters into the exact glyphs and positions a font should draw.
related: [shaping-engine, complex-text-layout, gsub, gpos, opentype]
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
Text shaping turns a string of characters into the exact glyphs and positions a font should draw.

## Why it matters
Shaping is the step between text and pixels. A shaper takes Unicode text, a font, and the script and language, then selects the correct glyph forms and computes their x and y positions before anything is rendered. For scripts where letters change shape by context (Arabic) or get reordered and stacked (Devanagari), shaping is where that logic happens, driven by the font's [opentype](opentype.md) layout tables ([gsub](gsub.md) for substitution, [gpos](gpos.md) for positioning). It is the machinery that makes [complex-text-layout](complex-text-layout.md) possible.

## Example
Shaping turns the Arabic letters in a word into their initial, medial, and final joined forms.

## Common mistake
Assuming text is just glyphs placed one after another, an assumption that holds for simple Latin and quietly breaks everything else. Measuring text width by counting characters, building your own glyph layout, or rotating a string to fake vertical text all fall apart for scripts that join, reorder, or stack, because they skip shaping.

## In practice
- **Let a real shaper do it:** on the web, in apps, and in OS text fields the platform shapes text for you (usually via [shaping-engine](shaping-engine.md) HarfBuzz). Do not hand-roll glyph layout; lean on the engine and supply fonts that carry the right OpenType tables. See [What is HarfBuzz? (HarfBuzz)](https://harfbuzz.github.io/what-is-harfbuzz.html).
- **Watch the boundaries:** when you render text outside the normal pipeline (canvas, PDF generation, image export), confirm that path actually shapes, or complex scripts will come out wrong.
- **Languages:** correct shaping depends on the font declaring script and language support; verify it for every script you ship, and confirm complex-script results with the language experts.

## Related terms
[Shaping engine](shaping-engine.md) · [Complex text layout](complex-text-layout.md) · [GSUB](gsub.md) · [GPOS](gpos.md) · [OpenType](opentype.md)

## Further reading
- Foundations: [What is HarfBuzz? (HarfBuzz)](https://harfbuzz.github.io/what-is-harfbuzz.html)
