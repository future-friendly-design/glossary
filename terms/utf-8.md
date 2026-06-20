---
term: UTF-8
slug: utf-8
aliases: []
tags: [characters-encoding]
level: foundational
depth: core
summary: UTF-8 is the most common way to store Unicode text, using one to four bytes per character.
related: [utf-16, character-encoding, unicode, code-point]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Encoding Standard (WHATWG)"
    url: https://encoding.spec.whatwg.org/
    type: code
  - title: "FAQ: UTF-8, UTF-16, UTF-32 & BOM (unicode.org)"
    url: https://www.unicode.org/faq/utf_bom.html
    type: authority
license: CC-BY-4.0
---

## Definition
UTF-8 is the most common way to store Unicode text, using one to four bytes per character.

## Why it matters
UTF-8 is a variable-width encoding: ASCII characters take a single byte, which makes it backward-compatible with ASCII, while other characters take two, three, or four bytes. It is by far the most popular text encoding on the web. Because it is byte-oriented and ASCII-compatible, it sidesteps the surrogate and byte-order headaches of [utf-16](utf-16.md). The practical guidance, use it everywhere and declare it, lives in [character-encoding](character-encoding.md).

## Example
"A" is one byte in UTF-8; "€" is three bytes; an emoji is four.

## Related terms
[utf-16](utf-16.md) · [character-encoding](character-encoding.md) · [unicode](unicode.md) · [code-point](code-point.md)

## Further reading
- Code & specs: [Encoding Standard (WHATWG)](https://encoding.spec.whatwg.org/)
- Foundations: [FAQ: UTF-8, UTF-16, UTF-32 & BOM (unicode.org)](https://www.unicode.org/faq/utf_bom.html)
