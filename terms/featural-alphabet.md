---
term: Featural alphabet
slug: featural-alphabet
aliases:
  - featural script
level: advanced
depth: core
summary: A featural alphabet is a script whose letter shapes are built to reflect the physical features of the sounds they represent.
related:
  - alphabet
  - syllabary
  - script
  - hangul
  - canadian-aboriginal-syllabics
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Featural writing system (Wikipedia)
    url: https://en.wikipedia.org/wiki/Featural_writing_system
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Featural alphabet

## Definition

A featural alphabet is a [script](../language-terms/writing-systems-and-scripts/script.md) whose letter shapes are built to reflect the physical features of the sounds they represent, so related sounds get visually related letters. [Hangul](hangul.md), the Korean script, is the most cited example; the Unicode Standard calls it a featural syllabic script.<sup>1</sup> That sets it apart from an ordinary [alphabet](alphabet.md), where the link between a letter's shape and its sound is arbitrary.

### Why it matters in design systems

Featural design shows that a script's shapes can carry linguistic structure directly, rather than assigning arbitrary symbols to sounds. In Hangul the consonant letters are traditionally described as suggesting the position of the tongue and lips, so related sounds look related; the letters are then grouped into square syllable blocks built from a set of alphabetic components, rather than written in a simple line.<sup>2</sup> [Canadian Aboriginal Syllabics](canadian-aboriginal-syllabics.md) is also often described as featural, because rotating a consonant's symbol systematically encodes the following vowel (which is why it is sometimes called a featural abugida).

The practical consequence is the unit of layout. Because Hangul builds syllable blocks out of letter components, [font](font.md) design and rendering treat the block, not the single letter, as the shape that has to sit consistently in a square. That is a different problem from placing alphabetic letters one after another, so featural does not mean "just an alphabet" when you scope typeface and layout work.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Canadian Aboriginal Syllabics](canadian-aboriginal-syllabics.md) · [Font](font.md) · [Hangul](hangul.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Syllabary](syllabary.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Featural writing system (Wikipedia)](https://en.wikipedia.org/wiki/Featural_writing_system)

### Sources

1. "Korean Hangul may be considered a featural syllabic script." - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
2. "As opposed to many other syllabic scripts, the syllables are formed from a set of alphabetic components in a regular fashion." - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)

<!-- NEEDS EXPERT REVIEW: the "consonant shapes suggest the position of the tongue and lips" account of Hangul (from the Hunminjeongeum tradition) and the "featural abugida" characterization of Canadian Aboriginal Syllabics are the standard descriptions but are stated here without a fetched primary quote; the Unicode primary confirms only that Hangul is a "featural syllabic script." Cohort to confirm wording and attribution (Hangul created under King Sejong, 15th century). -->
