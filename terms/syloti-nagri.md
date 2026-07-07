---
term: Syloti Nagri
slug: syloti-nagri
aliases:
  - Sylheti Nagri
  - Sylheti Nagari
level: advanced
depth: core
summary: Syloti Nagri is a script used to write Sylheti, a language spoken in northeast Bangladesh and southeast Assam in India.
related:
  - abugida
  - brahmic-scripts
  - bengali-assamese
  - virama
  - conjunct
status: voice-passed
version_added: 0.1
updated: 2026-07-07
contributors:
  - sam-gordashko
further_reading:
  - title: Noto Sans Syloti Nagri (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Syloti+Nagri
    type: design-tool
  - title: 'Unicode Syloti Nagri code chart (U+A800)'
    url: https://www.unicode.org/charts/PDF/UA800.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Syloti Nagri

## Definition

Syloti Nagri is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Sylheti,<sup>1</sup> a language spoken in northeast Bangladesh and southeast Assam in India.<sup>2</sup> It is an [abugida](../language-terms/writing-systems-and-scripts/abugida.md) descended from the [Brahmic](brahmic-scripts.md) family: each of its 27 consonants carries an inherent vowel /o/ that dependent vowel signs can change,<sup>3</sup> and it also has independent vowel letters.<sup>4</sup> It is a historical script of the Sylhet region, descended from the Kaithi script and without a single known inventor, and is the focus of modern revival.<sup>5</sup>

For example, the script's own name ꠍꠤꠟꠐꠤ ꠘꠣꠉꠞꠤ ("Siloti Nagri") is written left to right, its vowel signs attached to the consonants.

Syloti Nagri is one script within the writing system of the language that uses it. This page describes the script itself; how Sylheti uses it, its spelling, punctuation, and which symbols, is the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Syloti Nagri |
| --- | --- |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) (Brahmic) |
| Autonym | ꠍꠤꠟꠐꠤ ꠘꠣꠉꠞꠤ |
| Symbols | consonants carrying an inherent vowel /o/, plus independent vowels |
| Marks | dependent vowel signs; a hasanta (like a [virama](../language-terms/writing-systems-and-scripts/virama.md)) and anusvara |
| Letter case | None (no uppercase and lowercase) |
| Numerals | common ASCII digits |
| Unicode block | Syloti Nagri, [U+A800 to U+A82F](https://www.unicode.org/charts/PDF/UA800.pdf) |
| [Complex text layout](complex-text-layout.md) | Yes: dependent vowel signs and the hasanta (conjuncts) need positioning and shaping |
| Languages | Sylheti |

### Script rules and features

Script rules apply to any language that uses Syloti Nagri in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature | How it works in Syloti Nagri |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right |
| Inherent vowel | each consonant carries an inherent vowel /o/; dependent vowel signs attach to change it (see [abugida](../language-terms/writing-systems-and-scripts/abugida.md)) |
| Hasanta | a hasanta mark (like a [virama](../language-terms/writing-systems-and-scripts/virama.md)) suppresses the inherent vowel, marking a word-final consonant or forming a [conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) |

### Why it matters in design systems

Treat this entry as a starting playbook for Syloti Nagri, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Syloti Nagri coverage, because a Bengali or Latin font will not render it.

Where you cannot be creative is the script rules. Unlike the region's recently devised community alphabets, Syloti Nagri is a Brahmic [abugida](../language-terms/writing-systems-and-scripts/abugida.md), so it does need shaping: each consonant carries an inherent vowel /o/, dependent vowel signs attach and have to be positioned, and a hasanta mark suppresses that inherent vowel to mark a word-final consonant or form a [conjunct](../language-terms/writing-systems-and-scripts/conjunct.md).<sup>6</sup> The font's [OpenType](opentype.md) rules carry that positioning and conjunct behaviour, and the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) applies it at render time, the step that turns stored characters into positioned glyphs. It is lighter than [Devanagari](devanagari.md), but it is not a plain row of letters. These are not styling choices: get the vowel-sign placement or the conjuncts wrong and the text renders incorrectly, not just unstyled.

Where you are free is the rest: the typeface's personality, weight, size, colour, and spacing, within what the script allows and what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for, remembering that Sylheti is largely written in the [Bengali-Assamese script](bengali-assamese.md) today, and also in [Latin](latin-script.md), so Syloti Nagri is one option, not the only way the language is written. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script and its shaping, and give people a way to type it:** confirm the font ships the Syloti Nagri consonants, independent vowels, dependent vowel signs, and hasanta, AND positions the vowel signs and forms conjuncts, not just the base letters. Pair it with a [keyboard layout](keyboard-layout.md). [Noto Sans Syloti Nagri](https://fonts.google.com/noto/specimen/Noto+Sans+Syloti+Nagri) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a letter grid:** set a word that uses a dependent vowel sign and a hasanta or conjunct, and confirm they position and form correctly. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Check the orthography, and which script the community uses:** Sylheti is written in Syloti Nagri, the Bengali-Assamese script, and Latin, so do not assume one script. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an [endangered](endangered-language.md) or under-resourced script the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Bengali-Assamese](bengali-assamese.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari](devanagari.md) · [Endangered language](endangered-language.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Keyboard layout](keyboard-layout.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](latin-script.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto Sans Syloti Nagri (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Syloti+Nagri)
* Foundations: [Unicode Syloti Nagri code chart (U+A800)](https://www.unicode.org/charts/PDF/UA800.pdf)

### Sources

1. Syloti Nagri is a lesser-known Brahmi-derived script used for writing the Sylheti language - The Unicode Standard, Version 16.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/)
2. Sylheti is spoken by some 5 million speakers in the Barak Valley region of northeast Bangladesh and southeast Assam in India - The Unicode Standard, Version 16.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/)
3. The Syloti Nagri script has 27 consonant letters with an inherent vowel of /o/ - The Unicode Standard, Version 16.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/)
4. There are 5 independent vowel letters, and 5 dependent vowel signs that are attached to a consonant letter - The Unicode Standard, Version 16.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/)
5. Syloti Nagri is a historical script of the Sylhet region descended from the Kaithi script, with no single known inventor, now the focus of revival (secondary source, interim pending an upgrade to a primary attribution) - Sylheti Nagri (Wikipedia) [https://en.wikipedia.org/wiki/Syloti_Nagri](https://en.wikipedia.org/wiki/Syloti_Nagri)
6. U+A806 SYLOTI NAGRI SIGN HASANTA indicates a word-final consonant, or is inserted between consonants to represent a conjunct - The Unicode Standard, Version 16.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-15/)
