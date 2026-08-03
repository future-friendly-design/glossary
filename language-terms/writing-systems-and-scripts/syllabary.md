---
term: Syllabary
slug: syllabary
aliases: []
level: intermediate
depth: core
summary: >-
  A syllabary is a type of script where each symbol stands for a whole syllable
  rather than a single sound.
related:
  - abugida
  - alphabet
  - logographic
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Syllabary (Wikipedia)
    url: https://en.wikipedia.org/wiki/Syllabary
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Syllabary

## Definition

A syllabary is a type of [script](script.md) where each symbol stands for a whole syllable rather than a single sound. Japanese hiragana and katakana are syllabaries,<sup>1</sup> and so is the Cherokee script that Sequoyah created.<sup>2</sup>

For example, the hiragana `あ` (a) and `い` (i) are two separate, unrelated symbols, one for each syllable.

Each symbol standing for a whole syllable is what sets a syllabary apart from an [alphabet](alphabet.md), which spells a syllable out of separate consonant and vowel letters.<sup>3</sup>

The syllabaries the glossary has an entry for are listed below, alongside a few other notable syllabaries not yet covered. Select a linked term to navigate to its glossary page.

| Script                                                            | Languages               | Example                                                    |
| ----------------------------------------------------------------- | ----------------------- | ---------------------------------------------------------- |
| [Canadian Aboriginal Syllabics](canadian-aboriginal-syllabics.md) | Cree, Ojibwe, Inuktitut | ᑖᓂᓯ (tânisi): "hello" (Cree)                               |
| Cherokee                                                          | Cherokee                | ᎣᏏᏲ (osiyo): "hello"<sup>4</sup>                           |
| [Hiragana](hiragana.md)                                           | Japanese                | こんにちは (konnichiwa): "hello"                                |
| [Katakana](katakana.md)                                           | Japanese                | ハロー (harō): "hello" (English loanword)                     |
| Vai                                                               | Vai                     | ꘋꕯ ꖬꕎ ꘃꗡ ꗪ ꔤ ꕮ (ŋna suwa kɛɛ ɓɛ i ma): "hello"<sup>5</sup> |

### Why it matters in design systems

In a syllabary each symbol usually stands for a consonant-plus-vowel unit, and the symbols for different syllables are not built from a shared, systematic set of parts. That is the line between a syllabary and an [abugida](abugida.md): in an abugida, syllables that share a consonant share a base shape with vowel marks added,<sup>6</sup> whereas a syllabary gives each syllable its own distinct symbol. It also differs from a [logographic](logographic.md) script, whose symbols stand for meaning rather than sound.

For a design system the payoff is knowing what kind of set you are covering. A syllabary is a fixed, learnable inventory of symbols, so [font coverage](../../terms/font-coverage.md) and keyboard or [input method](../../terms/input-method-editor.md) support target that whole set rather than a small recombining alphabet. Syllabaries also tend to appear mixed with other scripts: everyday Japanese runs hiragana and katakana together with logographic kanji on one line, so "supports Japanese" is never a single-script decision.

***

### Related terms and mentions

[Abugida](abugida.md) · [Alphabet](alphabet.md) · [Canadian Aboriginal Syllabics script](canadian-aboriginal-syllabics.md) · [Font coverage](../../terms/font-coverage.md) · [Hiragana script](hiragana.md) · [Input method editor (IME)](../../terms/input-method-editor.md) · [Katakana script](katakana.md) · [Logographic](logographic.md) · [Script](script.md) · [Symbol](symbol.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [Syllabary (Wikipedia)](https://en.wikipedia.org/wiki/Syllabary)

### Sources

1. "A collective term for the two syllabic scripts used (along with kanji and romaji) by the Japanese writing system." (hiragana and katakana) - Unicode Glossary: Kana [https://www.unicode.org/glossary/#kana](https://www.unicode.org/glossary/#kana)
2. "The Cherokee script is a syllabary developed between 1815 and 1821, to write the Cherokee language... The Cherokee syllabary, as invented by Sequoyah between 1815 and 1821, contained 6 vowels and 17 consonants." - The Unicode Standard, Version 17.0, Chapter 20: Americas [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-20/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-20/)
3. An alphabet indicates both consonants and vowels - Unicode Glossary: Alphabet [https://www.unicode.org/glossary/#alphabet](https://www.unicode.org/glossary/#alphabet)
4. ᎣᏏᏲ (osiyo) is listed as the Cherokee word for "hello" (general greeting) - Omniglot: Useful phrases in Cherokee [https://www.omniglot.com/language/phrases/cherokee.php](https://www.omniglot.com/language/phrases/cherokee.php)
5. ꘋꕯ ꖬꕎ ꘃꗡ ꗪ ꔤ ꕮ (ŋna suwa kɛɛ ɓɛ i ma) is listed as the Vai phrase for "hello" (general greeting, addressing one person) - Omniglot: Useful phrases in Vai [https://www.omniglot.com/language/phrases/vai.htm](https://www.omniglot.com/language/phrases/vai.htm)
6. An abugida's base letters carry an inherent vowel that additional distinguishing marks change - Unicode Glossary: Abugida [https://www.unicode.org/glossary/#abugida](https://www.unicode.org/glossary/#abugida)
