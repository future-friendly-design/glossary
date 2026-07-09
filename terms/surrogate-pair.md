---
term: Surrogate pair
slug: surrogate-pair
aliases: [surrogates]
tags: [characters-encoding]
level: advanced
depth: core
summary: A surrogate pair is two UTF-16 code units used together to represent a character beyond the Basic Multilingual Plane.
related: [utf-16, plane-bmp, code-point]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "UTF-16 (MDN Glossary)"
    url: https://developer.mozilla.org/en-US/docs/Glossary/UTF-16
    type: code
  - title: "FAQ: UTF-8, UTF-16, UTF-32 & BOM (unicode.org)"
    url: https://www.unicode.org/faq/utf_bom.html
    type: authority
license: CC-BY-4.0
---

# Surrogate pair

## Definition
A surrogate pair is two UTF-16 code units used together to represent a character beyond the Basic Multilingual Plane.

## Why it matters
[utf-16](utf-16.md) can encode characters above U+FFFF only by pairing a high surrogate (U+D800 to U+DBFF) with a low surrogate (U+DC00 to U+DFFF). Those surrogate code points are reserved and are not valid characters on their own, so a lone surrogate is invalid UTF-16. Surrogate pairs are why a single emoji counts as length 2 in JavaScript and other UTF-16-based environments; to avoid splitting one in half, iterate by code point (for example `for...of`) or by [grapheme-cluster](grapheme-cluster.md), never by raw index.

## Example
The emoji "😀" (U+1F600) is stored as the surrogate pair U+D83D U+DE00 in UTF-16.

## Related terms
[UTF-16](utf-16.md) · [Plane / Basic Multilingual Plane](plane-bmp.md) · [Code point](code-point.md) · [Grapheme cluster](grapheme-cluster.md)

## Further reading
- Code & specs: [UTF-16 (MDN Glossary)](https://developer.mozilla.org/en-US/docs/Glossary/UTF-16)
- Foundations: [FAQ: UTF-8, UTF-16, UTF-32 & BOM (unicode.org)](https://www.unicode.org/faq/utf_bom.html)
