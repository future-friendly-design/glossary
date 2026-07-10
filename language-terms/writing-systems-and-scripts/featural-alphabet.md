---
term: Featural script
slug: featural-alphabet
aliases:
  - featural alphabet
level: advanced
depth: core
summary: >-
  A featural script is a type of script whose letter shapes are built to reflect
  the physical features of the sounds they represent, so related sounds get
  visually related letters.
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

# Featural script

## Definition

A featural script is a type of [script](script.md) whose letter shapes are built to reflect the physical features of the sounds they represent, so related sounds get visually related letters. [Hangul](../../terms/hangul.md), the Korean script, is the most cited example; the Unicode Standard calls it a featural syllabic script.<sup>1</sup> That sets it apart from an ordinary [alphabet](alphabet.md), where the link between a letter's shape and its sound is arbitrary.

While this glossary doesn't cover every script, here are some scripts described as featural to be aware of. Select a linked term to navigate to its glossary page.

| Script                                                                        | Languages               | Example |
| ----------------------------------------------------------------------------- | ----------------------- | ------- |
| [Hangul](../../terms/hangul.md)                                               | Korean                  | 안녕하세요 (annyeonghaseyo): "hello" |
| [Canadian Aboriginal Syllabics](../../terms/canadian-aboriginal-syllabics.md) | Cree, Ojibwe, Inuktitut | ᑖᓂᓯ (tânisi): "hello" (Cree) |

### Why it matters in design systems

Featural design shows that a script's shapes can carry linguistic structure directly, rather than assigning arbitrary symbols to sounds. Hangul, developed under King Sejong and promulgated in 1446,<sup>2</sup> was designed so its five basic consonants are shaped after the human speech organs used to make each sound, so related sounds look related;<sup>3</sup> the letters are then grouped into square syllable blocks built from a set of alphabetic components, rather than written in a simple line.<sup>4</sup> [Canadian Aboriginal Syllabics](../../terms/canadian-aboriginal-syllabics.md) is also often described as featural, because rotating a consonant's symbol systematically encodes the following vowel (which is why it is sometimes called a featural abugida).

The practical consequence is the unit of layout. Because Hangul builds syllable blocks out of letter components, [font](../../terms/font.md) design and rendering treat the block, not the single letter, as the shape that has to sit consistently in a square. That is a different problem from placing alphabetic letters one after another, so featural does not mean "just an alphabet" when you scope typeface and layout work.

***

### Related terms and mentions

[Abugida](abugida.md) · [Alphabet](alphabet.md) · [Canadian Aboriginal Syllabics](../../terms/canadian-aboriginal-syllabics.md) · [Font](../../terms/font.md) · [Hangul](../../terms/hangul.md) · [Script](script.md) · [Symbol](symbol.md) · [Syllabary](syllabary.md) · [Typeface](../../terms/typeface.md) · [Unicode Standard](../../terms/unicode-standard.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Featural writing system (Wikipedia)](https://en.wikipedia.org/wiki/Featural_writing_system)

### Sources

1. "Korean Hangul may be considered a featural syllabic script." - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
2. The Hunminjeongeum manuscript, published in 1446, contains King Sejong's promulgation of the Korean alphabet now called Hangul, the development of which he completed in 1443 - UNESCO Memory of the World: Hunminjeongum Manuscript [https://www.unesco.org/en/memory-world/hunminjeongum-manuscript](https://www.unesco.org/en/memory-world/hunminjeongum-manuscript)
3. The five basic consonants of Hangul were designed based on the shape of the human vocal organs used to make each sound - The spirit and principles behind Hangeul's creation (Korean Cultural Center) [https://www.koreanculture.org/gallery-korea/2024/04/07/hangeul](https://www.koreanculture.org/gallery-korea/2024/04/07/hangeul)
4. "As opposed to many other syllabic scripts, the syllables are formed from a set of alphabetic components in a regular fashion." - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
