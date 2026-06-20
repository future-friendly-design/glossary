---
term: Character encoding
slug: character-encoding
aliases: [text encoding, charset]
tags: [characters-encoding]
level: foundational
depth: deep
summary: A character encoding is the rule for turning characters into bytes and back again.
related: [utf-8, utf-16, unicode, code-point]
status: voice-passed
version_added: 0.1
updated: 2026-06-18
contributors: [sam-gordashko]
further_reading:
  - title: "Encoding Standard (WHATWG)"
    url: https://encoding.spec.whatwg.org/
    type: code
  - title: "Character encodings: Essential concepts (W3C)"
    url: https://www.w3.org/International/articles/definitions-characters/
    type: authority
license: CC-BY-4.0
---

## Definition
A character encoding is the rule for turning characters into bytes and back again.

## Why it matters
An encoding maps [code-point](code-point.md)s to sequences of bytes for storage or transmission, and back again, which is what lets a file of bytes be read as the text someone meant to write. Choose the wrong encoding when reading and you get garbled text, the failure mode known as mojibake. [utf-8](utf-8.md) is the dominant encoding on the web; older encodings like Latin-1 or Shift-JIS only cover limited character sets.

## Example
Reading a UTF-8 file as Latin-1 turns "é" into "Ã©".

## Common mistake
Not declaring the encoding, or trusting a default to be right. The classic mojibake bug is text saved as UTF-8 but read back as something else, or the reverse. It tends to stay hidden through all-ASCII testing and only surfaces when a non-ASCII character (an accented letter, a curly quote, an emoji) shows up as garbage in production.

## In practice
- **Use UTF-8 everywhere, explicitly:** the WHATWG Encoding Standard states that new formats and protocols must use UTF-8 exclusively. Declare it rather than relying on a default: `<meta charset="utf-8">`, an HTTP `Content-Type: ...; charset=utf-8` header, and UTF-8 for database tables, columns, and saved files. See the [Encoding Standard (WHATWG)](https://encoding.spec.whatwg.org/).
- **Match every hop:** editor, version control, database, API, and file all need to agree on UTF-8. A single mismatched step corrupts text for everything downstream.
- **Be careful with the BOM:** avoid a UTF-8 byte-order mark unless a specific consumer requires it, since some tools mishandle it.

## Related terms
[UTF-8](utf-8.md) · [UTF-16](utf-16.md) · [Unicode](unicode.md) · [Code point](code-point.md)

## Further reading
- Code & specs: [Encoding Standard (WHATWG)](https://encoding.spec.whatwg.org/)
- Foundations: [Character encodings: Essential concepts (W3C)](https://www.w3.org/International/articles/definitions-characters/)
