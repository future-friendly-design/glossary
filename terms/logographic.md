---
term: Logographic
slug: logographic
aliases:
  - logography
  - logogram
level: intermediate
depth: core
summary: A logographic script uses symbols that stand for whole words or meaningful units (morphemes) rather than for sounds alone.
related:
  - syllabary
  - alphabet
  - script
  - logosyllabary
  - ideographic
status: voice-passed
version_added: 0.1
updated: 2026-06-18T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: 'Unicode Glossary: Logogram'
    url: https://www.unicode.org/glossary/#logogram
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Logographic

## Definition

A logographic script uses symbols that stand for whole words or meaningful units (morphemes) rather than for sounds alone.<sup>1</sup> [Han characters](han-characters.md) are the most widely used example; the Unicode Standard describes them as "logographic (each character represents a word, not just a sound)".<sup>2</sup> Because each symbol also maps to a spoken syllable, a system like Chinese is more precisely a [logosyllabary](logosyllabary.md).

For example, the Chinese character `山` writes the whole word "mountain", not the separate sounds in it.

While this glossary doesn't cover every script, here are some logographic scripts to be aware of; fully logographic systems are rare, and Han characters are the main one in modern use. Select a linked term to navigate to its glossary page.

| Script                            | Languages                       | Example |
| --------------------------------- | ------------------------------- | ------- |
| [Han characters](han-characters.md) | Chinese (also Japanese, Korean) | 山      |
| Tangut                            | Tangut (historical)             |         |

### Why it matters in design systems

The common shortcut is to call these characters "ideographic", as if each were a picture of an idea. That is mostly wrong: Han characters are tied to specific words and morphemes of a spoken language, and they represent them phonetically for the most part,<sup>3</sup> so [logographic](logographic.md) (or more precisely [logosyllabary](logosyllabary.md)) is the accurate term, not [ideographic](ideographic.md).

For type and product work the defining consequence is scale. A logographic script needs thousands of distinct symbols rather than a few dozen letters, which drives [font](font.md) file size and [subsetting](font-subsetting.md), [glyph](glyph.md) coverage, and input: text entry relies on an [input method editor](input-method-editor.md) that converts typed sounds into characters, rather than one key per symbol.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Font](font.md) · [Font subsetting](font-subsetting.md) · [Glyph](glyph.md) · [Han characters](han-characters.md) · [Ideographic](ideographic.md) · [Input method editor (IME)](input-method-editor.md) · [Logosyllabary](logosyllabary.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Syllabary](syllabary.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Foundations: [Unicode Glossary: Logogram](https://www.unicode.org/glossary/#logogram)

### Sources

1. "Any symbol that primarily represents a word (or morpheme) in contrast to a sound or pronunciation." - Unicode Glossary: Logogram [https://www.unicode.org/glossary/#logogram](https://www.unicode.org/glossary/#logogram)
2. "They are logographic (each character represents a word, not just a sound) characters that developed from pictographic and ideographic principles." (Chapter 18 reproduces this from the dictionary Kōjien) - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
3. "Chinese characters represent words (or better, morphemes), not ideas, and they represent them phonetically, for the most part, as do all real writing systems…" - John DeFrancis, The Ideographic Myth [https://www.pinyin.info/readings/texts/ideographic_myth.html](https://www.pinyin.info/readings/texts/ideographic_myth.html)
