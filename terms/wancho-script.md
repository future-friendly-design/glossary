---
term: Wancho script
slug: wancho-script
aliases: []
level: advanced
depth: core
summary: >-
  The Wancho script is a script used to write the Wancho language of Arunachal
  Pradesh, India.
related:
  - alphabet
  - ol-chiki
  - warang-citi
  - tone-mark
  - endangered-language
status: voice-passed
version_added: 0.1
updated: 2026-07-07T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Noto Sans Wancho (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Wancho
    type: design-tool
  - title: Unicode Wancho code chart (U+1E2C0)
    url: https://www.unicode.org/charts/PDF/U1E2C0.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Wancho script

## Definition

The Wancho script is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write the Wancho language of Arunachal Pradesh, India. It is an [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) recently devised to write Wancho,<sup>1</sup> a Sino-Tibetan language used mainly in the southeast of Arunachal Pradesh, and also in Assam, Nagaland, Myanmar, and Bhutan.<sup>2</sup> It was created between 2001 and 2012 by Banwang Losu, in Longding district, Arunachal Pradesh.<sup>3</sup>

For example, the script's own name 𞋒𞋀𞋉𞋃𞋕 𞋈𞋀𞋜𞋐𞋜 ("Wancho") is written left to right, each vowel and consonant its own full letter.

The Wancho script is one script within the writing system of the language that uses it. This page describes the script itself; how Wancho uses it, its spelling, punctuation, and which symbols, is the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property                                      | Wancho script                                                                                                                                       |
| --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| Script type                                   | [Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md)                                                                               |
| Autonym                                       | 𞋒𞋀𞋉𞋃𞋕 𞋈𞋀𞋜𞋐𞋜                                                                                                                               |
| Symbols                                       | full letters for consonants and vowels                                                                                                              |
| Marks                                         | [Tone marks](../language-terms/writing-systems-and-scripts/tone-mark.md) (Wancho is a tonal language); vowels are full letters, not dependent marks |
| Letter case                                   | None (no uppercase and lowercase)                                                                                                                   |
| Numerals                                      | Wancho digits (U+1E2F0 to U+1E2F9), alongside common ASCII digits                                                                                   |
| Unicode block                                 | Wancho, [U+1E2C0 to U+1E2FF](https://www.unicode.org/charts/PDF/U1E2C0.pdf)                                                                         |
| [Complex text layout](complex-text-layout.md) | No reordering or contextual shaping; tone marks position on their letters                                                                           |
| Languages                                     | Wancho                                                                                                                                              |

### Script rules and features

Script rules apply to any language that uses the Wancho script in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature                                                                   | How it works in the Wancho script                                                     |
| --------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right                                                                         |
| [Tone marks](../language-terms/writing-systems-and-scripts/tone-mark.md)          | Wancho is a tonal language, and tone is written with tone marks placed on the letters |

### Why it matters in design systems

Treat this entry as a starting playbook for the Wancho script, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Wancho coverage, because no Latin or Devanagari font will render it.

Where you cannot be creative is the script rules, and they are few: the Wancho script is a linear [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) that runs left to right, so it is not complex to shape, no reordering or contextual analysis, and the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) and the font's [OpenType](opentype.md) rules mostly map each letter straight to its glyph. The one positioning job is the [tone marks](../language-terms/writing-systems-and-scripts/tone-mark.md): Wancho is tonal, so tone is written with marks on the letters, which the font has to place correctly. The larger work is coverage and input: the Wancho script is a very recent, purpose-built community script for a small language community, so fonts, a [keyboard layout](keyboard-layout.md), and rendering for it are a concrete deliverable, not a special case to skip. These are not styling choices: without the font, the tone marks, and a way to type it, the language cannot be set in its own script at all.

Everything else is a free design choice: the typeface's personality, weight, size, colour, and spacing, within what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for, remembering that Wancho is also written in the [Devanagari](devanagari.md) and [Latin](../language-terms/writing-systems-and-scripts/latin-script.md) scripts, so the script is a recent choice, not the only way the language is written. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script, its tone marks, and a way to type it:** confirm the font ships the Wancho letters, tone marks, and digits, positions the tone marks correctly, and is paired with a [keyboard layout](keyboard-layout.md). [Noto Sans Wancho](https://fonts.google.com/noto/specimen/Noto+Sans+Wancho) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, tone marks included:** set a real Wancho word with its tone marks and confirm the marks sit on the right letters at your text sizes.
* **Check the orthography, and which script the community uses:** Wancho is written in the Wancho script, Devanagari, and Latin, so do not assume one script. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an [endangered](endangered-language.md) or under-resourced language the conventions may not be in any library yet. Capture them with fluent speakers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) · [Autonym](autonym.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Devanagari](devanagari.md) · [Endangered language](endangered-language.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Keyboard layout](keyboard-layout.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [Ol Chiki](ol-chiki.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Tone mark](../language-terms/writing-systems-and-scripts/tone-mark.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Warang Citi](warang-citi.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto Sans Wancho (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Wancho)
* Foundations: [Unicode Wancho code chart (U+1E2C0)](https://www.unicode.org/charts/PDF/U1E2C0.pdf)

### Sources

1. The Wancho script is an alphabet recently devised to write the Wancho language - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
2. Wancho is a Sino-Tibetan language used mainly in the southeast of Arunachal Pradesh, as well as in Assam, Nagaland, Myanmar, and Bhutan - The Unicode Standard, Version 16.0, Chapter 13: South and Central Asia-II [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-13/)
3. The Wancho script was created between 2001 and 2012 by Banwang Losu, in Longding district, Arunachal Pradesh (secondary source, interim pending an upgrade to a primary attribution) - Wancho script (Wikipedia) [https://en.wikipedia.org/wiki/Wancho\_script](https://en.wikipedia.org/wiki/Wancho_script)
