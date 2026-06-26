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
  - devanagari
  - precomposed-character
  - normalization
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
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

## Why it matters

A nukta (the word means "dot") is a small combining sign that sits beneath a consonant and changes the sound it represents, letting an [abugida](abugida.md) such as Devanagari write sounds borrowed from other languages without inventing whole new letters. It belongs to the same family of attached signs as the vowel sign ([matra](matra.md)) and the vowel-killer ([virama](virama.md)). For software, two practical points follow. A base letter plus a nukta can often also be stored as a single [precomposed character](precomposed-character.md), so the same word can exist in two forms that need [normalization](normalization.md) to match. And the nukta is one more combining [mark](../language-terms/writing-systems-and-scripts/mark.md) that the software laying out the text has to position correctly under the letter.

## Example

In Devanagari, adding a nukta under a consonant turns it into a related sound used mainly in loanwords, while the rest of the letter stays the same.

## Related terms

[Matra](matra.md) · [Virama](virama.md) · [Diacritic](diacritic.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Devanagari](devanagari.md) · [Precomposed character](precomposed-character.md) · [Normalization](normalization.md)

## Further reading

* Foundations: [Nuqta (Wikipedia)](https://en.wikipedia.org/wiki/Nuqta)
