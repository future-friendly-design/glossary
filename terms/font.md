---
term: Font
slug: font
aliases: [font file]
tags: [typography]
level: foundational
depth: deep
summary: A font is a specific style and weight of a typeface, today usually delivered as a digital file.
related: [typeface, font-weight, variable-font]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Typeface vs Font: what's the difference? (TypeType)"
    url: https://typetype.org/blog/font-and-typeface-what-s-the-difference/
    type: authority
  - title: "Font (Google Fonts Knowledge)"
    url: https://fonts.google.com/knowledge/glossary/font
    type: resource
license: CC-BY-4.0
---

# Font

## Definition
A font is a specific style and weight of a typeface, today usually delivered as a digital file.

## Why it matters
A font is the thing you actually load and ship. The [typeface](typeface.md) is the design; the font is one specific cut of it, like Times New Roman Bold Italic (Times New Roman being a serif typeface, one with small finishing strokes on the letters). In casual use "font" and "typeface" are swapped freely. The distinction earns its keep on the engineering side, where a font is a concrete file with a real size cost and a fixed set of glyphs.

## Example
"Times New Roman Bold Italic" is one font within the Times New Roman typeface. Regular, Bold, and Italic are each their own font in that family.

## Common mistake
Assuming a font carries every weight and style. A single font file is usually one cut; each additional weight or style is its own file you have to load. Forget that and you either ship a heavy page (loading cuts you never use) or ask for a weight that isn't there, so the browser fakes it (see [faux-bold](faux-bold.md)). A [variable-font](variable-font.md) is the exception: one file that produces many styles.

## In practice
- **Performance and tokens:** weights and styles are separate files to load, so load only the cuts you actually use. A variable font folds many cuts into one file, which can be lighter when you need several weights. Reference the family as one token and the specific cuts (weight, style) as their own decisions.
- **Tools:** in Figma you pick the typeface, then the specific font (the style dropdown). In CSS, `@font-face` declares each font file, and `font-family`, `font-weight`, and `font-style` select among the ones you loaded. See [Explore text properties (Figma Help)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties).
- **Languages:** a font only contains glyphs for the scripts it was drawn for. When text needs a character the font lacks, the system falls back to another font or shows an empty box. Confirm your fonts cover every script your product ships in.

## Related terms
[Typeface](typeface.md) · [Font weight](font-weight.md) · [Variable font](variable-font.md) · [Faux bold](faux-bold.md)

## Further reading
- Foundations: [Typeface vs Font: what's the difference? (TypeType)](https://typetype.org/blog/font-and-typeface-what-s-the-difference/)
- Resource library: [Font (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/font)
