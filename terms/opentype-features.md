---
term: OpenType features
slug: opentype-features
aliases: [font features, feature tags]
tags: [shaping-layout]
level: intermediate
depth: deep
summary: OpenType features are switchable typographic behaviors in a font, each named by a short tag.
related: [opentype, gsub, gpos, ligature]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "OpenType font features guide (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/OpenType_fonts_guide
    type: code
  - title: "Feature tags (Microsoft OpenType spec)"
    url: https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags
    type: authority
license: CC-BY-4.0
---

## Definition
OpenType features are switchable typographic behaviors in a font, each named by a short tag.

## Why it matters
A feature is a packaged set of substitution or positioning rules identified by a four-letter tag: "liga" for standard ligatures, "smcp" for small caps, "tnum" for tabular figures, "kern" for kerning, and many more. Some features are on by default and required for a script to display correctly; others are optional stylistic choices a designer turns on. They are the user-facing handles on the [gsub](gsub.md) and [gpos](gpos.md) machinery, which is why so much typographic control comes down to enabling the right feature.

## Example
In CSS, `font-variant-numeric: tabular-nums` turns on the "tnum" feature so figures line up in columns, if the font provides it.

## Common mistake
Reaching for the low-level `font-feature-settings` for everything. It does not inherit the way normal properties do and it overrides the browser's defaults, so setting one feature can silently switch off others (including ones a script needs). It is also all-or-nothing per declaration. Prefer the high-level `font-variant-*` properties and keep `font-feature-settings` for features that have no high-level equivalent.

## In practice
- **Use high-level properties first:** `font-variant-ligatures`, `font-variant-caps`, `font-variant-numeric`, and friends map to features cleanly and cascade normally. See the [OpenType font features guide (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/OpenType_fonts_guide).
- **Confirm the font ships the feature:** a feature only does something if the font contains it; check coverage before relying on small caps, alternate figures, or stylistic sets. The registered tags are listed in the [Microsoft feature tags registry](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags).
- **Required vs optional:** treat default-on features as part of correct rendering (especially for non-Latin scripts) and only toggle the optional ones deliberately.

## Related terms
[OpenType](opentype.md) · [GSUB](gsub.md) · [GPOS](gpos.md) · [Ligature](ligature.md)

## Further reading
- Code & specs: [OpenType font features guide (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/OpenType_fonts_guide)
- Foundations: [Feature tags (Microsoft OpenType spec)](https://learn.microsoft.com/en-us/typography/opentype/spec/featuretags)
