---
term: Grapheme
slug: grapheme
aliases: []
level: intermediate
depth: core
summary: >-
  A grapheme is a minimally distinctive unit of writing within a particular
  writing system.
related:
  - grapheme-cluster
  - glyph
  - character
  - code-point
status: voice-passed
version_added: 0.1
updated: 2026-08-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Grapheme (Unicode Glossary)
    url: https://www.unicode.org/glossary/#grapheme
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Grapheme

## Definition

A grapheme is a minimally distinctive unit of writing within a particular [writing system](../../language-terms/writing-systems-and-scripts/writing-system.md).<sup>1</sup>

Unicode's own example: `b` and `d` are distinct graphemes in English writing because there are distinct words like "big" and "dig", while a slanted `a` and an upright `a` are not, because no word is distinguished by that difference.<sup>2</sup>

### Why it matters in design systems

A grapheme is the abstract written unit, the counterpart in writing to what a [phoneme](../../language-terms/linguistics/phoneme.md) is in speech. It belongs to a writing system, not to software: a community decides what counts as a distinct unit of its writing long before any of it is encoded.

That is the whole reason this term is worth keeping separate from the encoding vocabulary. Software's unit is the [character](character.md), and characters were assigned by Unicode to serve storage and interchange, not to match how a writing system counts itself. The two do not line up one to one. The same visible unit may be one character or two, depending on how it was typed or stored, and Unicode acknowledges the mismatch directly by giving "what a user thinks of as a character" as a second sense of grapheme.<sup>3</sup>

For a design system, the practical form of this is that "how many characters is this?" has more than one correct answer, and the one your readers use is the writing system's, not your database's. When a person from a language community tells you their name is five letters long, they are counting graphemes. When your validation says it is seven, it is counting characters. Neither is wrong, and the gap between them is where names get truncated, rejected, or mangled. The unit that gets closest to the reader's count in software is the [grapheme cluster](grapheme-cluster.md), which is what to reach for when a limit or a cursor has to behave the way a person expects.

Keep grapheme, [glyph](../text-for-digital-products-and-the-web/glyph.md), and [code point](code-point.md) distinct and most of the confusion dissolves: the grapheme is the unit of writing, the glyph is a drawn shape, and the code point is a stored number.

***

### Related terms and mentions

[Character](character.md) · [Code point](code-point.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [Grapheme cluster](grapheme-cluster.md) · [Language](../../language-terms/linguistics/language.md) · [Orthography](../../language-terms/writing-systems-and-scripts/orthography.md) · [Phoneme](../../language-terms/linguistics/phoneme.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](unicode.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Text in software](./)

### Further reading

* Foundations: [Grapheme (Unicode Glossary)](https://www.unicode.org/glossary/#grapheme)

### Sources

1. "A minimally distinctive unit of writing in the context of a particular writing system" - Unicode Glossary: Grapheme, sense 1 [https://www.unicode.org/glossary/#grapheme](https://www.unicode.org/glossary/#grapheme)
2. "‹b› and ‹d› are distinct graphemes in English writing systems because there exist distinct words like big and dig. Conversely, a lowercase italiform letter a and a lowercase Roman letter a are not distinct graphemes because no word is distinguished on the basis of these two different forms" - Unicode Glossary: Grapheme [https://www.unicode.org/glossary/#grapheme](https://www.unicode.org/glossary/#grapheme)
3. "What a user thinks of as a character" - Unicode Glossary: Grapheme, sense 2 [https://www.unicode.org/glossary/#grapheme](https://www.unicode.org/glossary/#grapheme)
