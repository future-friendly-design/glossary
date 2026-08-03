---
term: Abjad
slug: abjad
aliases:
  - consonantal alphabet
level: intermediate
depth: core
summary: >-
  An abjad is a type of script in which each letter represents a consonant and
  vowels are usually left unwritten.
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

An abjad is a type of [script](script.md) in which each letter represents a consonant and vowels are usually left unwritten.<sup>1</sup> The [Arabic](arabic-script.md), [Hebrew](hebrew-script.md), and Syriac scripts are abjads.

For example, the Arabic greeting مرحبا ("hello") is written as a sequence of consonant letters, with the short vowels left for the reader to fill in.

The reader supplies the missing vowels from context, which is what sets an abjad apart from an [alphabet](alphabet.md), where consonants and vowels both get their own letters.<sup>2</sup>

The abjads the glossary has an entry for are listed below, alongside a few other notable abjads not yet covered. Select a linked term to navigate to its glossary page.

| Script                     | Languages                  | Example                  |
| -------------------------- | -------------------------- | ------------------------ |
| [Arabic](arabic-script.md) | Arabic, Persian, Urdu      | marhaba (مرحبا): "hello" |
| [Hebrew](hebrew-script.md) | Hebrew, Yiddish            | shalom (שלום): "hello"   |
| Syriac                     | Syriac (a form of Aramaic) | shlama (ܫܠܡܐ): "hello"   |

### Why it matters in design systems

If your design system supports a language whose [writing system](writing-system.md) uses an abjad, that can require substantially different typography, code, and design decisions than the alphabets most projects start from, such as the Latin script used for English.

For example, [text direction](text-direction.md): Arabic and Hebrew run right to left,<sup>3</sup> so supporting them alongside English often means mirroring the entire layout of a component or pattern and handling complex text layouts and bidirectional text in code. It's not as simple as choosing a new typeface and swapping a font. In contrast, adding another same-direction alphabet is often much closer to that: choosing a font with the right coverage and moving on.

While it's tempting to think that all abjads share the same design system requirements, they don't; be sure to consider each script's specific [script rules](script-rules.md) and each language's [orthography](orthography.md). It's also worth noting that a script type, abjad in this case, is not a fixed property of a script: it describes how a script is used in the writing system of a given language.

For example, the Arabic script writes Arabic as an abjad, with short vowels omitted, but works as an [alphabet](alphabet.md) for languages such as Kashmiri or Uyghur, where every vowel is written.<sup>4</sup> So the abjad label for the script is a fact about a language's [writing system](writing-system.md), not a universal property of the script.

***

### Related terms and mentions

[Abugida](abugida.md) · [Alphabet](alphabet.md) · [Arabic script](arabic-script.md) · [Bidirectional text](bidirectional-text.md) · [Complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) · [Diacritic](diacritic.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Hebrew script](hebrew-script.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Orthography](orthography.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Typeface](../../design-terms/typography/typeface.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./) · [Typography](../../terms/typography.md)

### Further reading

* Foundations: [Unicode Glossary: Abjad](https://www.unicode.org/glossary/#abjad)

### Sources

1. An abjad indicates only consonants - Unicode Glossary: Abjad [https://www.unicode.org/glossary/#abjad](https://www.unicode.org/glossary/#abjad)
2. An alphabet indicates both consonants and vowels - Unicode Glossary: Alphabet [https://www.unicode.org/glossary/#alphabet](https://www.unicode.org/glossary/#alphabet)
3. "However, there are several scripts (such as Arabic or Hebrew) where the natural ordering of horizontal text in display is from right to left." - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
4. "When this script is used to represent the Arabic language, short vowels diacritics are omitted. In that case, the Arabic script is referred to as an 'abjad'... when this script is used to write some other languages (such as Kashmiri, Uighur, and most African languages), all vowels are represented, including short vowels. The Arabic script is then an 'alphabet'." - W3C: An Introduction to Writing Systems & Unicode [https://www.w3.org/International/questions/qa-scripts](https://www.w3.org/International/questions/qa-scripts)
