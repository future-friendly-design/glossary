---
term: Ligature
slug: ligature
aliases: []
level: foundational
depth: core
summary: >-
  A ligature is a single glyph that replaces two or more letters to avoid
  collisions or for style.
related:
  - glyph
  - gsub
  - opentype-features
  - conjunct
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: OpenType font features guide (MDN)
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/OpenType_fonts_guide
    type: code
  - title: Ligatures (Butterick's Practical Typography)
    url: https://practicaltypography.com/ligatures.html
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# Ligature

## Definition

A ligature is a single glyph that replaces two or more letters to avoid collisions or for style.

## Why it matters

When adjacent letters clash or simply read better joined, a font can substitute one combined [glyph](glyph.md); common examples are fi, fl, ff, ffi, and ffl. In [opentype](opentype.md) this is a [gsub](gsub.md) substitution, with standard ligatures (the "liga" feature) on by default and decorative ones ("dlig") optional. The idea generalizes well beyond Latin: some scripts, like Arabic, rely on required ligatures for correct spelling, and the related [conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) forms in Indic scripts work on the same substitution principle.

## Example

Typing "f" then "i" can render as a single "fi" glyph so the dot of the i does not crash into the hood of the f.

## Related terms

[Glyph](glyph.md) · [GSUB](gsub.md) · [OpenType features](opentype-features.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [OpenType](opentype.md)

## Further reading

* Code & specs: [OpenType font features guide (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_fonts/OpenType_fonts_guide)
* Foundations: [Ligatures (Butterick's Practical Typography)](https://practicaltypography.com/ligatures.html)
