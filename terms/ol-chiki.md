---
term: Ol Chiki
slug: ol-chiki
aliases:
  - Ol Chemet
  - Ol Cemet'
  - Santali alphabet
level: advanced
depth: core
summary: Ol Chiki is a script used to write Santali, a Munda language of India.
related:
  - alphabet
  - brahmic-scripts
  - warang-citi
  - wancho-script
  - devanagari
status: voice-passed
version_added: 0.1
updated: 2026-07-07T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Noto Sans Ol Chiki (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Ol+Chiki
    type: design-tool
  - title: Unicode Ol Chiki code chart (U+1C50)
    url: https://www.unicode.org/charts/PDF/U1C50.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Ol Chiki

## Definition

Ol Chiki is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Santali, a Munda language of India.<sup>1</sup> It is an [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md), with a full letter for every vowel rather than the dependent vowel marks of the region's [Brahmic](brahmic-scripts.md) abugidas, and it is written left to right. It was created in 1925 by Pandit Raghunath Murmu,<sup>2</sup> and is used primarily for the southern [dialect](dialect.md) of Santali spoken in the state of Odisha.<sup>3</sup>

For example, the script's own name ᱚᱞ ᱪᱤᱠᱤ ("Ol Chiki") is written left to right, each vowel and consonant its own full letter.

Ol Chiki is one script within the writing system of the language that uses it. This page describes the script itself; how Santali uses it, its spelling, punctuation, and which symbols, is the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property                                      | Ol Chiki                                                                                    |
| --------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Script type                                   | [Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md)                       |
| Autonym                                       | ᱚᱞ ᱪᱤᱠᱤ                                                                                     |
| Symbols                                       | full letters for consonants and vowels (30 letters)                                         |
| Marks                                         | Vowels are full letters, not dependent marks; a small set of modifier signs is also encoded |
| Letter case                                   | None (no uppercase and lowercase)                                                           |
| Numerals                                      | Ol Chiki digits (U+1C50 to U+1C59), alongside common ASCII digits                           |
| Unicode block                                 | Ol Chiki, [U+1C50 to U+1C7F](https://www.unicode.org/charts/PDF/U1C50.pdf)                  |
| [Complex text layout](complex-text-layout.md) | No: a linear alphabet, rendered directly (no conjuncts or reordering)                       |
| Languages                                     | Santali                                                                                     |

### Script rules and features

Script rules apply to any language that uses Ol Chiki in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature                                                                   | How it works in Ol Chiki                                                                                              |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right                                                                                                         |
| Full vowel letters                                                                | every vowel is a full letter, unlike the dependent vowel signs of the region's [Brahmic](brahmic-scripts.md) abugidas |

### Why it matters in design systems

Treat this entry as a starting playbook for Ol Chiki, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Ol Chiki coverage, because a Latin or Devanagari font will not render it.

Where you cannot be creative is the script rules, but they are few, and that is the point: Ol Chiki is a linear [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) that runs left to right, with a full letter for every vowel, so it is not complex to shape, no reordering or contextual analysis, and the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) and the font's [OpenType](opentype.md) rules mostly map each letter straight to its glyph. The real work is coverage and input: Santali is one of the scheduled languages of India with millions of speakers, and Ol Chiki is a purpose-built community script with a real and growing digital footprint, so fonts, a [keyboard layout](keyboard-layout.md), and rendering for it are a concrete deliverable, not a special case to skip. These are not styling choices: without the font and a way to type it, the language cannot be set in its own script at all.

Everything else is a free design choice: the typeface's personality, weight, size, colour, and spacing, within what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for, remembering that Santali is also written in the [Devanagari](devanagari.md), Bengali, Odia, and [Latin](../language-terms/writing-systems-and-scripts/latin-script.md) scripts in different regions, so "Santali" is not one script. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script and give people a way to type it:** confirm the font ships the Ol Chiki letters and digits, and pair it with a [keyboard layout](keyboard-layout.md) so the community can actually enter text. [Noto Sans Ol Chiki](https://fonts.google.com/noto/specimen/Noto+Sans+Ol+Chiki) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a letter grid:** set a real Santali word and confirm the letters and any modifier signs render cleanly at your text sizes.
* **Check the orthography, and which script the community uses:** Santali is written in Ol Chiki, Devanagari, Bengali, Odia, and Latin in different places, so do not assume one script. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent speakers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) · [Autonym](autonym.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Dialect](dialect.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Keyboard layout](keyboard-layout.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Warang Citi](warang-citi.md) · [Wancho script](wancho-script.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto Sans Ol Chiki (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Ol+Chiki)
* Foundations: [Unicode Ol Chiki code chart (U+1C50)](https://www.unicode.org/charts/PDF/U1C50.pdf)

### Sources

1. Ol Chiki is an alphabetic script invented in the 20th century to write Santali, a Munda language of India - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
2. Ol Chiki was created in 1925 by Pandit Raghunath Murmu (secondary source, interim pending an upgrade to a primary attribution) - Ol Chiki script (Wikipedia) [https://en.wikipedia.org/wiki/Ol\_Chiki\_script](https://en.wikipedia.org/wiki/Ol_Chiki_script)
3. It is used primarily for the southern dialect of Santali spoken in the state of Odisha - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
