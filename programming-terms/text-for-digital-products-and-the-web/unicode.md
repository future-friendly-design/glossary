---
term: Unicode
slug: unicode
aliases: [The Unicode Standard]
tags: [characters-encoding]
level: foundational
depth: core
summary: Unicode is the standard that gives every character in the world's writing systems a unique number.
related: [code-point, character-encoding, utf-8, plane-bmp]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "What is Unicode? (unicode.org)"
    url: https://www.unicode.org/standard/WhatIsUnicode.html
    type: authority
license: CC-BY-4.0
---

# Unicode

## Definition
Unicode is the standard that gives every character in the world's writing systems a unique number.

## Why it matters
Maintained by the Unicode Consortium, Unicode defines a code space from U+0000 to U+10FFFF (about 1.1 million possible [code-point](code-point.md)s) and assigns characters, their properties, and rules for processing text. The key thing it does, and does not do: it defines characters and code points, not how they are stored as bytes (that is the role of an encoding like [utf-8](utf-8.md)) and not the shapes they take on screen (that is the role of a font's [glyph](glyph.md)s). It is the shared foundation that lets text move between systems, platforms, and languages without falling apart.

## Example
Unicode assigns the same code point to "€" whether you type it in Tokyo or Paris.

## Related terms
[Code point](code-point.md) · [Character encoding](character-encoding.md) · [UTF-8](utf-8.md) · [Plane / Basic Multilingual Plane](plane-bmp.md) · [Glyph](glyph.md)

## Further reading
- Foundations: [What is Unicode? (unicode.org)](https://www.unicode.org/standard/WhatIsUnicode.html)
