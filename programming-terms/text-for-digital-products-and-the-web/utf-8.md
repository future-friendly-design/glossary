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
updated: 2026-08-04
contributors: [sam-gordashko]
further_reading:
  - title: "Encoding Standard (WHATWG)"
    url: https://encoding.spec.whatwg.org/
    type: code
  - title: "UTF-8 Encoding Form (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#utf_8_encoding_form
    type: authority
license: CC-BY-4.0
---

# UTF-8

## Definition

UTF-8 is the most common way to store Unicode text, using one to four bytes per character.<sup>1</sup>

### Why it matters in design systems

UTF-8 is variable-width: a character takes as many bytes as it needs. The first 128 code points, the ASCII range, take exactly one byte each and are indistinguishable from ASCII itself, which is why UTF-8 slotted into a world already full of ASCII-based systems without breaking them.<sup>2</sup> It is the encoding the WHATWG calls the mandatory encoding for all things,<sup>3</sup> and the practical guidance, use it everywhere and declare it, lives in [character encoding](character-encoding.md).

The part worth knowing as a designer is what that variable width costs, because the cost is not distributed evenly across the world's writing systems. Unicode spells it out: many non-ideographic scripts take two bytes per code point, everything from U+0800 to U+FFFF takes three, and anything above U+FFFF takes four.<sup>4</sup> English text is close to one byte per character. The same sentence in Greek or Cyrillic is roughly double that, and in Devanagari, Thai, or Han characters roughly triple.

That has consequences that surface in unglamorous places. A database column defined as 20 *bytes* holds 20 English characters and perhaps 6 Devanagari ones, so a field that comfortably fits your team's names silently truncates a user's. Payload sizes, search index sizes, and any limit expressed in bytes rather than characters all shift depending on the script. When you specify a limit, specify the unit, and check what your database is actually counting.

***

### Related terms and mentions

[Character](character.md) · [Character encoding](character-encoding.md) · [Code point](code-point.md) · [Code unit](code-unit.md) · [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Han characters](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Thai script](../../language-terms/writing-systems-and-scripts/thai-script.md) · [Unicode](unicode.md) · [UTF-16](utf-16.md) · [Text in software](../text-in-software/)

### Further reading

* Code & specs: [Encoding Standard (WHATWG)](https://encoding.spec.whatwg.org/)
* Foundations: [UTF-8 Encoding Form (Unicode Glossary)](https://www.unicode.org/glossary/#utf_8_encoding_form)

### Sources

1. "The Unicode encoding form that assigns each Unicode scalar value to an unsigned byte sequence of one to four bytes in length" - Unicode Glossary: UTF-8 Encoding Form [https://www.unicode.org/glossary/#utf\_8\_encoding\_form](https://www.unicode.org/glossary/#utf_8_encoding_form)
2. "The UTF-8 encoding form maintains transparency for all of the ASCII code points (0x00..0x7F). That means Unicode code points U+0000..U+007F are converted to single bytes 0x00..0x7F in UTF-8 and are thus indistinguishable from ASCII itself" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/latest/core-spec/chapter-2/](https://www.unicode.org/versions/latest/core-spec/chapter-2/)
3. "The problems outlined here go away when exclusively using UTF-8, which is one of the many reasons that is now the mandatory encoding for all things" - Encoding Standard, WHATWG [https://encoding.spec.whatwg.org/](https://encoding.spec.whatwg.org/)
4. "Beyond the ASCII range of Unicode, many of the non-ideographic scripts are represented by two bytes per code point in UTF-8; all non-surrogate code points between U+0800 and U+FFFF are represented by three bytes; and supplementary code points above U+FFFF require four bytes" - The Unicode Standard, Core Specification, Chapter 2 [https://www.unicode.org/versions/latest/core-spec/chapter-2/](https://www.unicode.org/versions/latest/core-spec/chapter-2/)
