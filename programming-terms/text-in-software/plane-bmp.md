---
term: Plane / Basic Multilingual Plane
slug: plane-bmp
aliases: [BMP, Unicode plane, supplementary plane]
tags: [characters-encoding]
level: intermediate
depth: core
summary: A plane is one slice of Unicode's numbering range, 65,536 numbers long; the Basic Multilingual Plane is the first slice, and it holds most of the characters in everyday use.
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
A plane is one slice of [Unicode](unicode.md)'s numbering range, 65,536 numbers long; the Basic Multilingual Plane is the first slice, and it holds most of the characters in everyday use.

## Why it matters
Unicode's numbers run from zero to a little over one million. That is a lot of range to talk about at once, so the standard cuts it into 17 equal slices, called planes and numbered 0 to 16. Each slice holds 65,536 numbers, one per possible character; an individual number in that range is a [code point](code-point.md).

Plane 0, the Basic Multilingual Plane (BMP), covers U+0000 to U+FFFF and holds almost all of the characters that modern languages use day to day, plus the common symbols. Planes 1 to 16 are the supplementary planes, used for historic [scripts](../../language-terms/writing-systems-and-scripts/script.md), additional [Han characters](../../language-terms/writing-systems-and-scripts/han-characters.md), emoji, and private-use characters.

The split shows up in product work because of how text gets stored. [UTF-16](utf-16.md), one common way of storing text, fits any BMP character into a single storage slot but needs two slots for anything above the BMP, in the form of a [surrogate pair](surrogate-pair.md). That is the root of the "emoji counts as length 2" quirk.

## Example
The letter `A` lives in the BMP, while most emoji live in supplementary planes.

## Related terms
[Character](character.md) · [Code point](code-point.md) · [Han characters](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Surrogate pair](surrogate-pair.md) · [Unicode](unicode.md) · [UTF-16](utf-16.md)

## Further reading
- Foundations: [Plane (Unicode Glossary)](https://www.unicode.org/glossary/#plane)
