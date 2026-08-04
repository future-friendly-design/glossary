---
term: Character
slug: character
aliases: [abstract character]
tags: [characters-encoding]
level: foundational
depth: core
summary: A character is the basic unit of text that Unicode encodes and gives a number to.
related: [glyph, code-point, grapheme-cluster, unicode]
status: voice-passed
version_added: 0.1
updated: 2026-08-04
contributors: [sam-gordashko]
further_reading:
  - title: "Character (Unicode Glossary)"
    url: https://www.unicode.org/glossary/#character
    type: authority
license: CC-BY-4.0
---

# Character

## Definition

A character is the basic unit of text that Unicode encodes and gives a number to.<sup>1</sup>

For example, the symbol `A`, the digit `7`, and the Devanagari symbol `न` are each one character.

### Why it matters in design systems

A character is an abstract unit, not a picture. Unicode defines the abstract character as a unit of information used for organizing, controlling, or representing text,<sup>2</sup> which means the character is the thing being represented, and the [glyph](glyph.md) is only the shape a particular font draws for it. Change the font and every glyph changes; the characters underneath do not.

The word gets used for three different things at once, and separating them is what heads off a whole class of text bugs. A character is the encoded unit. A [code point](code-point.md) is the number assigned to it. A [grapheme cluster](grapheme-cluster.md) is what a reader counts as one character on screen, which is often several characters combined. The three agree for `A` and disagree for an accented symbol or an emoji, which is exactly where products break.

That gap decides real things. A field capped at "20 characters" will cut some names short and others in half depending on which unit it counts, and a search that compares characters directly will fail to match two spellings that look identical on screen. Neither is a translation problem; both are a counting problem, and the fix is choosing your unit deliberately rather than inheriting whichever one your database happened to use.

One naming note, because it causes real confusion in multilingual work. Unicode records a second, much older sense of the word: character is also the English name for the ideographic written elements of Chinese origin.<sup>3</sup> That is why the symbols of the [Han script](../../language-terms/writing-systems-and-scripts/han-characters.md) are called characters while the symbols of an alphabet are usually called letters. When a spec, an API, or this glossary says "character" without qualification, it means the encoded unit, not that sense.

***

### Related terms and mentions

[Alphabet](../../language-terms/writing-systems-and-scripts/alphabet.md) · [Character encoding](character-encoding.md) · [Code point](code-point.md) · [Font](font.md) · [Glyph](glyph.md) · [Grapheme](grapheme.md) · [Grapheme cluster](grapheme-cluster.md) · [Han characters](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Ideographic](../../language-terms/writing-systems-and-scripts/ideographic.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](unicode.md) · [Text in software](../text-in-software/)

### Further reading

* Foundations: [Character (Unicode Glossary)](https://www.unicode.org/glossary/#character)

### Sources

1. "The basic unit of encoding for the Unicode character encoding" - Unicode Glossary: Character, sense 3 [https://www.unicode.org/glossary/#character](https://www.unicode.org/glossary/#character)
2. "A unit of information used for the organization, control, or representation of textual data" - Unicode Glossary: Abstract Character [https://www.unicode.org/glossary/#abstract\_character](https://www.unicode.org/glossary/#abstract_character)
3. "The English name for the ideographic written elements of Chinese origin" - Unicode Glossary: Character, sense 4 [https://www.unicode.org/glossary/#character](https://www.unicode.org/glossary/#character)
