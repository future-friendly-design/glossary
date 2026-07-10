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

An abjad is a type of [script](script.md) in which each letter represents a consonant and vowels are usually left unwritten.<sup>1</sup> The [Arabic](arabic-script.md), [Hebrew](hebrew-script.md) and Syriac scripts are abjads.

For example, the Arabic greeting مرحبا ("hello") is written as a run of consonant letters, with the short vowels left for the reader to fill in.

The reader supplies the missing vowels from context, which is what sets an abjad apart from an [alphabet](alphabet.md), where consonants and vowels both get their own letters.<sup>2</sup>&#x20;

While this glossary doesn't cover every script, here are some abjads to be aware of. Select a linked term to navigate to its glossary page.

| Script                     | Languages                  | Example of Hello! |
| -------------------------- | -------------------------- | ----------------- |
| [Arabic](arabic-script.md) | Arabic, Persian, Urdu      |    مرحبا          |
| [Hebrew](hebrew-script.md) | Hebrew, Yiddish            |                   |
| Syriac                     | Syriac (a form of Aramaic) |                   |

### Why it matters in design systems

If your design system supports languages that have scripts in their [writing system](writing-system.md) that are classified as Abjad's, it can require quite a substantial difference in typography, code, and design decisions when compared to the most common languages to support (English and other scripts which are classified as alphabets).&#x20;

For example, [text direction](text-direction.md): Arabic and Hebrew run right to left,<sup>3</sup> so supporting them alongside english often means mirroring the entire layout of a component or pattern, and introducing complex text layouts and bidirectional text in code, its not as simple as choosing a new typeface and swapping a font. In contrast,&#x20;

While its tempting to think that all abjad's will share the same design system requirements, this is not the case; be sure to consider the specific [script rules](script-rules.md) and language-specific rules ([orthography](orthography.md)).It's important to note that script type, in this case abjad, is technically not fixed property of a script: it describes how a script is used for the writing system of a given language.

For example, the Arabic script writes Arabic as an abjad, with short vowels omitted, but works as an [alphabet](alphabet.md) for languages such as Kashmiri or Uyghur, where every vowel is written.<sup>4</sup> So the abjad label for the script is a fact about a language's [writing system](writing-system.md), not a universal property of the script.

***

### Related terms and mentions

[Abugida](abugida.md) · [Alphabet](alphabet.md) · [Arabic script](arabic-script.md) · [Bidirectional text](bidirectional-text.md) · [Diacritic](diacritic.md) · [Hebrew script](hebrew-script.md) · [Orthography](orthography.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Unicode Glossary: Abjad](https://www.unicode.org/glossary/#abjad)

### Sources

1. An abjad indicates only consonants - Unicode Glossary: Abjad [https://www.unicode.org/glossary/#abjad](https://www.unicode.org/glossary/#abjad)
2. An alphabet indicates both consonants and vowels - Unicode Glossary: Alphabet [https://www.unicode.org/glossary/#alphabet](https://www.unicode.org/glossary/#alphabet)
3. "However, there are several scripts (such as Arabic or Hebrew) where the natural ordering of horizontal text in display is from right to left." - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
4. "When this script is used to represent the Arabic language, short vowels diacritics are omitted. In that case, the Arabic script is referred to as an 'abjad'... when this script is used to write some other languages (such as Kashmiri, Uighur, and most African languages), all vowels are represented, including short vowels. The Arabic script is then an 'alphabet'." - W3C: An Introduction to Writing Systems & Unicode [https://www.w3.org/International/questions/qa-scripts](https://www.w3.org/International/questions/qa-scripts)
