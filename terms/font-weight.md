---
term: Font weight
slug: font-weight
aliases: [weight]
tags: [typography]
level: foundational
depth: deep
summary: Font weight is the thickness of a typeface's strokes, ranging from very thin to very heavy.
tool_names:
  figma: Weight
  css: font-weight
related: [faux-bold, variable-font, typeface]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "font-weight (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight
    type: code
  - title: "Introducing weights & styles (Google Fonts Knowledge)"
    url: https://fonts.google.com/knowledge/introducing_type/introducing_weights_styles
    type: resource
license: CC-BY-4.0
---

# Font weight

## Definition
Font weight is the thickness of a typeface's strokes, ranging from very thin to very heavy.

## Why it matters
Weight is the dial that takes type from hairline-thin up through regular and bold to black. It is usually expressed as a number from 100 to 900, where regular is 400 and bold is 700. Those two carry most of the work in an interface, but the named steps in between (medium, semibold) are what let a type system signal hierarchy without changing the typeface.

## Example
Setting a heading to 700 (bold) makes its strokes noticeably thicker than body text at 400 (regular).

## Also called
Figma: Weight · CSS: `font-weight`. The numeric scale (100 to 900) is the portable way to name a weight across tools.

## Common mistake
Asking for a weight the family does not actually ship. If a typeface has no bold cut and you set bold anyway, the tool or browser may fake it (see [faux-bold](faux-bold.md)), which distorts the letters. A second trap: assuming named weights line up across families. One typeface's "Medium" is not guaranteed to match another's, so pin weights to numbers, not names, when consistency matters.

## In practice
- **Tokens:** define weights as named tokens that map to numeric values (regular to 400, bold to 700) so the numbers stay the portable source of truth and the names stay readable. Avoid hard-coding a family's idiosyncratic style names.
- **Variable fonts:** in a [variable-font](variable-font.md), weight is often a continuous axis, so any value in the supported range is usable, not just the named instances. That is what makes fine-tuned or animated weight possible from a single file.
- **Tools and CSS:** Figma sets weight through the style dropdown, or a Weight axis slider for variable fonts; CSS `font-weight` takes either a keyword or a number. See [font-weight (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight).

## Related terms
[Faux bold](faux-bold.md) · [Variable font](variable-font.md) · [Typeface](typeface.md)

## Further reading
- Code & specs: [font-weight (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight)
- Resource library: [Introducing weights & styles (Google Fonts Knowledge)](https://fonts.google.com/knowledge/introducing_type/introducing_weights_styles)
