---
term: Ligature
slug: ligature
aliases: []
tags: [shaping-layout]
level: foundational
depth: core
summary: A ligature is a single glyph that replaces two or more letters to avoid collisions or for style.
related: [glyph, gsub, opentype-features, conjunct]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "OpenType font features guide (MDN)"
    url: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/OpenType_fonts_guide
    type: code
  - title: "Ligatures (Butterick's Practical Typography)"
    url: https://practicaltypography.com/ligatures.html
    type: authority
license: CC-BY-4.0
---

## Definition
A ligature is a single glyph that replaces two or more letters to avoid collisions or for style.

## Why it matters
When adjacent letters clash or simply read better joined, a font can substitute one combined [[glyph]]; common examples are fi, fl, ff, ffi, and ffl. In [[opentype]] this is a [[gsub]] substitution, with standard ligatures (the "liga" feature) on by default and decorative ones ("dlig") optional. The idea generalizes well beyond Latin: some scripts, like Arabic, rely on required ligatures for correct spelling, and the related [[conjunct]] forms in Indic scripts work on the same substitution principle.

## Example
Typing "f" then "i" can render as a single "fi" glyph so the dot of the i does not crash into the hood of the f.

## Related terms
[[glyph]] · [[gsub]] · [[opentype-features]] · [[conjunct]]

## Further reading
- Code & specs: [OpenType font features guide (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/OpenType_fonts_guide)
- Foundations: [Ligatures (Butterick's Practical Typography)](https://practicaltypography.com/ligatures.html)
