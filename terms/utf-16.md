---
term: UTF-16
slug: utf-16
aliases: []
tags: [characters-encoding]
level: intermediate
depth: core
summary: UTF-16 stores Unicode text in 16-bit units, using one unit for common characters and two for the rest.
related: [utf-8, surrogate-pair, plane-bmp, character-encoding]
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

## Definition
UTF-16 stores Unicode text in 16-bit units, using one unit for common characters and two for the rest.

## Why it matters
A single 16-bit code unit covers the Basic Multilingual Plane (U+0000 to U+FFFF); characters beyond it need a [surrogate-pair](surrogate-pair.md) of two code units. UTF-16 is used internally by JavaScript, Java, and Windows, which is why string length in those environments counts code units rather than characters, a frequent source of bugs with emoji and other supplementary-plane characters. When you need to count or slice user-visible characters, work in [grapheme-cluster](grapheme-cluster.md)s instead.

## Example
In JavaScript, `"😀".length` is 2 because the emoji is a surrogate pair in UTF-16.

## Related terms
[UTF-8](utf-8.md) · [Surrogate pair](surrogate-pair.md) · [Plane / Basic Multilingual Plane](plane-bmp.md) · [Character encoding](character-encoding.md)

## Further reading
- Code & specs: [UTF-16 (MDN Glossary)](https://developer.mozilla.org/en-US/docs/Glossary/UTF-16)
- Foundations: [FAQ: UTF-8, UTF-16, UTF-32 & BOM (unicode.org)](https://www.unicode.org/faq/utf_bom.html)
