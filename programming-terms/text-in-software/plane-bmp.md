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

A plane is one slice of [Unicode](unicode.md)'s numbering range, 65,536 numbers long; the Basic Multilingual Plane is the first slice, and it holds most of the characters in everyday use.<sup>1</sup>

### Why it matters in design systems

Unicode's numbers run from zero to a little over one million. That is a lot of range to talk about at once, so the standard cuts it into 17 equal slices, called planes and numbered 0 to 16.<sup>2</sup> Each slice holds 65,536 numbers, one per possible character; an individual number in that range is a [code point](code-point.md).

Plane 0, the Basic Multilingual Plane (BMP), covers U+0000 to U+FFFF and holds almost all of the characters that modern languages use day to day, plus the common symbols.<sup>3</sup> Planes 1 to 16 are the supplementary planes,<sup>4</sup> used for historic [scripts](../../language-terms/writing-systems-and-scripts/script.md), additional [Han characters](../../language-terms/writing-systems-and-scripts/han-characters.md), emoji, and private-use characters.

The split shows up in product work because of how text gets stored. [UTF-16](utf-16.md), one common way of storing text, fits any BMP character into a single storage slot but needs two slots for anything above the BMP, in the form of a [surrogate pair](surrogate-pair.md). That is the root of the "emoji counts as length 2" quirk.

### Example

The letter `A` lives in the BMP, while most emoji live in supplementary planes.

***

### Related terms and mentions

[Character](character.md) · [Code point](code-point.md) · [Han characters](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Surrogate pair](surrogate-pair.md) · [Unicode](unicode.md) · [UTF-16](utf-16.md) · [Text in software](./)

### Further reading

* Foundations: [Plane (Unicode Glossary)](https://www.unicode.org/glossary/#plane)

### Sources

1. "A range of 65,536 (10000_16) contiguous Unicode code points, where the first code point is an integer multiple of 65,536" - Unicode Glossary: Plane [https://www.unicode.org/glossary/#plane](https://www.unicode.org/glossary/#plane)
2. "Planes are numbered from 0 to 16, with the number being the first code point of the plane divided by 65,536" - Unicode Glossary: Plane [https://www.unicode.org/glossary/#plane](https://www.unicode.org/glossary/#plane)
3. "The Basic Multilingual Plane (BMP, or Plane 0) contains the common-use characters for all the modern scripts of the world as well as many historical and rare characters" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/latest/core-spec/chapter-2/](https://www.unicode.org/versions/latest/core-spec/chapter-2/)
4. "Planes 1 through 16, consisting of the supplementary code points" - Unicode Glossary: Supplementary Planes [https://www.unicode.org/glossary/#supplementary\_planes](https://www.unicode.org/glossary/#supplementary_planes)
