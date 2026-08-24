---
term: Character encoding
slug: character-encoding
aliases:
  - text encoding
  - charset
level: foundational
depth: deep
summary: >-
  A character encoding is the rule for turning characters into bytes and back
  again.
related:
  - utf-8
  - utf-16
  - unicode
  - code-point
status: voice-passed
version_added: 0.1
updated: 2026-08-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Encoding Standard (WHATWG)
    url: https://encoding.spec.whatwg.org/
    type: code
  - title: 'Character encodings: Essential concepts (W3C)'
    url: https://www.w3.org/International/articles/definitions-characters/
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Character encoding

## Definition

A character encoding is the rule for turning characters into bytes and back again.<sup>1</sup>

### Why it matters in design systems

Software does not store characters, it stores bytes. A [character](character.md) is an abstract unit of text, and its [code point](code-point.md) is the number Unicode gives it, but neither of those can go into a file as it is. A character encoding is the rulebook for turning those numbers into bytes and back again, and the same rulebook has to be used at both ends: once when the text is saved, and again when it is opened.

This is the part that usually gets skipped, and the W3C is explicit that the two ideas have to be kept apart.<sup>2</sup> [Unicode](unicode.md) and the encoding do different jobs. Unicode is the list: it decides which characters exist and gives each one a number.<sup>3</sup> The encoding is the storage rule: it decides how those numbers are written as data.<sup>4</sup> So [UTF-8](utf-8.md) is not an alternative to Unicode. It is one of Unicode's own encodings, which is why it can store any character Unicode has assigned.<sup>5</sup>

Older encodings work differently, and that is where most text corruption comes from. Latin-1 and Shift-JIS were built before Unicode, and each covers only a limited set of characters. You cannot mix them on one page or in one database, which the W3C describes as making multilingual pages very difficult to support, and which is the problem Unicode's single character set was created to solve.<sup>6</sup>

When text is saved under one rulebook and opened under another, it does not just look slightly wrong. Each byte gets read as a character it was never meant to be. Save `é` as UTF-8 and it is stored as two bytes. Read those same two bytes as Latin-1 and you get two separate characters, `Ã` and `©`. The name for this failure is mojibake: garbled characters caused by using the wrong character encoding to interpret the bytes in a string or file.<sup>7</sup>

### Common mistake

Not declaring the encoding, and trusting the default to be right. The classic version is text saved as UTF-8 and read back as something else, or the reverse. It survives an entire test cycle unnoticed, because English text is identical in most encodings. It shows up the first time someone enters an accented name, a curly quotation mark, an emoji, or any script other than Latin. By then the broken text is usually already saved, so fixing it means repairing data, not just changing code.

### In practice

* **Use UTF-8 everywhere, and say so:** the WHATWG Encoding Standard requires that new formats and protocols, and existing ones used in new contexts, use UTF-8 exclusively.<sup>8</sup> Declare it rather than relying on a default: `<meta charset="utf-8">` in your pages, `charset=utf-8` in the HTTP `Content-Type` header, and UTF-8 for database tables, columns, and saved files.
* **Every step has to agree:** editor, version control, database, API, and file. One mismatched step corrupts the text for everything after it, and the step that breaks it is rarely the one where anybody notices.
* **Test with text you cannot read:** put a name in a script your team does not use into every form, save it, load it back, and look at it. Testing in English cannot find an encoding problem, which is exactly why these reach production.

***

### Related terms and mentions

[Character](character.md) · [Code point](code-point.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [Grapheme cluster](grapheme-cluster.md) · [Normalization](normalization.md) · [Punctuation mark](../../language-terms/writing-systems-and-scripts/punctuation-mark.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](unicode.md) · [UTF-8](utf-8.md) · [UTF-16](utf-16.md) · [Text in software](./)

### Further reading

* Code & specs: [Encoding Standard (WHATWG)](https://encoding.spec.whatwg.org/)
* Foundations: [Character encodings: Essential concepts (W3C)](https://www.w3.org/International/articles/definitions-characters/)

### Sources

1. "The character encoding reflects the way the coded character set is mapped to bytes for manipulation in a computer" - Character encodings: Essential concepts, W3C Internationalization [https://www.w3.org/International/articles/definitions-characters/](https://www.w3.org/International/articles/definitions-characters/)
2. "It is important to clearly distinguish between the concepts of a character set versus a character encoding" - Character encodings: Essential concepts, W3C Internationalization [https://www.w3.org/International/articles/definitions-characters/](https://www.w3.org/International/articles/definitions-characters/)
3. "A coded character set is a set of characters for which a unique number has been assigned to each character" - Character encodings: Essential concepts, W3C Internationalization [https://www.w3.org/International/articles/definitions-characters/](https://www.w3.org/International/articles/definitions-characters/)
4. "Mapping from a character set definition to the actual code units used to represent the data" - Unicode Glossary: Character Encoding Form [https://www.unicode.org/glossary/#character\_encoding\_form](https://www.unicode.org/glossary/#character_encoding_form)
5. "The Unicode encoding form that assigns each Unicode scalar value to an unsigned byte sequence of one to four bytes in length" - Unicode Glossary: UTF-8 Encoding Form [https://www.unicode.org/glossary/#utf\_8\_encoding\_form](https://www.unicode.org/glossary/#utf_8_encoding_form)
6. "it is usually impossible to combine different encodings on the same Web page or in a database, so it is usually very difficult to support multilingual pages using 'legacy' approaches to encoding. The Unicode Consortium provides a large, single character set that aims to include all the characters needed for any writing system in the world" - Character encodings: Essential concepts, W3C Internationalization [https://www.w3.org/International/articles/definitions-characters/](https://www.w3.org/International/articles/definitions-characters/)
7. "Garbled or incorrectly rendered or processed characters, generally caused by using the wrong character encoding to interpret the bytes in a string or file" - Internationalization Glossary, W3C Group Note: Mojibake [https://www.w3.org/TR/i18n-glossary/](https://www.w3.org/TR/i18n-glossary/)
8. "New protocols and formats, as well as existing formats deployed in new contexts, must use the UTF-8 encoding exclusively" - Encoding Standard, WHATWG, Names and labels [https://encoding.spec.whatwg.org/#names-and-labels](https://encoding.spec.whatwg.org/#names-and-labels)
