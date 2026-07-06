---
term: Latin script
slug: latin-script
aliases:
  - Roman script
  - Roman alphabet
level: foundational
depth: core
summary: The Latin script is a script used to write a wide variety of languages all over the world.
related:
  - alphabet
  - cyrillic
  - greek-script
  - diacritic
  - orthography
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-06
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Standard Scripts (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/standard
    type: code
  - title: Noto Sans (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans
    type: design-tool
  - title: 'Unicode Basic Latin code chart (U+0000)'
    url: https://www.unicode.org/charts/PDF/U0000.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Latin script

## Definition

The Latin script is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write a wide variety of languages all over the world.<sup>1</sup> It is an [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md), with separate symbols for consonants and vowels, and its letters come in uppercase and lowercase pairs.<sup>2</sup> The Latin alphabet descends from the one the Etruscans adopted from a Western variant of the classical [Greek](greek-script.md) alphabet.<sup>3</sup>

For example, the Vietnamese phrase Tiếng Việt ("Vietnamese") extends the basic letters with stacked accent marks, one of countless ways languages adapt the script to their own sounds.

The Latin script is one script within the writing system of each language that uses it. This page describes the script itself; how a given language uses it, its spelling, punctuation, and which symbols, is that language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Latin script |
| --- | --- |
| Script type | [Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) |
| Autonym | Latin |
| Symbols | letters for consonants and vowels (the basic 26), extended per language with accented and additional letters |
| Marks | [diacritics](../language-terms/writing-systems-and-scripts/diacritic.md) (acute, grave, circumflex, tilde, cedilla, and others), available both precomposed and as combining marks |
| Letter case | Bicameral: uppercase and lowercase pairs (case conversion is locale-sensitive, for example Turkish dotted and dotless i) |
| Numerals | European digits 0 to 9 (shared "common" digits, not unique to the Latin script) |
| Unicode block | Basic Latin, [U+0000 to U+007F](https://www.unicode.org/charts/PDF/U0000.pdf) (plus Latin-1 Supplement, Latin Extended-A and B, and more) |
| [Complex text layout](complex-text-layout.md) | No, a standard (non-complex) script: no reordering or contextual analysis required |
| Languages | English, Spanish, French, Vietnamese, Turkish, Yoruba, and hundreds of others |

### Script rules and features

Script rules apply to any language that uses the Latin script in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature | How it works in the Latin script |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right |
| Letter case | letters come in uppercase and lowercase pairs, and case conversion follows rules that depend on the language, not just the letter |
| [Diacritics](../language-terms/writing-systems-and-scripts/diacritic.md) | accents and other marks extend the basic letters; they exist both as precomposed letters and as combining marks positioned on a base |
| [Ligature](ligature.md) | optional typographic ligatures such as fi and fl are an aesthetic choice, not a requirement of the script |

### Why it matters in design systems

Treat this entry as a starting playbook for the Latin script, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with coverage for the languages you actually serve, because the basic 26 letters are only the start.

Where you cannot be creative is the script rules. Text runs left to right.<sup>4</sup> The Latin script is a standard, non-complex script, meaning it needs no reordering or contextual analysis to shape, so almost every font and tool handles it.<sup>5</sup> The trap is a quieter one: only a small fraction of the languages written with the Latin script can be written with just the basic 26 uppercase and lowercase letters,<sup>6</sup> so treating "Latin" as "English" or "ASCII" drops the accented and additional letters that Vietnamese, Turkish, Polish, Yoruba, and many others require. Those letters exist both precomposed and as base letters plus combining [diacritics](../language-terms/writing-systems-and-scripts/diacritic.md), which the font's [OpenType](opentype.md) rules position and the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) applies at render time, the step that turns stored characters into positioned glyphs. Case is a rule too: uppercase and lowercase are paired, but converting between them is locale-sensitive, so the same letter can uppercase differently in different languages. These are not styling choices: drop a language's letters or mis-case them and the text is wrong, not just unstyled.

Where you are free is the rest: the typeface's personality, weight, size, colour, and spacing, within what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for, since a typeface that suits English may lack the marks Vietnamese stacks or the letters Turkish needs. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the languages, not just the alphabet:** confirm the font ships the accented and additional letters and combining [diacritics](../language-terms/writing-systems-and-scripts/diacritic.md) your languages need, not only the basic 26. [Noto Sans](https://fonts.google.com/noto/specimen/Noto+Sans) is a free, open-licensed option with broad Latin coverage, and [Noto](noto-fonts.md) reaches languages where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not "The quick brown fox":** type a word that stacks diacritics, such as Tiếng Việt, and a word that tests casing, such as Istanbul in Turkish, and confirm the marks position and the case converts correctly. Tool support varies, so test early.
* **Check the orthography, not just the script, before reusing symbols across languages:** two languages can share the Latin script and still differ in which letters they use and how they case them. Do not hardcode one language's choices; pull them from [locale](locale.md) data. Unicode's [CLDR](cldr.md) publishes per-language conventions, including casing rules, as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) · [Autonym](autonym.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Cyrillic](cyrillic.md) · [Diacritic](../language-terms/writing-systems-and-scripts/diacritic.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Greek script](greek-script.md) · [Language](../language-terms/linguistics/language.md) · [Ligature](ligature.md) · [Locale](locale.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Standard Scripts (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/standard)
* Design tools: [Noto Sans (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans)
* Foundations: [Unicode Basic Latin code chart (U+0000)](https://www.unicode.org/charts/PDF/U0000.pdf)

### Sources

1. The Latin script is used to write a wide variety of languages all over the world - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
2. Latin letters come in uppercase and lowercase pairs - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
3. The Latin alphabet is derived from the alphabet used by the Etruscans, who had adopted a Western variant of the classical Greek alphabet - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
4. The Latin script is written in linear sequence from left to right - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
5. In this document, "standard" refers to any non-complex script, that is, any script that does not require re-ordering or contextual analysis - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
6. Only a small fraction of the languages written with the Latin script can be written entirely with the basic set of 26 uppercase and 26 lowercase Latin letters - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
