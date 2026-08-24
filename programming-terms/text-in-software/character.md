---
term: Character
slug: character
aliases:
  - abstract character
level: foundational
depth: core
summary: A character is the basic unit of text that software encodes and numbers.
related:
  - glyph
  - code-point
  - grapheme-cluster
  - unicode
status: voice-passed
version_added: 0.1
updated: 2026-08-04T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Character (Unicode Glossary)
    url: https://www.unicode.org/glossary/#character
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Character

## Definition

A character is the basic unit of text that software encodes and numbers.<sup>1</sup> [Unicode](unicode.md), the standard for representing the world's writing systems in software, gives each character a unique identification number, known as a [code point](code-point.md).

For example, the English letter `A`, the numeral digit `7`, and the Devanagari symbol `न` are each one character.

{% hint style="info" %}
To avoid confusion when working with multi-language design systems, you should know:

The word carries a second, older sense. Unicode records that _character_ is also the English name for the ideographic written elements of Chinese origin,<sup>2</sup> the [symbols](../../language-terms/writing-systems-and-scripts/symbol.md) this glossary covers under [Han characters](../../language-terms/writing-systems-and-scripts/han-characters.md) and classifies as [logographic](../../language-terms/writing-systems-and-scripts/logographic.md).

When a spec, an API, or this glossary says "character" without qualification, it means the encoded unit, not that sense.
{% endhint %}



### Why it matters in design systems

Unicode defines character as an abstract unit of information used for organizing, controlling, or representing text.<sup>3</sup> In software, when you change the font used to visualize text in a particular language, the [glyphs](../text-for-digital-products-and-the-web/glyph.md) will change but the characters they represent remain the same.

For languages with a writing system that combines marks and symbols to change the meaning of a single character, a [grapheme cluster](grapheme-cluster.md) is what a reader counts as one character on screen, which is often several characters combined.&#x20;

For example, `é` can be one character or two. A reader sees one either way, but stored as a single [precomposed character](precomposed-character.md) it is one, and stored as the letter `e` followed by a combining acute accent mark it is technically two.

This matters in search indexing and when your design system has form inputs with character counters. You need to be sure the software is counting the grapheme cluster as a single character `é` to match the mental model of the person filling in the form. In search it's important to use [normalization](normalization.md) to ensure search results are accurate regardless of whether the same name was typed as a precomposed `é` or as `e` plus an accent.<sup>4</sup>&#x20;



***

### Related terms and mentions

[Alphabet](../../language-terms/writing-systems-and-scripts/alphabet.md) · [Character encoding](character-encoding.md) · [Code point](code-point.md) · [Combining mark](combining-mark.md) · [Font](../text-for-digital-products-and-the-web/font.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [Grapheme](grapheme.md) · [Grapheme cluster](grapheme-cluster.md) · [Han characters](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Ideographic](../../language-terms/writing-systems-and-scripts/ideographic.md) · [Language](../../language-terms/linguistics/language.md) · [Logographic](../../language-terms/writing-systems-and-scripts/logographic.md) · [Normalization](normalization.md) · [Precomposed character](precomposed-character.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](unicode.md) · [Writing system](../../language-terms/writing-systems-and-scripts/writing-system.md) · [Text in software](./)

### Further reading

* Foundations: [Character (Unicode Glossary)](https://www.unicode.org/glossary/#character)

### Sources

1. "The basic unit of encoding for the Unicode character encoding" - Unicode Glossary: Character, sense 3 [https://www.unicode.org/glossary/#character](https://www.unicode.org/glossary/#character)
2. "The English name for the ideographic written elements of Chinese origin" - Unicode Glossary: Character, sense 4 [https://www.unicode.org/glossary/#character](https://www.unicode.org/glossary/#character)
3. "A unit of information used for the organization, control, or representation of textual data" - Unicode Glossary: Abstract Character [https://www.unicode.org/glossary/#abstract\_character](https://www.unicode.org/glossary/#abstract_character)
4. "A process of removing alternate representations of equivalent sequences from textual data, to convert the data into a form that can be binary-compared for equivalence" - Unicode Glossary: Normalization [https://www.unicode.org/glossary/#normalization](https://www.unicode.org/glossary/#normalization)
