---
term: Character
slug: character
aliases:
  - abstract character
level: foundational
depth: core
summary: >-
  A character is the basic unit of text that Unicode encodes and gives a number
  to.
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

A character is the basic unit of measuring text in software. [Unicode](unicode.md), the authority for programming standards when it comes to encoding text, gives a unique identification number to each character in a writing system, known as a [code point](code-point.md).

For example, the english letter `A`, the numeral digit `7`, and the Devanagari symbol `न` are each one character.

{% hint style="info" %}
To avoid confusion when working with multi-language design systems, you should know:

In the study of linguistics, the term _character_ also refers to a specific classification of [symbols](../../language-terms/writing-systems-and-scripts/symbol.md) used in a [logographic](../../language-terms/writing-systems-and-scripts/logographic.md) writing system for languages such as Japanese, Korean, and Chinese.

When a spec, an API, or this glossary says "character" without qualification, it means the encoded unit, not that sense.
{% endhint %}



### Why it matters in design systems

Unicode defines character as an abstract unit of information used for organizing, controlling, or representing text.<sup>2</sup> In software, when you change the font used to visualize text in a particular language, the [glyphs](../text-for-digital-products-and-the-web/glyph.md) will change but the characters they represent remain the same.

For languages with a writing system that combines marks and symbols to change the meaning of a single character, a [grapheme cluster](grapheme-cluster.md) is what a reader counts as one character on screen, which is often several characters combined.&#x20;

For example, `é` can be counted as one character or two. Someone reading `é` sees the grapheme cluster as one [precomposed character](precomposed-character.md), when the letter `e` followed by a combining acute accent mark is two technically characters.

This matters in search indexing and when your design system has form inputs with character counters. You need to be sure the software is counting the grapheme cluster as a single character `é` to match the mental model of the person filling in the form. In search it's important to use [normalization](normalization.md) to ensure search results are accurate regardless if the same name was typed as `e` or `é.`&#x20;



***

### Related terms and mentions

[Alphabet](../../language-terms/writing-systems-and-scripts/alphabet.md) · [Character encoding](character-encoding.md) · [Code point](code-point.md) · [Font](../text-for-digital-products-and-the-web/font.md) · [Glyph](../text-for-digital-products-and-the-web/glyph.md) · [Grapheme](grapheme.md) · [Grapheme cluster](grapheme-cluster.md) · [Han characters](../../language-terms/writing-systems-and-scripts/han-characters.md) · [Ideographic](../../language-terms/writing-systems-and-scripts/ideographic.md) · [Script](../../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../../language-terms/writing-systems-and-scripts/symbol.md) · [Unicode](unicode.md) · [Text in software](./)

### Further reading

* Foundations: [Character (Unicode Glossary)](https://www.unicode.org/glossary/#character)

### Sources

1. "The basic unit of encoding for the Unicode character encoding" - Unicode Glossary: Character, sense 3 [https://www.unicode.org/glossary/#character](https://www.unicode.org/glossary/#character)
2. "A unit of information used for the organization, control, or representation of textual data" - Unicode Glossary: Abstract Character [https://www.unicode.org/glossary/#abstract\_character](https://www.unicode.org/glossary/#abstract_character)
3. "The English name for the ideographic written elements of Chinese origin" - Unicode Glossary: Character, sense 4 [https://www.unicode.org/glossary/#character](https://www.unicode.org/glossary/#character)
