---
term: Latin script
slug: latin-script
aliases:
  - Roman script
  - Roman alphabet
level: foundational
depth: core
summary: >-
  The Latin script is used to write a wide variety of languages all over the
  world.
related:
  - alphabet
  - cyrillic
  - greek-script
  - diacritic
  - orthography
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-06T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Standard Scripts (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/standard
    type: code
  - title: Noto Sans (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans
    type: design-tool
  - title: Unicode Basic Latin code chart (U+0000)
    url: https://www.unicode.org/charts/PDF/U0000.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Latin script

## Definition

The Latin [script](script.md) is used to write a wide variety of languages all over the world.<sup>1</sup> It is an [alphabet](alphabet.md), with separate symbols for consonants and vowels, and its letters come in uppercase and lowercase pairs.<sup>2</sup>&#x20;

For example, the Vietnamese phrase Tiếng Việt ("Vietnamese") extends the basic letters with stacked accent marks, one of countless ways languages adapt the script to their own sounds.

The Latin alphabet descends from the one the Etruscans adopted from a Western variant of the classical [Greek](greek-script.md) alphabet.<sup>3</sup>

{% hint style="info" %}
This glossary doesn't cover every Latin script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Latin script profile

These properties of the Latin script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                          | Latin script                                                                                                                         |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| [Autonym](../../terms/autonym.md) | Latin                                                                                                                                |
| Languages                         | English, Spanish, French, Vietnamese, Turkish, Yoruba, and hundreds of others                                                        |
| Letter case                       | Bicameral: uppercase and lowercase pairs (case conversion is locale-sensitive, for example Turkish dotted and dotless i)             |
| [Marks](mark.md)                  | [Diacritics](diacritic.md) (acute, grave, circumflex, tilde, cedilla, and others), available both precomposed and as combining marks |
| Numerals                          | European digits 0 to 9 (shared "common" digits, not unique to the Latin script)                                                      |
| Script type                       | [Alphabet](alphabet.md)                                                                                                              |
| [Symbols](symbol.md)              | Letters for consonants and vowels (the basic 26), extended per language with accented and additional letters                         |

### Latin script rules and digital use considerations

If your design system supports languages that use the Latin script, here are some considerations to keep in mind:

| Rule or feature                                           | How it works in the Latin script                                                                                                                                                                                 | Design systems                                                                                                                                                                                                                                                                                                                                                             |
| --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Complex text layout](../../terms/complex-text-layout.md) | Not required                                                                                                                                                                                                     | A standard, non-complex script that needs no reordering or contextual analysis to shape, so almost every font and tool handles it<sup>4</sup>                                                                                                                                                                                                                              |
| [Diacritics](diacritic.md)                                | Accents and other marks extend the basic letters; they exist both as precomposed letters and as combining marks positioned on a base                                                                             | Only a small fraction of Latin-written languages use just the basic 26 letters,<sup>5</sup> so ship the accented and additional letters your languages need; the font's [OpenType](../../terms/opentype.md) rules and the platform's [text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) position combining marks at render time |
| Letter case                                               | Letters come in uppercase and lowercase pairs, and case conversion follows rules that depend on the language, not just the letter                                                                                | Case conversion is locale-sensitive (for example Turkish dotted and dotless i), so use locale-aware case mapping, not a naive per-character upper or lower                                                                                                                                                                                                                 |
| [Ligature](../../terms/ligature.md)                       | Optional typographic ligatures such as fi and fl are an aesthetic choice, not a requirement of the script; the [OpenType](../../terms/opentype.md) standard ligatures (`liga`) feature supplies them<sup>6</sup> | A free styling choice: enable them for polish, but nothing breaks without them                                                                                                                                                                                                                                                                                             |
| [Text direction](text-direction.md)                       | Left to right<sup>7</sup>                                                                                                                                                                                        | Left-aligned text as the default                                                                                                                                                                                                                                                                                                                                           |
| [Unicode](../../terms/unicode.md) block                   | Basic Latin, [U+0000 to U+007F](https://www.unicode.org/charts/PDF/U0000.pdf) (plus Latin-1 Supplement, Latin Extended-A and B, and more)                                                                        | No special handling beyond ensuring [font coverage](../../terms/font-coverage.md) across the blocks your languages need, not just Basic Latin                                                                                                                                                                                                                              |

### In practice

* **Cover the languages, not just the alphabet:** confirm the font ships the accented and additional letters and combining [diacritics](diacritic.md) your languages need, not only the basic 26. [Noto Sans](https://fonts.google.com/noto/specimen/Noto+Sans) is a free, open-licensed option with broad Latin coverage, and [Noto](../../terms/noto-fonts.md) reaches languages where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Test with a real word, not "The quick brown fox":** type a word that stacks diacritics, such as Tiếng Việt, and a word that tests casing, such as Istanbul in Turkish, and confirm the marks position and the case converts correctly. Tool support varies, so test early.
* **Check the orthography, not just the script, before reusing symbols across languages:** two languages can share the Latin script and still differ in which letters they use and how they case them. Do not hardcode one language's choices; pull them from [locale](../../terms/locale.md) data. Unicode's [CLDR](../../terms/cldr.md) publishes per-language conventions, including casing rules, as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Autonym](../../terms/autonym.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Cyrillic](cyrillic.md) · [Diacritic](diacritic.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Greek script](greek-script.md) · [Language](../linguistics/language.md) · [Ligature](../../terms/ligature.md) · [Locale](../../terms/locale.md) · [Mark](mark.md) · [Noto fonts](../../terms/noto-fonts.md) · [OpenType](../../terms/opentype.md) · [Orthography](orthography.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Standard Scripts (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/standard)
* Design tools: [Noto Sans (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans)
* Foundations: [Unicode Basic Latin code chart (U+0000)](https://www.unicode.org/charts/PDF/U0000.pdf)

### Sources

1. The Latin script is used to write a wide variety of languages all over the world - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
2. Latin letters come in uppercase and lowercase pairs - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
3. The Latin alphabet is derived from the alphabet used by the Etruscans, who had adopted a Western variant of the classical Greek alphabet - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
4. In this document, "standard" refers to any non-complex script, that is, any script that does not require re-ordering or contextual analysis - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
5. Only a small fraction of the languages written with the Latin script can be written entirely with the basic set of 26 uppercase and 26 lowercase Latin letters - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
6. The Standard Ligatures (liga) feature replaces a sequence of glyphs with a single glyph which is preferred for typographic purposes; for example, the glyph for ffl replaces the sequence of glyphs f f l - Registered features, k-o (OpenType 1.9.1), Microsoft [https://learn.microsoft.com/en-us/typography/opentype/spec/features\_ko#liga](https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko#liga)
7. The Latin script is written in linear sequence from left to right - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
