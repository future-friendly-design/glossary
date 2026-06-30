---
term: Text shaping
slug: text-shaping
aliases:
  - shaping
level: intermediate
depth: deep
summary: >-
  Text shaping turns a string of characters into the exact glyphs and positions
  a font should draw.
related:
  - shaping-engine
  - complex-text-layout
  - gsub
  - gpos
  - opentype
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: What is HarfBuzz? (HarfBuzz)
    url: https://harfbuzz.github.io/what-is-harfbuzz.html
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
  - shaping-layout
---

# Text shaping

## Definition

Text shaping turns a string of characters into the exact glyphs and positions a font should draw.

### Why it matters in design systems

Shaping is the step between text and pixels. A shaper takes [Unicode](../terms/unicode.md) text, a font, and the script and language, then selects the correct glyph forms and computes their x and y positions before anything is rendered. For scripts where letters change shape by context ([Arabic](../terms/arabic-script.md)) or get reordered and stacked ([Devanagari](../terms/devanagari.md)), shaping is where that logic happens, driven by the font's [OpenType](../terms/opentype.md) layout tables ([GSUB](../terms/gsub.md) for substitution, [GPOS](../terms/gpos.md) for positioning).<sup>1</sup>

So for a design system, shaping is necessary but easy to skip by accident. It is the machinery that makes [complex text layout](../terms/complex-text-layout.md) possible, and any path that draws text without it, by counting characters or placing glyphs in order, will break every script that joins, reorders, or stacks.

### Example

Shaping turns the Arabic letters in a word into their initial, medial, and final joined forms.

### Common mistake

Assuming text is just glyphs placed one after another, an assumption that holds for simple Latin and quietly breaks everything else. Measuring text width by counting characters, building your own glyph layout, or rotating a string to fake vertical text all fall apart for scripts that join, reorder, or stack, because they skip shaping.

### In practice

* **Let a real shaper do it:** on the web, in apps, and in OS text fields the platform shapes text for you (usually via the [shaping engine](../terms/shaping-engine.md) HarfBuzz). Do not hand-roll glyph layout; lean on the engine and supply fonts that carry the right OpenType tables. See [What is HarfBuzz? (HarfBuzz)](https://harfbuzz.github.io/what-is-harfbuzz.html).
* **Watch the boundaries:** when you render text outside the normal pipeline (canvas, PDF generation, image export), confirm that path actually shapes, or complex scripts will come out wrong.
* **Languages:** correct shaping depends on the font declaring script and language support; verify it for every script you ship, and confirm complex-script results with the language experts.

***

### Related terms and mentions

[Arabic script](../terms/arabic-script.md) · [Complex text layout](../terms/complex-text-layout.md) · [Devanagari](../terms/devanagari.md) · [GPOS](../terms/gpos.md) · [GSUB](../terms/gsub.md) · [OpenType](../terms/opentype.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Shaping engine](../terms/shaping-engine.md) · [Unicode](../terms/unicode.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [What is HarfBuzz? (HarfBuzz)](https://harfbuzz.github.io/what-is-harfbuzz.html)

### Sources

1. OpenType Layout turns characters into positioned glyphs in two stages: the GSUB table substitutes glyph forms and the GPOS table positions them - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
