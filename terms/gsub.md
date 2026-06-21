---
term: GSUB
slug: gsub
aliases: [Glyph Substitution table]
tags: [shaping-layout]
level: advanced
depth: core
summary: GSUB is the OpenType table that tells a font when to swap one or more glyphs for others.
related: [gpos, opentype, opentype-features, ligature, text-shaping]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "GSUB: Glyph Substitution Table (Microsoft)"
    url: https://learn.microsoft.com/en-us/typography/opentype/spec/gsub
    type: authority
license: CC-BY-4.0
---

# GSUB

## Definition
GSUB is the OpenType table that tells a font when to swap one or more glyphs for others.

## Why it matters
The Glyph Substitution table stores the rules for replacing glyphs, which covers a lot of typographic behavior: ligatures, small caps, Arabic contextual forms, and Indic glyph rearrangement all live here. A [shaping-engine](shaping-engine.md) applies GSUB lookups in the order the [opentype](opentype.md) spec defines for each script, and substitution always happens before positioning. Its companion table, [gpos](gpos.md), handles where glyphs sit rather than which glyphs are used.

## Example
A GSUB rule replaces the glyph sequence f + i with a single fi [ligature](ligature.md) glyph.

## Related terms
[GPOS](gpos.md) · [OpenType](opentype.md) · [OpenType features](opentype-features.md) · [Ligature](ligature.md) · [Text shaping](text-shaping.md)

## Further reading
- Foundations: [GSUB: Glyph Substitution Table (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/spec/gsub)
