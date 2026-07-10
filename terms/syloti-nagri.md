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
updated: 2026-07-07T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Noto Sans Syloti Nagri (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Syloti+Nagri
    type: design-tool
  - title: Unicode Syloti Nagri code chart (U+A800)
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

{% hint style="info" %}
This glossary doesn't cover every Syloti Nagri property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Syloti Nagri profile

These properties of Syloti Nagri apply to any language that uses it in its [writing system](../language-terms/writing-systems-and-scripts/writing-system.md). Beyond the [script rules](../language-terms/writing-systems-and-scripts/script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

| Property | Syloti Nagri |
| --- | --- |
| [Autonym](autonym.md) | ꠍꠤꠟꠐꠤ ꠘꠣꠉꠞꠤ |
| Languages | Sylheti |
| Letter case | None (no uppercase and lowercase) |
| [Marks](../language-terms/writing-systems-and-scripts/mark.md) | Dependent vowel signs; a hasanta (like a [virama](../language-terms/writing-systems-and-scripts/virama.md)) and anusvara |
| Numerals | Common ASCII digits |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) (Brahmic) |
| [Symbols](../language-terms/writing-systems-and-scripts/symbol.md) | Consonants carrying an inherent vowel /o/, plus independent vowels |

### Syloti Nagri rules and digital use considerations

If your design system supports languages that use Syloti Nagri, here are some considerations to keep in mind:

| Rule or feature | How it works in Syloti Nagri | Design systems |
| --- | --- | --- |
| [Complex text layout](complex-text-layout.md) | Yes, shaping required | Each consonant carries an inherent vowel, dependent vowel signs attach and have to be positioned,<sup>6</sup> and a hasanta forms conjuncts, so the font's [OpenType](opentype.md) rules carry that positioning and conjunct behaviour and the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) applies it at render time; it is lighter than [Devanagari](devanagari.md), but not a plain row of symbols, so a tool or font that cannot shape renders the vowel signs or conjuncts wrongly, not just unstyled, and a Bengali or Latin font will not render it at all |
| Hasanta | a hasanta mark (like a [virama](../language-terms/writing-systems-and-scripts/virama.md)) suppresses the inherent vowel, marking a word-final consonant or forming a [conjunct](../language-terms/writing-systems-and-scripts/conjunct.md)<sup>7</sup> | Confirm the font marks word-final consonants and forms conjuncts with the hasanta |
| Inherent vowel | each consonant carries an inherent vowel /o/; dependent vowel signs attach to change it (see [abugida](../language-terms/writing-systems-and-scripts/abugida.md))<sup>8</sup> | Dependent vowel signs have to be positioned on the consonant, so test a syllable that changes the inherent vowel |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right<sup>9</sup> | Left-aligned text as the default |
| [Unicode](unicode.md) block | Syloti Nagri, [U+A800 to U+A82F](https://www.unicode.org/charts/PDF/UA800.pdf) | No special handling beyond ensuring [font coverage](font-coverage.md) of the block; pair it with a [keyboard layout](keyboard-layout.md) so people can type it |

### In practice

* **Cover the script and its shaping, and give people a way to type it:** confirm the font ships the Syloti Nagri consonants, independent vowels, dependent vowel signs, and hasanta, AND positions the vowel signs and forms conjuncts, not just the base symbols. Pair it with a [keyboard layout](keyboard-layout.md). [Noto Sans Syloti Nagri](https://fonts.google.com/noto/specimen/Noto+Sans+Syloti+Nagri) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a glyph grid:** set a word that uses a dependent vowel sign and a hasanta or conjunct, and confirm they position and form correctly. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Check the orthography, and which script the community uses:** Sylheti is written in Syloti Nagri, the Bengali-Assamese script, and [Latin](../language-terms/writing-systems-and-scripts/latin-script.md), so do not assume one script. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** for an [endangered](endangered-language.md) or under-resourced script the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Bengali-Assamese](bengali-assamese.md) · [Brahmic scripts](brahmic-scripts.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari](devanagari.md) · [Endangered language](endangered-language.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Keyboard layout](keyboard-layout.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](../language-terms/writing-systems-and-scripts/latin-script.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto Sans Syloti Nagri (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Syloti+Nagri)
* Foundations: [Unicode Syloti Nagri code chart (U+A800)](https://www.unicode.org/charts/PDF/UA800.pdf)

### Sources

1. Syloti Nagri is a lesser-known Brahmi-derived script used for writing the Sylheti language - The Unicode Standard, Version 17.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/)
2. Sylheti is spoken by some 5 million speakers in the Barak Valley region of northeast Bangladesh and southeast Assam in India - The Unicode Standard, Version 17.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/)
3. The Syloti Nagri script has 27 consonant letters with an inherent vowel of /o/ - The Unicode Standard, Version 17.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/)
4. There are 5 independent vowel letters, and 5 dependent vowel signs that are attached to a consonant letter - The Unicode Standard, Version 17.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/)
5. Syloti Nagri is a historical script of the Sylhet region descended from the Kaithi script, with no single known inventor, now the focus of revival (secondary source, interim pending an upgrade to a primary attribution) - Sylheti Nagri (Wikipedia) [https://en.wikipedia.org/wiki/Syloti\_Nagri](https://en.wikipedia.org/wiki/Syloti_Nagri)
6. Syloti Nagri requires both context-sensitive shaping and positioning. Multiple combining marks can attach to a single base letter - Syloti Nagri (r12a script notes) [https://r12a.github.io/scripts/sylo/syl.html](https://r12a.github.io/scripts/sylo/syl.html)
7. U+A806 SYLOTI NAGRI SIGN HASANTA indicates a word-final consonant, or is inserted between consonants to represent a conjunct - The Unicode Standard, Version 17.0, Chapter 15: South and Central Asia-IV [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-15/)
8. The Syloti Nagri script is an abugida, ie. each consonant contains an inherent vowel sound - Syloti Nagri (r12a script notes) [https://r12a.github.io/scripts/sylo/syl.html](https://r12a.github.io/scripts/sylo/syl.html)
9. Syloti Nagri text runs left to right in horizontal lines - Syloti Nagri (r12a script notes) [https://r12a.github.io/scripts/sylo/syl.html](https://r12a.github.io/scripts/sylo/syl.html)
</content>
