---
term: Harakat
slug: harakat
aliases:
  - tashkil
  - arabic vowel marks
level: advanced
depth: core
summary: Harakat are the optional vowel marks of the Arabic script, written above and below the consonants to show short vowels.
related:
  - arabic-script
  - abjad
  - diacritic
  - mark
  - combining-mark
  - precomposed-character
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Harakat (Unicode Glossary)
    url: https://www.unicode.org/glossary/#harakat
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Harakat

## Definition

Harakat are the optional vowel marks of the [Arabic script](arabic-script.md), written above and below the consonants to show short vowels.

For example, the Arabic letter `ب` (b) takes a different short vowel with each mark: `بَ` (ba), `بِ` (bi), `بُ` (bu).

### Why it matters in design systems

The Arabic script is an [abjad](abjad.md): it writes consonants and long vowels, while short vowels are normally left out and supplied by the reader. Harakat are the optional marks that spell those short vowels out when needed, for example in the Quran, in children's books, in dictionaries, and anywhere ambiguity has to be removed.<sup>1</sup> They are combining [mark](../language-terms/writing-systems-and-scripts/mark.md)s layered on the base letters, so in software a letter plus its harakat is a sequence, not a single [precomposed character](precomposed-character.md). That has direct consequences: search and matching usually need to ignore harakat so a word is found whether or not it is voweled, and input methods have to let users add the marks.

***

### Related terms and mentions

[Abjad](abjad.md) · [Arabic script](arabic-script.md) · [Combining mark](../programming-terms/combining-mark.md) · [Diacritic](../language-terms/writing-systems-and-scripts/diacritic.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Precomposed character](precomposed-character.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Harakat (Unicode Glossary)](https://www.unicode.org/glossary/#harakat)

### Sources

1. Harakat are marks used in the Arabic script to indicate short vowels, a subtype of tashkil - Unicode Glossary: Harakat [https://www.unicode.org/glossary/#harakat](https://www.unicode.org/glossary/#harakat)
