---
term: Abjad
slug: abjad
aliases:
  - consonantal alphabet
level: intermediate
depth: core
summary: An abjad is a type of script in which each letter represents a consonant and vowels are usually left unwritten.
related:
  - alphabet
  - abugida
  - script
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Glossary: Abjad'
    url: https://www.unicode.org/glossary/#abjad
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Abjad

## Definition

An abjad is a type of [script](script.md) in which each letter represents a consonant and vowels are usually left unwritten.<sup>1</sup> The reader supplies the missing vowels from context, which is what sets an abjad apart from an [alphabet](alphabet.md), where consonants and vowels both get their own letters.<sup>2</sup> [Arabic](../../terms/arabic-script.md) and [Hebrew](../../terms/hebrew-script.md) are the abjads a design system is most likely to support.

For example, the Arabic greeting مرحبا ("hello") is written as a run of consonant letters, with the short vowels left for the reader to fill in.

While this glossary doesn't cover every script, here are some abjads to be aware of. Select a linked term to navigate to its glossary page.

| Script                                 | Languages                  | Example |
| -------------------------------------- | -------------------------- | ------- |
| [Arabic](../../terms/arabic-script.md) | Arabic, Persian, Urdu      | مرحبا   |
| [Hebrew](../../terms/hebrew-script.md) | Hebrew, Yiddish            |         |
| Syriac                                 | Syriac (a form of Aramaic) |         |

### Why it matters in design systems

Whether a script counts as an abjad is not even fixed: it describes how a script is used for a language. The Arabic script writes Arabic as an abjad, with short vowels omitted, but works as an [alphabet](alphabet.md) for languages such as Kashmiri or Uyghur, where every vowel is written.<sup>3</sup> So the abjad label is a fact about a language's [writing system](writing-system.md), not just its script.

Two consequences follow for a design system. First, direction: Arabic and Hebrew run right to left,<sup>4</sup> so supporting them pulls in [bidirectional text](bidirectional-text.md) handling the moment a Latin name or a number shares a line, and it can mean mirroring layout, not just swapping a font. Second, because short vowels are normally unwritten and appear only as optional [diacritic](diacritic.md) marks, the same consonant skeleton may be typed, stored, and searched with or without those marks, which affects input, search, and text matching.

***

### Related terms and mentions

[Abugida](abugida.md) · [Alphabet](alphabet.md) · [Arabic script](../../terms/arabic-script.md) · [Bidirectional text](bidirectional-text.md) · [Diacritic](diacritic.md) · [Hebrew script](../../terms/hebrew-script.md) · [Script](script.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Unicode Glossary: Abjad](https://www.unicode.org/glossary/#abjad)

### Sources

1. An abjad indicates only consonants - Unicode Glossary: Abjad [https://www.unicode.org/glossary/#abjad](https://www.unicode.org/glossary/#abjad)
2. An alphabet indicates both consonants and vowels - Unicode Glossary: Alphabet [https://www.unicode.org/glossary/#alphabet](https://www.unicode.org/glossary/#alphabet)
3. "When this script is used to represent the Arabic language, short vowels diacritics are omitted. In that case, the Arabic script is referred to as an 'abjad'... when this script is used to write some other languages (such as Kashmiri, Uighur, and most African languages), all vowels are represented, including short vowels. The Arabic script is then an 'alphabet'." - W3C: An Introduction to Writing Systems & Unicode [https://www.w3.org/International/questions/qa-scripts](https://www.w3.org/International/questions/qa-scripts)
4. "However, there are several scripts (such as Arabic or Hebrew) where the natural ordering of horizontal text in display is from right to left." - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
