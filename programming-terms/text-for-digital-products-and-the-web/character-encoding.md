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
updated: 2026-08-04
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

# Character encoding

## Definition

A character encoding is the rule for turning [characters](character.md) into bytes and back again.<sup>1</sup>

### Why it matters in design systems

A [code point](code-point.md) is a number, and a file is a sequence of bytes. The encoding is the agreement that bridges the two, and the agreement has to hold at both ends. Write bytes with one rule and read them with another, and the text does not merely look odd, it comes apart into different characters entirely. That failure has a name, mojibake, which the W3C defines as garbled characters generally caused by using the wrong character encoding to interpret the bytes in a string or file.<sup>2</sup>

The mechanism is worth seeing once, because it makes every future instance recognizable. The symbol `é` is stored in [UTF-8](utf-8.md) as two bytes, C3 and A9. Latin-1 is a single-byte encoding, so software reading those same bytes as Latin-1 finds two characters instead of one: C3 is `Ã` and A9 is `©`. The text becomes `Ã©`. Nothing was corrupted; each byte was simply read as a character it was never meant to be.

For a design system this is mostly a discipline question rather than a design one, but it is the discipline that decides whether a person's name survives the trip from a form field to a database to a rendered page. The modern answer is settled: use UTF-8 everywhere and declare it explicitly. It is the only encoding that covers every script Unicode has encoded, and the WHATWG Encoding Standard calls it the mandatory encoding for all things.<sup>3</sup>

### Common mistake

Not declaring the encoding, and trusting a default to be right. The classic bug is text saved as UTF-8 and read back as something else, or the reverse, and it hides through an entire test cycle because ASCII text survives the mismatch unchanged. It surfaces the first time a non-ASCII character appears: an accented name, a curly quotation mark, an emoji, a script other than Latin. By then the corrupted text is often already stored, so the fix is a data repair rather than a code change.

### In practice

* **Use UTF-8 everywhere, explicitly:** the WHATWG Encoding Standard requires that new protocols and formats, and existing formats deployed in new contexts, use UTF-8 exclusively.<sup>4</sup> Declare it rather than relying on a default: `<meta charset="utf-8">`, an HTTP `Content-Type` header with `charset=utf-8`, and UTF-8 for database tables, columns, and saved files. See the [Encoding Standard (WHATWG)](https://encoding.spec.whatwg.org/).
* **Match every hop:** editor, version control, database, API, and file all have to agree. A single mismatched step corrupts text for everything downstream of it, and the step that corrupts is rarely the one where the problem is noticed.
* **Test with content you cannot read:** paste a name in a script your team does not use into every form, then read it back from storage and render it. All-English test data cannot detect an encoding mismatch, which is exactly why these bugs reach production.

***

### Related terms and mentions

[Character](character.md) · [Code point](code-point.md) · [Glyph](glyph.md) · [Grapheme cluster](grapheme-cluster.md) · [Normalization](normalization.md) · [Punctuation mark](../../language-terms/writing-systems-and-scripts/punctuation-mark.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](unicode.md) · [UTF-8](utf-8.md) · [UTF-16](utf-16.md) · [Text in software](../text-in-software/)

### Further reading

* Code & specs: [Encoding Standard (WHATWG)](https://encoding.spec.whatwg.org/)
* Foundations: [Character encodings: Essential concepts (W3C)](https://www.w3.org/International/articles/definitions-characters/)

### Sources

1. "The character encoding reflects the way the coded character set is mapped to bytes for manipulation in a computer" - Character encodings: Essential concepts, W3C Internationalization [https://www.w3.org/International/articles/definitions-characters/](https://www.w3.org/International/articles/definitions-characters/)
2. "Garbled or incorrectly rendered or processed characters, generally caused by using the wrong character encoding to interpret the bytes in a string or file" - Internationalization Glossary, W3C Group Note: Mojibake [https://www.w3.org/TR/i18n-glossary/](https://www.w3.org/TR/i18n-glossary/)
3. "The problems outlined here go away when exclusively using UTF-8, which is one of the many reasons that is now the mandatory encoding for all things" - Encoding Standard, WHATWG, Security background [https://encoding.spec.whatwg.org/](https://encoding.spec.whatwg.org/)
4. "New protocols and formats, as well as existing formats deployed in new contexts, must use the UTF-8 encoding exclusively" - Encoding Standard, WHATWG, Names and labels [https://encoding.spec.whatwg.org/#names-and-labels](https://encoding.spec.whatwg.org/#names-and-labels)
