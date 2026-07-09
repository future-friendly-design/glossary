---
term: GPOS
slug: gpos
aliases:
  - Glyph Positioning table
level: advanced
depth: core
summary: >-
  GPOS is the OpenType table that tells a font how to position glyphs, such as
  kerning and accent placement.
related:
  - gsub
  - opentype
  - opentype-features
  - text-shaping
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'GPOS: Glyph Positioning Table (Microsoft)'
    url: https://learn.microsoft.com/en-us/typography/opentype/spec/gpos
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# GPOS

## Definition

GPOS is the OpenType table that tells a font how to position glyphs, such as kerning and accent placement.

## Why it matters

The Glyph Positioning table stores rules that adjust where glyphs sit: [kerning](kerning.md) between pairs, [cursive joining](../language-terms/writing-systems-and-scripts/joining.md), and attaching marks like accents to their base. Positioning is applied after substitution, so GPOS works on the glyph sequence that [gsub](gsub.md) produced. Together GSUB and GPOS, which share the same script, feature, and lookup structures, drive most [opentype](opentype.md) layout behavior.

## Example

A GPOS rule shifts a combining accent so it sits centered over its base letter.

## Related terms

[GSUB](gsub.md) · [Joining](../language-terms/writing-systems-and-scripts/joining.md) · [Kerning](kerning.md) · [OpenType](opentype.md) · [OpenType features](opentype-features.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md)

## Further reading

* Foundations: [GPOS: Glyph Positioning Table (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/gpos)
