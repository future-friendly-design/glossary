---
term: Phoneme
slug: phoneme
aliases: []
level: intermediate
depth: core
summary: "A phoneme is the smallest unit of sound in a language that can distinguish one word from another."
related:
  - grapheme
  - language
  - script
  - orthography
status: voice-passed
version_added: 0.1
updated: 2026-08-03
contributors:
  - sam-gordashko
further_reading:
  - title: International Phonetic Association
    url: https://www.internationalphoneticassociation.org/
    type: authority
  - title: Phoneme (Wikipedia)
    url: https://en.wikipedia.org/wiki/Phoneme
    type: authority
license: CC-BY-4.0
tags:
  - language-linguistics
---

# Phoneme

## Definition

A phoneme is the smallest unit of sound in a language that can distinguish one word from another.<sup>1</sup> It is the spoken-language counterpart to a [grapheme](../../programming-terms/text-for-digital-products-and-the-web/grapheme.md), the smallest unit of writing: where a grapheme is an abstract unit of a [script](../writing-systems-and-scripts/script.md), a phoneme is an abstract unit of speech. For example, the English words pat and bat differ only in their first phoneme, /p/ versus /b/, and swapping one for the other changes the word; a pair that differs in a single sound like this is called a minimal pair.<sup>2</sup>

### Why it matters in design systems

The tempting shortcut is to treat letters as sounds: one symbol, one sound. Spelling and pronunciation are not that tidy. The correspondence between the symbols of a writing system and a language's phonemes is not one-to-one,<sup>3</sup> so one phoneme can be spelled many ways (English /f/ in fan, phone, and rough) and one symbol can spell different phonemes (the c in cat and city). English is an extreme case, but no [orthography](../writing-systems-and-scripts/orthography.md) is perfectly phonemic. For product work the payoff is mostly conceptual: the phoneme is the spoken-language half of the distinction the writing-systems cluster leans on, where a grapheme is the smallest unit of writing and a phoneme the smallest unit of sound. Where it bites directly is any feature that quietly assumes letters equal sounds: search and autocomplete, sorting and [collation](../../programming-terms/text-for-digital-products-and-the-web/collation.md), transliteration, and text-to-speech all have to model the gap between how a word is written and how it is said, rather than reading the letters as if they were the sounds.

***

### Related terms and mentions

[Collation](../../programming-terms/text-for-digital-products-and-the-web/collation.md) · [Grapheme](../../programming-terms/text-for-digital-products-and-the-web/grapheme.md) · [Language](language.md) · [Orthography](../writing-systems-and-scripts/orthography.md) · [Script](../writing-systems-and-scripts/script.md) · [Symbol](../writing-systems-and-scripts/symbol.md) · [Writing system](../writing-systems-and-scripts/writing-system.md) · [Language & linguistics](./)

### Further reading

* Foundations: [International Phonetic Association](https://www.internationalphoneticassociation.org/)
* Foundations: [Phoneme (Wikipedia)](https://en.wikipedia.org/wiki/Phoneme)

### Sources

1. "A phoneme is ... the smallest possible phonetic unit ... that helps distinguish one word from another." [Phoneme (Wikipedia)](https://en.wikipedia.org/wiki/Phoneme)
2. "A pair of words like kátur and gátur that differ only in one phone is called a minimal pair." [Phoneme (Wikipedia)](https://en.wikipedia.org/wiki/Phoneme)
3. "The correspondence between symbols and phonemes in alphabetic writing systems is not necessarily a one-to-one correspondence." [Phoneme (Wikipedia)](https://en.wikipedia.org/wiki/Phoneme)
