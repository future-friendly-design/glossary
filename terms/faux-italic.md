---
term: Faux italic
slug: faux-italic
aliases: [fake italic, synthetic oblique, faux oblique]
tags: [typography]
level: intermediate
depth: deep
summary: Faux italic is a fake slant created by tilting a regular font's glyphs rather than using a real italic design.
related: [faux-bold, typeface, variable-font]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "font-style (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-style
    type: code
license: CC-BY-4.0
---

# Faux italic

## Definition
Faux italic is a fake slant created by tilting a regular font's glyphs rather than using a real italic design.

## Why it matters
A true italic is usually redrawn, not just leaned over: it is more cursive, often narrower, and some letters change shape entirely (a single-story "a" in place of the upright two-story one). Faux italic skips all that and just shears the upright shapes to one side, which looks stiff next to a real italic. As with faux bold, it usually arrives by accident: a browser synthesizing a slant when no italic face exists, or text pasted from another tool.

## Example
A sloped version of a regular "a" is faux italic; a true italic may use a single-story cursive "a" instead, a different letterform rather than the same one tilted.

## Common mistake
Assuming italic just means slanted. Real italics change the letterforms; faking it only shears the uprights. This shows up whenever a chosen style has no true italic cut and the renderer slopes the regular instead, so designs that depend on italics need a typeface that actually ships one.

## In practice
- **CSS:** `font-style: italic` uses the real italic if the font has one and otherwise synthesizes a slant; `font-synthesis: none` (or `font-synthesis-style: none`) turns that faking off so a missing italic fails visibly. See [font-style (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style), which spells out the italic-versus-oblique distinction.
- **Languages:** the italic convention is largely a Latin-script idea. Many writing systems have no italic tradition, so applying a slant to them is meaningless at best and distorting at worst. Do not apply italic styling blindly across multilingual text.
- **Tools:** confirm the family includes a true italic before relying on it; if your design leans on italics, that becomes a typeface selection criterion, not an afterthought.

## Related terms
[Faux bold](faux-bold.md) · [Typeface](typeface.md) · [Variable font](variable-font.md)

## Further reading
- Code & specs: [font-style (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)
