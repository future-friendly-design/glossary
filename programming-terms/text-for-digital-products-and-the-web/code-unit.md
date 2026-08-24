---
term: Code unit
slug: code-unit
aliases:
  - code value
level: intermediate
depth: core
summary: >-
  A code unit is the smallest unit of storage an encoding uses to represent
  text.
related:
  - code-point
  - utf-8
  - utf-16
  - surrogate-pair
status: voice-passed
version_added: 0.1
updated: 2026-08-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'String: length (MDN)'
    url: >-
      https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length
    type: code
  - title: Code Unit (Unicode Glossary)
    url: https://www.unicode.org/glossary/#code_unit
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Code unit

## Definition

A code unit is the smallest unit of storage an encoding uses to represent text.<sup>1</sup>

Its size depends on the encoding: [UTF-8](../text-in-software/utf-8.md) uses 8-bit code units, [UTF-16](../text-in-software/utf-16.md) uses 16-bit ones.<sup>2</sup>

### Why it matters in design systems

A [code point](../text-in-software/code-point.md) and a code unit answer different questions. The code point is the character's identity, the number Unicode assigned it. The code unit is a chunk of computer storage,<sup>3</sup> and how many of them a character needs depends entirely on which encoding is doing the storing. The same character is one code point always, but one, two, three, or four code units depending on the encoding.

This is worth a design systems reader's attention for one reason: the number your code reports as a string's "length" is usually a count of code units, and it is not the number your reader sees. In JavaScript, the length property returns the length of the string in UTF-16 code units,<sup>4</sup> and MDN is direct that this may not match the number of characters in the string.<sup>5</sup>

MDN's own example makes the gap visible. The Adlam text `𞤲𞥋𞤣𞤫`, in the script created for writing Fulani, reports a length of 8 while containing 4 code points.<sup>6</sup> A "maximum 8 characters" rule built on that number would accept four written units from a Fulani speaker and eight from an English one. The same rule, same code, wildly different experience depending on whose language it is.

So when you write a character limit into a spec, say which unit you mean. Code units are a storage detail that should almost never surface to a person. What a reader counts is closer to a [grapheme cluster](../text-in-software/grapheme-cluster.md), and that is the unit a user-facing limit should use.

***

### Related terms and mentions

[Character](../text-in-software/character.md) · [Character encoding](../text-in-software/character-encoding.md) · [Code point](../text-in-software/code-point.md) · [Grapheme cluster](../text-in-software/grapheme-cluster.md) · [Language](../../language-terms/linguistics/language.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Surrogate pair](../text-in-software/surrogate-pair.md) · [Unicode](../text-in-software/unicode.md) · [UTF-8](../text-in-software/utf-8.md) · [UTF-16](../text-in-software/utf-16.md) · [Text in software](../text-in-software/)

### Further reading

* Code & specs: [String: length (MDN)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
* Foundations: [Code Unit (Unicode Glossary)](https://www.unicode.org/glossary/#code_unit)

### Sources

1. "The minimal bit combination that can represent a unit of encoded text for processing or interchange" - Unicode Glossary: Code Unit [https://www.unicode.org/glossary/#code\_unit](https://www.unicode.org/glossary/#code_unit)
2. "The Unicode Standard uses 8-bit code units in the UTF-8 encoding form, 16-bit code units in the UTF-16 encoding form, and 32-bit code units in the UTF-32 encoding form" - Unicode Glossary: Code Unit [https://www.unicode.org/glossary/#code\_unit](https://www.unicode.org/glossary/#code_unit)
3. "Code units are particular units of computer storage" - The Unicode Standard, Core Specification, Chapter 3, definition D77 [https://www.unicode.org/versions/latest/core-spec/chapter-3/](https://www.unicode.org/versions/latest/core-spec/chapter-3/)
4. "The length data property of a String value contains the length of the string in UTF-16 code units" - String: length, MDN [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
5. "JavaScript uses UTF-16 encoding, where each Unicode character may be encoded as one or two code units, so it's possible for the value returned by length to not match the actual number of Unicode characters in the string" - String: length, MDN [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
6. "const adlam = "𞤲𞥋𞤣𞤫"; console.log(adlam.length); // 8 / console.log(\[...adlam].length); // 4" - String: length, MDN [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/String/length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
