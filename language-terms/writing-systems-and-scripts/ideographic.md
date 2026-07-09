---
term: Ideographic
slug: ideographic
aliases:
  - ideogram
level: intermediate
depth: core
summary: >-
  An ideographic symbol stands for an idea or concept directly, rather than for
  the sounds of a word.
related:
  - logographic
  - pictographic
  - logosyllabary
  - han-characters
status: voice-passed
version_added: 0.1
updated: 2026-06-22T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: The Ideographic Myth (John DeFrancis)
    url: https://www.pinyin.info/readings/texts/ideographic_myth.html
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Ideographic

## Definition

An ideographic symbol stands for an idea or concept directly, rather than for the sounds of a word. Unicode's example is `♻`, which denotes the concept of recycling.<sup>1</sup> As a [script](script.md) classification it would sit alongside [logographic](logographic.md), [alphabet](alphabet.md), and the other type categories, with one crucial difference: no complete writing system is actually ideographic.

### Why it matters in design systems

Because no full writing system is ideographic, this is one of the most misused terms in the vocabulary, and the misuse has a specific home. People routinely call [Han characters](../../terms/han-characters.md) "ideographic", meaning each character is a little picture of an idea understood independently of any language. That is mostly wrong: Han characters are tied to specific words and morphemes and represent them phonetically for the most part,<sup>2</sup> so the accurate term is [logographic](logographic.md), or more precisely [logosyllabary](logosyllabary.md). Even Unicode, whose "CJK Unified Ideographs" block keeps the older word, notes that "the term 'Han ideographs' remains in English usage as a conventional cover term for the script as a whole",<sup>3</sup> not a claim that the characters denote ideas.

Getting this right is both an accuracy and a respect issue when you write documentation, specs, or UI copy about East Asian text: reach for logographic when you mean "characters stand for words". Reserve ideographic for genuinely language-independent symbols, the kind Unicode illustrates with the recycling mark, such as some mathematical, cartographic, or safety symbols, where the concept reads the same whatever language you speak.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Han characters](../../terms/han-characters.md) · [Logographic](logographic.md) · [Logosyllabary](logosyllabary.md) · [Pictographic](pictographic.md) · [Script](script.md) · [Symbol](symbol.md) · [Writing systems & scripts](./)

### Further reading

* Foundations: [The Ideographic Myth (John DeFrancis)](https://www.pinyin.info/readings/texts/ideographic_myth.html)

### Sources

1. "Any symbol that primarily denotes an idea or concept in contrast to a sound or pronunciation" (the entry's example is ♻, the recycling concept) - Unicode Glossary: Ideograph [https://www.unicode.org/glossary/#ideograph](https://www.unicode.org/glossary/#ideograph)
2. "Chinese characters represent words (or better, morphemes), not ideas, and they represent them phonetically, for the most part, as do all real writing systems…" - John DeFrancis, The Ideographic Myth [https://www.pinyin.info/readings/texts/ideographic\_myth.html](https://www.pinyin.info/readings/texts/ideographic_myth.html)
3. "Taken literally, the word 'ideograph' applies only to some of the ancient original character forms... The vast majority of Han characters were developed later via composition, borrowing, and other non-ideographic principles, but the term 'Han ideographs' remains in English usage as a conventional cover term for the script as a whole." - The Unicode Standard, Version 17.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-18/)
