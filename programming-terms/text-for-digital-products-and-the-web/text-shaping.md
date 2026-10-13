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

Shaping is the step between text and pixels. A shaper takes [Unicode](../text-in-software/unicode.md) text, a font, and the script and language, then selects the correct glyph forms and computes their x and y positions before anything is rendered.<sup>1</sup> For scripts where letters change shape by context ([Arabic](../../language-terms/writing-systems-and-scripts/arabic-script.md)) or get reordered and stacked ([Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md)), shaping is where that logic happens. Swapping and placing glyphs is driven by the font's [OpenType](../../design-terms/typography/opentype.md) layout tables ([GSUB](gsub.md) for substitution, [GPOS](gpos.md) for positioning).<sup>2</sup> [Reordering](reordering.md) is different: the shaping software does it by its own rules, and it is not stored in the font.<sup>3</sup>

So for a design system, shaping is necessary but easy to skip by accident. It is the machinery that makes [complex text layout](complex-text-layout.md) possible, and any path that draws text without it, by counting characters or placing glyphs in order, will break every script that joins, reorders, or stacks.

### Example

Shaping turns the Arabic letters in a word into their initial, medial, and final joined forms.

### Common mistake

Assuming text is just glyphs placed one after another, an assumption that looks true for a lot of English text and quietly breaks for many other scripts.<sup>4</sup> Measuring text width by counting characters, building your own glyph layout, or rotating a string to fake vertical text all fall apart for scripts that join, reorder, or stack, because they skip shaping.

### In practice

* **Let a real shaper do it:** on the web, in apps, and in OS text fields the platform shapes text for you (through a [shaping engine](shaping-engine.md) such as HarfBuzz, or CoreText on macOS).<sup>5</sup> Do not hand-roll glyph layout; lean on the engine and supply fonts that carry the right OpenType tables. See [What is HarfBuzz? (HarfBuzz)](https://harfbuzz.github.io/what-is-harfbuzz.html).
* **Watch the boundaries:** when you render text outside the normal pipeline (canvas, PDF generation, image export), confirm that path actually shapes, or complex scripts will come out wrong.
* **Languages:** correct shaping depends on the font declaring script and language support; verify it for every script you ship, and confirm complex-script results with the language experts.

***

### Related terms and mentions

[Arabic script](../../language-terms/writing-systems-and-scripts/arabic-script.md) · [Character](../text-in-software/character.md) · [Complex text layout](complex-text-layout.md) · [Devanagari script](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](font.md) · [Glyph](glyph.md) · [GPOS](gpos.md) · [GSUB](gsub.md) · [Joining](../../language-terms/writing-systems-and-scripts/joining.md) · [Language](../../language-terms/linguistics/language.md) · [Ligature](ligature.md) · [OpenType](../../design-terms/typography/opentype.md) · [Reordering](reordering.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../../language-terms/writing-systems-and-scripts/script-rules.md) · [Shaping engine](shaping-engine.md) · [Stacking script](../../language-terms/writing-systems-and-scripts/stacking-script.md) · [Unicode](../text-in-software/unicode.md) · [Vertical text](../../terms/vertical-text.md) · [Text shaping & layout](../text-shaping-and-layout/)

### Further reading

* Foundations: [What is HarfBuzz? (HarfBuzz)](https://harfbuzz.github.io/what-is-harfbuzz.html)

### Sources

1. "The shaping process is dependent on the input string, the active font, the script (or writing system) that the string is in, and the language that the string is in" and "HarfBuzz selects and positions the corresponding glyphs from the font" - What is HarfBuzz?, HarfBuzz Manual [https://harfbuzz.github.io/what-is-harfbuzz.html](https://harfbuzz.github.io/what-is-harfbuzz.html)
2. GSUB "Contains information about glyph substitutions" and GPOS "Contains information about X and Y positioning of glyphs" - Advanced typographic tables: OpenType Layout, OpenType specification (Microsoft) [https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1](https://learn.microsoft.com/en-us/typography/opentype/spec/ttochap1)
3. "OpenType fonts should not have substitutions that attempt to perform the re-ordering" - Developing OpenType Fonts for Devanagari Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
4. "For some writing systems (or scripts) and languages, the process is simple, requiring the shaper to do little more than advance the horizontal position forward by the correct amount for each successive glyph. But, for other scripts (often unceremoniously called complex scripts), any combination of several shaping operations may be required" - Shaping concepts, HarfBuzz Manual [https://harfbuzz.github.io/shaping-concepts.html](https://harfbuzz.github.io/shaping-concepts.html)
5. "You could use Uniscribe if you are writing Windows software; you could use CoreText on macOS; or you could use HarfBuzz" - Why do I need a shaping engine?, HarfBuzz Manual [https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html](https://harfbuzz.github.io/why-do-i-need-a-shaping-engine.html)
