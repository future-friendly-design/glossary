---
term: Variable font
slug: variable-font
aliases: [VF, OpenType variable font]
tags: [typography]
level: intermediate
depth: deep
summary: A variable font is a single font file that can produce many styles by adjusting continuous sliders called axes.
related: [font-weight, typeface, font, font-subsetting]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Variable fonts guide (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide
    type: code
  - title: "OpenType Font Variations overview (Microsoft Learn)"
    url: https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview
    type: authority
  - title: "Introducing variable fonts (Google Fonts Knowledge)"
    url: https://fonts.google.com/knowledge/introducing_type/introducing_variable_fonts
    type: resource
license: CC-BY-4.0
---

## Definition
A variable font is a single font file that can produce many styles by adjusting continuous sliders called axes.

## Why it matters
Built on OpenType Font Variations, a variable font packs a whole family's worth of weights and styles into one compact file. The five registered axes are weight (`wght`), width (`wdth`), italic (`ital`), slant (`slnt`), and optical size (`opsz`); a typeface can also define custom axes (named with uppercase four-letter tags, like `GRAD` for grade). Because the axes are continuous, any value in the supported range is available, not just the named instances, which is what makes fine-tuned and animated type possible.

## Example
One variable font file can render Thin, Regular, Bold, and every weight in between through its weight axis.

## Common mistake
Assuming a variable font is automatically the lighter choice. It bundles many styles into one file, which wins when you actually use several weights or widths. But a single variable file can be larger than one static cut, so if a design only needs Regular and Bold, two static fonts may download less. Decide based on how many styles you really use, not the format alone.

## In practice
- **Tokens and CSS:** prefer the high-level properties (`font-weight`, `font-stretch`, `font-style`, `font-optical-sizing`) over raw `font-variation-settings`, so values stay semantic and cascade normally; reserve `font-variation-settings` for custom axes. The weight axis lets [font-weight](font-weight.md) tokens take any value, not just the named steps. See the [Variable fonts guide (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide).
- **Performance:** one file covering many weights can cut the number of requests, but weigh that variable file against the few static cuts you would otherwise load before assuming it is smaller.
- **Tools:** Figma exposes a variable font's axes as sliders, so you can set a custom weight or width directly; confirm the axis values you design with are ones the build can reproduce.

## Related terms
[font-weight](font-weight.md) · [typeface](typeface.md) · [font](font.md) · [font-subsetting](font-subsetting.md)

## Further reading
- Code & specs: [Variable fonts guide (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/Variable_fonts_guide)
- Foundations: [OpenType Font Variations overview (Microsoft Learn)](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
- Resource library: [Introducing variable fonts (Google Fonts Knowledge)](https://fonts.google.com/knowledge/introducing_type/introducing_variable_fonts)
