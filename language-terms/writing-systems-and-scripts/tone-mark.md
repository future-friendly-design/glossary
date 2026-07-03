---
term: Tone mark
slug: tone-mark
aliases:
  - tone diacritic
level: intermediate
depth: core
summary: >-
  A tone mark is a diacritic that shows the pitch or tone of a syllable in tonal
  languages.
related:
  - diacritic
  - mark
  - orthography
  - line-height
status: voice-passed
version_added: 0.1
updated: 2026-06-25T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Diacritic (Wikipedia)
    url: https://en.wikipedia.org/wiki/Diacritic
    type: authority
license: CC-BY-4.0
tags:
  - characters-encoding
---

# Tone mark

## Definition

A tone mark is a diacritic that shows the pitch or tone of a syllable in tonal languages.

For example, in Hanyu Pinyin (Mandarin written in the Latin alphabet), the tone marks in `mā`, `má`, `mǎ`, and `mà` spell four different words.

### Why it matters in design systems

A tone mark is a specialized kind of [diacritic](diacritic.md), used where the pitch of a syllable changes a word's meaning, as in Mandarin Chinese and Vietnamese.

Vietnamese can stack a tone mark on a vowel letter that already carries a diacritic, so one vowel may carry two diacritics at once. That stack rises higher than a single accent, so it needs more room between lines. How many marks pile on a letter is set by the language's [orthography](orthography.md), not the shared script, which is why the same Latin letters need more [line height](../../terms/line-height.md) for Vietnamese than for most languages.<sup>1</sup>

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Diacritic](diacritic.md) · [Language](../linguistics/language.md) · [Latin script](../../terms/latin-script.md) · [Line height](../../terms/line-height.md) · [Mark](mark.md) · [Orthography](orthography.md) · [Script](script.md) · [Symbol](symbol.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Diacritic (Wikipedia)](https://en.wikipedia.org/wiki/Diacritic)

### Sources

1. In the Vietnamese alphabet a vowel letter and a tone mark stack on one base letter, stored either as one combined character or as separate combining marks - The Unicode Standard 17.0, Chapter 7 [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
