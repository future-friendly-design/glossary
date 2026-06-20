---
term: Small caps
slug: small-caps
aliases: [small capitals]
tags: [typography]
level: intermediate
depth: deep
summary: Small caps are uppercase letter shapes drawn at roughly the height of lowercase letters.
related: [figure-styles, x-height, faux-bold]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "font-variant-caps (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-caps
    type: code
  - title: "Small caps (Butterick's Practical Typography)"
    url: https://practicaltypography.com/small-caps.html
    type: authority
license: CC-BY-4.0
---

## Definition
Small caps are uppercase letter shapes drawn at roughly the height of lowercase letters.

## Why it matters
True small caps are a distinct set of glyphs, with the stroke weight and spacing adjusted so they sit at home next to lowercase text. They are the polite way to set an acronym in running prose: "PhD" or "NASA" in small caps reads at the right size instead of shouting in full-height capitals. Their height is tuned around the [x-height](x-height.md), which is what lets them blend in.

## Example
"PhD" set in true small caps blends with running text instead of shouting in full-size capitals.

## Common mistake
Letting an app fake them. Faux small caps, made by just shrinking the capitals, come out too light in stroke and too tightly spaced, the same kind of distortion as [faux-bold](faux-bold.md). Butterick's advice is blunt: do not click the small-caps box in your word processor; use a font that actually ships small caps. In CSS, `font-variant-caps: small-caps` uses real small caps when the font has them and synthesizes them otherwise, so the same trap applies if the font lacks the glyphs.

## In practice
- **Tools and CSS:** set `font-variant-caps: small-caps` (the OpenType `smcp` feature) and confirm the font genuinely includes small caps, or the browser will fake them. See [font-variant-caps (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-caps).
- **Type styles:** bake small caps into a dedicated type style for the place you use them (acronyms, labels, legal lines) rather than applying them ad hoc, and add a touch of letterspacing, which small caps usually want.
- **Languages:** small caps are a cased-script idea (Latin, Greek, Cyrillic). Scripts without an uppercase/lowercase distinction, like Arabic, Hebrew, and CJK, have no small caps, so do not apply the styling to them.

## Related terms
[figure-styles](figure-styles.md) · [x-height](x-height.md) · [faux-bold](faux-bold.md)

## Further reading
- Code & specs: [font-variant-caps (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-caps)
- Foundations: [Small caps (Butterick's Practical Typography)](https://practicaltypography.com/small-caps.html)
