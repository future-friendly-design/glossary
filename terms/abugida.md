---
term: Abugida
slug: abugida
aliases:
  - alphasyllabary
level: intermediate
depth: core
summary: An abugida is a script where each consonant carries a built-in vowel that is changed by adding marks.
related:
  - alphabet
  - abjad
  - syllabary
  - brahmic-scripts
  - matra
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Glossary: Abugida'
    url: https://www.unicode.org/glossary/#abugida
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Abugida

## Definition

An abugida is a [script](../language-terms/writing-systems-and-scripts/script.md) where each consonant carries a built-in vowel that is changed by adding marks.<sup>1</sup> That makes it a middle path between an [alphabet](alphabet.md), which gives consonants and vowels their own separate letters,<sup>2</sup> and an [abjad](abjad.md), where vowels are usually left unwritten.<sup>3</sup> An abugida is also called an [alphasyllabary](alphasyllabary.md). Most [Brahmic scripts](brahmic-scripts.md), the family that includes [Devanagari](devanagari.md), are abugidas.

For example, in Devanagari the consonant `क` (ka) carries an inherent "a"; adding the i-matra writes `कि` (ki). The [matra](../language-terms/writing-systems-and-scripts/matra.md) is typed after `क` but displays to its left, so software has to reorder it for display.<sup>4</sup>

While this glossary doesn't cover every script, here are some abugidas to be aware of. Select a linked term to navigate to its glossary page.

| Script                                   | Languages                | Example |
| ---------------------------------------- | ------------------------ | ------- |
| [Devanagari](devanagari.md)              | Hindi, Marathi, Sanskrit | नमस्ते  |
| [Bengali-Assamese](bengali-assamese.md)  | Bengali, Assamese        |         |
| [Tamil](tamil-script.md)                 | Tamil                    |         |
| [Tibetan](tibetan-script.md)             | Tibetan, Dzongkha        |         |
| [Thai](thai-script.md)                   | Thai                     |         |
| [Ethiopic (Geʽez)](ethiopic-script.md)   | Amharic, Tigrinya        |         |
| [Canadian Aboriginal Syllabics](canadian-aboriginal-syllabics.md) | Cree, Ojibwe, Inuktitut | |

### Why it matters in design systems

The built-in vowel is the whole reason an abugida cannot be treated as a row of letters placed left to right. Its vowel [matra](../language-terms/writing-systems-and-scripts/matra.md)s can sit to the left, right, above, or below the consonant they belong to, and one typed after its consonant may need to display before it. That is [reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md), and it is a hallmark of [complex text layout](complex-text-layout.md): the order text is stored in is not the order it is drawn in.

So an abugida needs real shaping support, not simple glyph-after-glyph placement, and a font passing a character-grid check can still lay these scripts out wrongly if its shaping rules are missing. When you scope support for a Brahmic language, treat the mark placement and reordering as the work, not an afterthought to picking a typeface with the right glyphs.

***

### Related terms and mentions

[Abjad](abjad.md) · [Alphabet](alphabet.md) · [Alphasyllabary](alphasyllabary.md) · [Bengali-Assamese](bengali-assamese.md) · [Brahmic scripts](brahmic-scripts.md) · [Canadian Aboriginal Syllabics](canadian-aboriginal-syllabics.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Ethiopic script](ethiopic-script.md) · [Font](font.md) · [Glyph](glyph.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Syllabary](syllabary.md) · [Tamil script](tamil-script.md) · [Thai script](thai-script.md) · [Tibetan script](tibetan-script.md) · [Typeface](typeface.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Unicode Glossary: Abugida](https://www.unicode.org/glossary/#abugida)

### Sources

1. An abugida's base letters carry an inherent vowel that additional distinguishing marks change - Unicode Glossary: Abugida [https://www.unicode.org/glossary/#abugida](https://www.unicode.org/glossary/#abugida)
2. An alphabet indicates both consonants and vowels - Unicode Glossary: Alphabet [https://www.unicode.org/glossary/#alphabet](https://www.unicode.org/glossary/#alphabet)
3. An abjad indicates only consonants - Unicode Glossary: Abjad [https://www.unicode.org/glossary/#abjad](https://www.unicode.org/glossary/#abjad)
4. In Devanagari the i-matra is stored after its consonant but displayed to its left, so it must be reordered for display - Microsoft: Developing OpenType Fonts for Devanagari Script [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
