---
term: Faux bold
slug: faux-bold
aliases: [fake bold, synthetic bold]
tags: [typography]
level: intermediate
depth: deep
summary: Faux bold is fake boldness made by thickening a regular font's strokes instead of using a real bold design.
related: [faux-italic, font-weight, variable-font]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "font-synthesis (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis
    type: code
license: CC-BY-4.0
---

## Definition
Faux bold is fake boldness made by thickening a regular font's strokes instead of using a real bold design.

## Why it matters
A real bold is a separately drawn cut, with the spacing and proportions adjusted so it still looks right. Faux bold skips that and just smears the regular outlines thicker, which reads as uneven and a little clumsy once you notice it. It tends to sneak in rather than get chosen: text pasted from a tool like Word, or CSS asking for bold when the loaded font has no bold cut.

## Example
Word can "bold" a font that has no bold cut by thickening its outlines on the fly; a true bold is a separate, designed file with its own letterforms.

## Common mistake
Designing with bold when the family does not ship a real bold, so the renderer fakes it. The damage is worst in scripts where stroke contrast carries meaning, like Arabic, where synthetic thickening can distort the shapes. Good to know: Figma will not generate faux bold (it needs a real cut to switch to), but faux bold can still arrive in pasted text or from CSS that synthesizes weight.

## In practice
- **CSS:** `font-synthesis: none` (or `font-synthesis-weight: none`) tells the browser not to fake bold, so a missing weight fails visibly instead of smearing. Pair that with actually loading the bold face you want. See [font-synthesis (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis).
- **Languages and accessibility:** synthetic bold is especially harmful in non-Latin scripts; disable synthesis for those (for example `font-synthesis: none` scoped to `:lang(ar)`) and supply a real bold cut instead.
- **Tools:** before you lean on bold in a design, confirm the typeface includes a real bold. A [variable-font](variable-font.md) with a weight axis is one reliable way to get genuine heavier weights rather than faked ones.

## Related terms
[faux-italic](faux-italic.md) · [font-weight](font-weight.md) · [variable-font](variable-font.md)

## Further reading
- Code & specs: [font-synthesis (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis)
