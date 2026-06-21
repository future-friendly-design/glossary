---
term: OpenType
slug: opentype
aliases: [OTF, OpenType font format]
tags: [shaping-layout]
level: foundational
depth: core
summary: OpenType is the modern, cross-platform font file format that supports advanced typography and large character sets.
related: [opentype-features, gsub, gpos, glyph, font]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "OpenType overview (Microsoft)"
    url: https://learn.microsoft.com/en-us/typography/opentype/
    type: authority
license: CC-BY-4.0
---

# OpenType

## Definition
OpenType is the modern, cross-platform font file format that supports advanced typography and large character sets.

## Why it matters
Developed jointly by Microsoft and Adobe and released in 1997, OpenType extends the older TrueType structure and can carry either TrueType or PostScript glyph outlines. The same font file works on macOS and Windows, can hold tens of thousands of glyphs, and stores layout rules in tables such as [gsub](gsub.md) and [gpos](gpos.md). It is Unicode-based, which is what lets a single OpenType font support many writing systems at once, and it is the format the rest of this category's machinery operates on.

## Example
A single OpenType font can include small caps, ligatures, and multiple language scripts in one file.

## Related terms
[OpenType features](opentype-features.md) · [GSUB](gsub.md) · [GPOS](gpos.md) · [Glyph](glyph.md) · [Font](font.md)

## Further reading
- Foundations: [OpenType overview (Microsoft)](https://learn.microsoft.com/en-us/typography/opentype/)
