---
term: Plane / Basic Multilingual Plane
slug: plane-bmp
aliases: [BMP, Unicode plane, supplementary plane]
tags: [characters-encoding]
level: intermediate
depth: core
summary: A plane is a block of 65,536 Unicode code points; the Basic Multilingual Plane is the first one, holding most common characters.
related: [code-point, surrogate-pair, utf-16, unicode]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Plane (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#plane
    type: authority
license: CC-BY-4.0
---

# Plane / Basic Multilingual Plane

## Definition
A plane is a block of 65,536 Unicode code points; the Basic Multilingual Plane is the first one, holding most common characters.

## Why it matters
Unicode is divided into 17 planes numbered 0 to 16, each containing 65,536 code points. Plane 0, the Basic Multilingual Plane (BMP), holds U+0000 to U+FFFF and covers almost all modern languages and common symbols. Planes 1 to 16 are the supplementary planes, used for historic scripts, additional CJK ideographs, emoji, and private-use characters. Characters in the supplementary planes need a [surrogate-pair](surrogate-pair.md) in [utf-16](utf-16.md), which is the root of the "emoji counts as length 2" quirk.

## Example
The letter "A" lives in the BMP, while most emoji live in supplementary planes.

## Related terms
[Code point](code-point.md) · [Surrogate pair](surrogate-pair.md) · [UTF-16](utf-16.md) · [Unicode](unicode.md)

## Further reading
- Foundations: [Plane (Unicode Glossary)](https://www.unicode.org/glossary/#plane)
