---
term: Typeface
slug: typeface
aliases: [type family, font family]
tags: [typography]
level: foundational
depth: deep
summary: A typeface is the overall design of a set of letters, numbers, and symbols that share a common visual style.
related: [font, font-weight, variable-font]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Typeface vs Font: what's the difference? (TypeType)"
    url: https://typetype.org/blog/font-and-typeface-what-s-the-difference/
    type: authority
  - title: "Typeface (Google Fonts Knowledge)"
    url: https://fonts.google.com/knowledge/glossary/typeface
    type: resource
license: CC-BY-4.0
---

## Definition
A typeface is the overall design of a set of letters, numbers, and symbols that share a common visual style.

## Why it matters
This is the design itself, the artwork, separate from any one file that delivers it. A typeface is the whole family (Helvetica, a widely used sans-serif), and a [font](font.md) is one specific instance inside it (Helvetica Bold at 12pt). In everyday speech people swap the two words freely, and that is fine in conversation. It starts to bite the moment you are specifying type for a real product, because "use Helvetica" does not tell anyone which weight or style, and a design system needs that precision.

## Example
Helvetica is a typeface: a sans-serif design (one without the small finishing strokes that serif designs have). "Helvetica Bold 12pt" is a font within it, one specific weight and size drawn from that design.

## Common mistake
Treating a typeface as a single thing you can just "apply," when what you actually ship is a set of fonts: regular, bold, italic, and so on. If you pick a typeface that only ships a regular weight and then ask for bold anyway, the tool or browser may fake it (see [faux-bold](faux-bold.md)), which distorts the letterforms. Choosing a typeface means checking that the family actually includes the weights and styles your design depends on.

## In practice
- **Tokens:** the typeface (the family name) is usually one token, like a `font-family` value, while the weights and styles it contains are separate decisions ([font-weight](font-weight.md), italics). Keeping the family as its own token lets you swap the whole typeface in one place without rewriting every weight reference.
- **Tools:** in Figma the font picker selects the typeface (the family); the weight and style dropdown then picks the specific font within it. The CSS equivalent is `font-family` naming the typeface, with `font-weight` and `font-style` selecting the cut. See [Explore text properties (Figma Help)](https://help.figma.com/hc/en-us/articles/360039956634-Explore-text-properties).
- **Languages:** a typeface only covers the scripts it was drawn for. A Latin-only typeface has no glyphs for Arabic or Devanagari, so multilingual products either choose a typeface with broad script coverage or pair a primary typeface with fallbacks. Confirm coverage before committing to a typeface for a multilingual interface.

## Related terms
[Font](font.md) · [Font weight](font-weight.md) · [Variable font](variable-font.md)

## Further reading
- Foundations: [Typeface vs Font: what's the difference? (TypeType)](https://typetype.org/blog/font-and-typeface-what-s-the-difference/)
- Resource library: [Typeface (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/typeface)
