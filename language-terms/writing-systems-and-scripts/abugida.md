---
term: Abugida
slug: abugida
aliases:
  - alphasyllabary
level: intermediate
depth: core
summary: >-
  An abugida is a type of script where each consonant carries a built-in vowel
  that added marks change to write a different one.
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

An abugida is a type of [script](script.md) where each consonant carries a built-in vowel that added marks change to write a different one.<sup>1</sup> Most [Brahmic scripts](brahmic-scripts.md), the family that includes [Devanagari](devanagari.md), are abugidas.

For example, in Devanagari the consonant `क` stands for "ka", the consonant with its built-in "a" already included. Adding the i-[matra](matra.md) writes `कि` ("ki"), swapping the built-in vowel for a new one. The matra is typed after `क` but displays to its left, so software has to reorder it for display.<sup>2</sup>

This built-in vowel is what places an abugida between two other script types: an [alphabet](alphabet.md), which gives every consonant and vowel its own separate letter,<sup>3</sup> and an [abjad](abjad.md), which usually leaves vowels unwritten.<sup>4</sup>

The abugidas the glossary has an entry for are listed below; the list grows as new scripts are added. Select a linked term to navigate to its glossary page.

| Script                                  | Languages                | Example                                                              |
| --------------------------------------- | ------------------------ | -------------------------------------------------------------------- |
| [Bengali-Assamese](bengali-assamese.md) | Bengali, Assamese        | নমস্কার (nômôskar): "hello" (Bengali)                                |
| [Devanagari](devanagari.md)             | Hindi, Marathi, Sanskrit | नमस्ते (namaste): "hello"                                            |
| [Ethiopic (Geʽez)](ethiopic-script.md)  | Amharic, Tigrinya        | ሰላም (selam): "hello" (Amharic; literally "peace")                    |
| [Syloti Nagri](syloti-nagri.md)         | Sylheti                  | ꠍꠤꠟꠐꠤ ꠘꠣꠉꠞꠤ (Siloti Nagri): the script's own name                    |
| [Tamil](tamil-script.md)                | Tamil                    | வணக்கம் (vaṇakkam): "hello"                                          |
| [Thai](thai-script.md)                  | Thai                     | สวัสดี (sawatdee): "hello"                                           |
| [Tibetan](tibetan-script.md)            | Tibetan, Dzongkha        | བཀྲ་ཤིས་བདེ་ལེགས (tashi delek): a greeting, literally "good fortune" |

### Why it matters in design systems

The built-in vowel is the whole reason an abugida cannot be treated as a row of letters placed left to right. Its vowel [matra](matra.md)s can sit to the left, right, above, or below the consonant they belong to, and one typed after its consonant may need to display before it. That is [reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md), and it is a hallmark of [complex text layout](../../terms/complex-text-layout.md): the order text is stored in is not the order it is drawn in.

So an abugida needs real shaping support, not simple glyph-after-glyph placement, and a font passing a character-grid check can still lay these scripts out wrongly if its shaping rules are missing. When you scope support for a Brahmic language, treat the mark placement and reordering as the work, not an afterthought to picking a typeface with the right glyphs.

***

### Related terms and mentions

[Abjad](abjad.md) · [Alphabet](alphabet.md) · [Alphasyllabary](alphasyllabary.md) · [Bengali-Assamese script](bengali-assamese.md) · [Brahmic scripts](brahmic-scripts.md) · [Canadian Aboriginal Syllabics script](canadian-aboriginal-syllabics.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Devanagari script](devanagari.md) · [Ethiopic script](ethiopic-script.md) · [Font](../../terms/font.md) · [Glyph](../../terms/glyph.md) · [Matra](matra.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](script.md) · [Symbol](symbol.md) · [Syllabary](syllabary.md) · [Syloti Nagri script](syloti-nagri.md) · [Tamil script](tamil-script.md) · [Thai script](thai-script.md) · [Tibetan script](tibetan-script.md) · [Typeface](../../terms/typeface.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Unicode Glossary: Abugida](https://www.unicode.org/glossary/#abugida)

### Sources

1. An abugida's base letters carry an inherent vowel that additional distinguishing marks change - Unicode Glossary: Abugida [https://www.unicode.org/glossary/#abugida](https://www.unicode.org/glossary/#abugida)
2. In Devanagari the i-matra is stored after its consonant but displayed to its left, so it must be reordered for display - Microsoft: Developing OpenType Fonts for Devanagari Script [https://learn.microsoft.com/en-us/typography/script-development/devanagari](https://learn.microsoft.com/en-us/typography/script-development/devanagari)
3. An alphabet indicates both consonants and vowels - Unicode Glossary: Alphabet [https://www.unicode.org/glossary/#alphabet](https://www.unicode.org/glossary/#alphabet)
4. An abjad indicates only consonants - Unicode Glossary: Abjad [https://www.unicode.org/glossary/#abjad](https://www.unicode.org/glossary/#abjad)
