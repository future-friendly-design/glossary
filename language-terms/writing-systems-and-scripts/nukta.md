---
term: Nukta
slug: nukta
aliases: []
level: advanced
depth: core
summary: >-
  A nukta is a dot added below a consonant in many Indic scripts to extend the
  script to sounds the base letters do not cover.
related:
  - matra
  - virama
  - diacritic
  - mark
  - combining-mark
  - devanagari
  - precomposed-character
  - normalization
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Nuqta (Wikipedia)
    url: https://en.wikipedia.org/wiki/Nuqta
    type: authority
license: CC-BY-4.0
tags:
  - shaping-layout
---

# Nukta

## Definition

A nukta is a dot added below a consonant in many Indic scripts to extend the script to sounds the base letters do not cover.

For example, in [Devanagari](../../terms/devanagari.md) `क` (ka) plus a nukta becomes `क़` (qa), a sound that mainly came in through loanwords.

### Why it matters in design systems

A nukta (the word means "dot") is a small [combining mark](../../programming-terms/combining-mark.md) that sits beneath a consonant and changes the sound it represents, letting an [abugida](../../terms/abugida.md) such as Devanagari write sounds borrowed from other languages without inventing whole new letters. It belongs to the same family of attached marks as the vowel mark ([matra](matra.md)) and the vowel-killer ([virama](virama.md)). For software, two practical points follow. A base letter plus a nukta can often also be stored as a single [precomposed character](../../terms/precomposed-character.md), so the same word can exist in two forms that need [normalization](../../terms/normalization.md) to match.<sup>1</sup> And the nukta is one more combining [mark](mark.md) that the software laying out the text has to position correctly, since the standard encodes it immediately after its consonant.<sup>2</sup>

***

### Related terms and mentions

[Matra](matra.md) · [Virama](virama.md) · [Diacritic](diacritic.md) · [Mark](mark.md) · [Combining mark](../../programming-terms/combining-mark.md) · [Devanagari](../../terms/devanagari.md) · [Precomposed character](../../terms/precomposed-character.md) · [Normalization](../../terms/normalization.md) · [Language](../linguistics/language.md) · [Script](script.md)

### Further reading

* Foundations: [Nuqta (Wikipedia)](https://en.wikipedia.org/wiki/Nuqta)

### Sources

1. A precomposed character has a canonical decomposition to its base plus a combining mark, so the two spellings are equivalent and normalization makes them match - Unicode Glossary: Canonical Decomposition [https://www.unicode.org/glossary/#canonical\_decomposition](https://www.unicode.org/glossary/#canonical_decomposition)
2. The nukta modifies a consonant form and is placed immediately after the consonant in the memory representation - The Unicode Standard 17.0, Chapter 12 [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-12/)
