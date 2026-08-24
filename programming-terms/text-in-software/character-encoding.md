---
term: Character encoding
slug: character-encoding
aliases:
  - text encoding
  - charset
level: foundational
depth: deep
summary: A character encoding is the agreed way of turning characters into numbers a computer can store, and back again so it can be displayed as text in software.
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

A character encoding is the agreed way of turning [characters](character.md) into numbers a computer can store, and back again so it can be displayed as text in software.<sup>1</sup>

### Why it matters in design systems

A computer can only store numbers. Not letters, not shapes, only numbers. So to save the word "cat", something has to turn `c`, `a`, and `t` into numbers, and turn those numbers back into letters when the file is opened again.

For that to work, both ends have to agree on which number means which character. If the software that saves the text uses one character encoding and the software that opens it uses a different one, the text being shown as [glyphs](../text-for-digital-products-and-the-web/glyph.md) on the page will be different from the characters being stored in the code to represent the text.&#x20;

Early character encodings did both jobs at once: they listed the characters and set the numbers. Each had room for about 256 characters, which covered English and some European languages, and left no room for Devanagari, Chinese, or Amharic, because the people who built them were not designing for those languages. It is not possible to mix character encoding sources in one page or one database, which made supporting more than a few languages difficult.<sup>2</sup>

[Unicode](unicode.md) split that job in two. Unicode now owns the list, giving every character in every writing system its own number, called a [code point](code-point.md).<sup>3</sup> The character encoding owns the second half: the rule for writing those numbers into a file.<sup>4</sup>

That is why [UTF-8](utf-8.md) is not an alternative to Unicode. UTF-8 is one of Unicode's own encodings, and it can store every character Unicode has ever assigned, using between one and four numbers per character.<sup>5</sup> Latin-1 is one of the older lists for character encoding, still sitting in older files and databases.&#x20;

Unicode has more than one encoding. UTF-8 is the one to use for files and the web. [UTF-16](utf-16.md) is another, used inside some programming languages and operating systems, which is where surprising character counts in code usually come from.

Here is an example of character encoding for the same text across three different lists:

| Character | Unicode's number | Stored by UTF-8 as | Stored by Latin-1 as   |
| --------- | ---------------- | ------------------ | ---------------------- |
| `A`       | 65               | `41`               | `41`                   |
| `é`       | 233              | `C3 A9`            | `E9`                   |
| `न`       | 2344             | `E0 A4 A8`         | cannot store it at all |

Two things fall out of that table. Text written by one encoding and read by the other comes out wrong: save `é` as UTF-8 and it is stored as `C3 A9`, but Latin-1 reads each number as a whole character, so you get `Ã` and `©` instead. That failure has a name, mojibake.<sup>6</sup> And Latin-1 simply has no number for `न`, so a product using it cannot store that person's name at all. Not truncated, not garbled. Impossible.

### Common mistake

Assuming it is already handled. Encoding is invisible when it works, so nobody checks it, and every tool in the chain has a default that is probably UTF-8 but might not be. The bug then hides through the entire build, because English text looks identical under almost every encoding. It appears the first time somebody enters an accented name, a curly quotation mark, an emoji, or any script other than Latin. By then the broken text is usually already saved, which is what makes this expensive: you are repairing stored data, not changing code.

### In practice

The answer is always UTF-8. The WHATWG Encoding Standard requires that new formats and protocols, and existing ones used in new contexts, use it exclusively.<sup>7</sup> What a design systems team can actually do about it:

* **Ask what the whole chain uses.** Design tool, front end, database, API, exports, and any spreadsheet a translator opens. One step disagreeing corrupts everything after it, and the step that breaks it is rarely the one where anybody notices.
* **Test with text you cannot read.** Put a name in a script your team does not use into every form, save it, load it back, and look at it. Testing in English cannot find this class of bug, which is exactly why it reaches real users.
* **Learn to tell it apart from a font problem.** Text turning into `Ã©`-style rubble is an encoding failure: the right characters were stored, then read with the wrong list. Empty boxes are a [font coverage](../text-for-digital-products-and-the-web/font-coverage.md) failure: the right characters arrived, but the font has no [glyph](../text-for-digital-products-and-the-web/glyph.md) to draw them. The two look equally broken on screen and go to completely different people to fix.

***

### Related terms and mentions

[Character](character.md) · [Code point](code-point.md) · [Devanagari](../../language-terms/writing-systems-and-scripts/devanagari.md) · [Font](../text-for-digital-products-and-the-web/font.md) · [Font coverage](../text-for-digital-products-and-the-web/font-coverage.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [Grapheme cluster](grapheme-cluster.md) · [Normalization](normalization.md) · [Punctuation mark](../../language-terms/writing-systems-and-scripts/punctuation-mark.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](unicode.md) · [UTF-8](utf-8.md) · [UTF-16](utf-16.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Text in software](./)

### Further reading

* Code & specs: [Encoding Standard (WHATWG)](https://encoding.spec.whatwg.org/)
* Foundations: [Character encodings: Essential concepts (W3C)](https://www.w3.org/International/articles/definitions-characters/)

### Sources

1. "The character encoding reflects the way the coded character set is mapped to bytes for manipulation in a computer" - Character encodings: Essential concepts, W3C Internationalization [https://www.w3.org/International/articles/definitions-characters/](https://www.w3.org/International/articles/definitions-characters/)
2. "it is usually impossible to combine different encodings on the same Web page or in a database, so it is usually very difficult to support multilingual pages using 'legacy' approaches to encoding" - Character encodings: Essential concepts, W3C Internationalization [https://www.w3.org/International/articles/definitions-characters/](https://www.w3.org/International/articles/definitions-characters/)
3. "A coded character set is a set of characters for which a unique number has been assigned to each character" - Character encodings: Essential concepts, W3C Internationalization [https://www.w3.org/International/articles/definitions-characters/](https://www.w3.org/International/articles/definitions-characters/)
4. "Mapping from a character set definition to the actual code units used to represent the data" - Unicode Glossary: Character Encoding Form [https://www.unicode.org/glossary/#character\_encoding\_form](https://www.unicode.org/glossary/#character_encoding_form)
5. "The Unicode encoding form that assigns each Unicode scalar value to an unsigned byte sequence of one to four bytes in length" - Unicode Glossary: UTF-8 Encoding Form [https://www.unicode.org/glossary/#utf\_8\_encoding\_form](https://www.unicode.org/glossary/#utf_8_encoding_form)
6. "Garbled or incorrectly rendered or processed characters, generally caused by using the wrong character encoding to interpret the bytes in a string or file" - Internationalization Glossary, W3C Group Note: Mojibake [https://www.w3.org/TR/i18n-glossary/](https://www.w3.org/TR/i18n-glossary/)
7. "New protocols and formats, as well as existing formats deployed in new contexts, must use the UTF-8 encoding exclusively" - Encoding Standard, WHATWG, Names and labels [https://encoding.spec.whatwg.org/#names-and-labels](https://encoding.spec.whatwg.org/#names-and-labels)
