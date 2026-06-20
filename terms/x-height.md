---
term: x-height
slug: x-height
aliases: [corpus size]
tags: [typography]
level: foundational
depth: deep
summary: The x-height is the height of a typeface's lowercase letters without ascenders or descenders.
related: [cap-height, baseline, ascender, descender]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "x-height (Google Fonts Knowledge)"
    url: https://fonts.google.com/knowledge/glossary/x_height
    type: resource
license: CC-BY-4.0
---

## Definition
The x-height is the height of a typeface's lowercase letters without ascenders or descenders.

## Why it matters
Named for the lowercase "x," it is the distance from the [baseline](baseline.md) to the top of letters like "x," "v," and "z". It does a lot of quiet work: a large x-height makes a typeface look bigger at the same point size and generally reads better at small sizes, though it usually comes with shorter [ascender](ascender.md)s and [descender](descender.md)s. It is one of the best quick signals of how a typeface will actually feel in an interface.

## Example
At the same point size, a font with a tall x-height looks larger than one with a small x-height.

## Common mistake
Comparing typefaces by point size alone. Two fonts set at 16px can look noticeably different in size because their x-heights differ, so matching or swapping typefaces purely by the number in the size field will surprise you. The point size is the box; the x-height is how full that box looks.

## In practice
- **Readability and accessibility:** a larger x-height improves legibility at small sizes and for low-vision readers, which is why it is a real selection criterion for UI body text and captions, not just an aesthetic detail.
- **Tokens and typeface swaps:** because x-height drives apparent size, changing the font-family token can shift how large everything reads even when every size token stays identical. After swapping a typeface, re-check optical sizing rather than trusting the unchanged numbers.
- **Pairing:** when combining two typefaces, matching their x-heights (not their point sizes) keeps them looking balanced together.

## Related terms
[Cap height](cap-height.md) · [Baseline](baseline.md) · [Ascender](ascender.md) · [Descender](descender.md)

## Further reading
- Resource library: [x-height (Google Fonts Knowledge)](https://fonts.google.com/knowledge/glossary/x_height)
