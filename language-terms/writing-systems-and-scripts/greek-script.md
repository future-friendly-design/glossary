---
term: Greek script
slug: greek-script
aliases:
  - greek
  - greek alphabet
level: foundational
depth: core
summary: The Greek script is used to write the Greek language.
related:
  - alphabet
  - latin-script
  - cyrillic
  - diacritic
  - font-coverage
status: voice-passed
version_added: 0.1
updated: 2026-07-06T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Standard Scripts (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/standard
    type: code
  - title: Noto Sans Greek (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Greek
    type: design-tool
  - title: Unicode Greek and Coptic code chart (U+0370)
    url: https://www.unicode.org/charts/PDF/U0370.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Greek script

## Definition

The Greek [script](script.md) is used to write the Greek language. It is an [alphabet](alphabet.md) with separate letters for consonants and vowels, and it strongly influenced the development of the [Latin](latin-script.md) and [Cyrillic](cyrillic.md) scripts.<sup>1</sup>

For example, άσπρος ("white") shows the two forms of lowercase sigma, σ in the middle of the word and ς at its end, above the accented vowel ά.

{% hint style="info" %}
This glossary doesn't cover every Greek script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Greek script profile

These properties of the Greek script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                          | Greek script                                                                                                                                                    |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Autonym](../../terms/autonym.md) | Ελληνικό αλφάβητο                                                                                                                                               |
| Languages                         | Greek                                                                                                                                                           |
| Letter case                       | Bicameral (uppercase and lowercase)<sup>2</sup>                                                                                                                 |
| [Marks](mark.md)                  | Modern Greek uses two diacritics, the tonos (stress accent) and the dialytika (diaeresis); classical (polytonic) spelling adds more accents and breathing marks |
| Numerals                          | Common ASCII digits (Greek also has a traditional system that uses letters as numbers)                                                                          |
| Script type                       | [Alphabet](alphabet.md)                                                                                                                                         |
| [Symbols](symbol.md)              | Separate letters for consonants and vowels, in uppercase and lowercase                                                                                          |

### Greek script rules and digital use considerations

If your design system supports languages that use the Greek script, here are some considerations to keep in mind:

| Rule or feature                                           | How it works in the Greek script                                                                                                                                                                                                                                                   | Design systems                                                                                                                                                                              |
| --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Bidirectional text](bidirectional-text.md) | The script runs left to right, but a line can still become bidirectional when right-to-left content (an Arabic or Hebrew name, for example) is embedded in it | Then the embedded right-to-left run needs the Unicode bidirectional algorithm to reorder correctly; isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text<sup>3</sup> |
| [Complex text layout](../../terms/complex-text-layout.md) | Not required                                                                                                                                                                                                                                                                       | A standard left-to-right script, with no [reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) or contextual shaping<sup>4</sup>. See the OpenType and Text shaping rows below                                                                                                       |
| [Diacritics](diacritic.md)                                | Modern (monotonic) Greek marks the stressed vowel with the tonos, and classical (polytonic) spelling uses several marks;<sup>5</sup> monotonic Greek also uses the dialytika, which shows that two adjacent vowel letters are read separately rather than as a digraph<sup>6</sup> | Cover the accented vowels, not just the bare letters; uppercasing drops most accents, so drop nothing by hand and let locale-aware case mapping decide, or the text is misspelled           |
| Final sigma                                               | The lowercase sigma is written ς at the end of a word and σ elsewhere<sup>7</sup>                                                                                                                                                                                                  | A spelling rule, not a style choice: lowercasing Σ must choose ς at a word's end, so use locale-aware case mapping (for example [ICU](../../terms/icu.md)), not a naive per-character lower |
| [OpenType](../../terms/opentype.md) | The font uses standard [OpenType features](../../terms/opentype-features.md): glyph substitution, [kerning](../../terms/kerning.md), and optional ligatures or localized forms; no mandatory shaping features | Confirm the font includes any features your languages rely on (accent composition, localized forms), but no special shaping is required. See the Text shaping row below |
| [Text direction](text-direction.md)                       | [Left to right](left-to-right.md)<sup>8</sup>                                                                                                                                                                                                                                                          | Left-aligned text as the default                                                                                                                                                            |
| [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) | Not required: the [shaping engine](../../terms/shaping-engine.md) places glyphs directly; there are no positional forms, reordering, or mandatory mark positioning | Any tool renders the script correctly as long as the font is present |
| [Unicode](../../terms/unicode.md) block                   | Greek and Coptic, [U+0370 to U+03FF](https://www.unicode.org/charts/PDF/U0370.pdf) (plus Greek Extended, U+1F00 to U+1FFF, for polytonic spelling)                                                                                                                                 | No special handling beyond ensuring [font coverage](../../terms/font-coverage.md) of the block, including Greek Extended if you set polytonic text                                          |

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships both cases AND the accented vowels (with the tonos), not just the bare letters. [Noto Sans Greek](https://fonts.google.com/noto/specimen/Noto+Sans+Greek) is a free, open-licensed option, and [Noto](../../terms/noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Do not treat Greek letters as Latin lookalikes:** Α (Greek alpha) and A (Latin A) are different [characters](../../terms/character.md) with different [code points](../../terms/code-point.md), even when they share a shape. Matching, sorting, or de-duplicating on the shape breaks, and mixing the two invites spoofed text, so validate and compare by script, not by appearance.
* **Mind case and the final sigma when you transform text:** uppercasing Greek drops most accents and turns ς into Σ, and lowercasing Σ should choose ς at the end of a word. Use locale-aware case mapping from a library such as [ICU](../../terms/icu.md), not a naive per-character upper or lower, and pull the conventions from [locale](../../terms/locale.md) data that Unicode's [CLDR](../../terms/cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a language or a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Autonym](../../terms/autonym.md) · [Bidirectional text](bidirectional-text.md) · [Character](../../terms/character.md) · [CLDR](../../terms/cldr.md) · [Code point](../../terms/code-point.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Cyrillic](cyrillic.md) · [Diacritic](diacritic.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [ICU](../../terms/icu.md) · [Kerning](../../terms/kerning.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Left-to-right](left-to-right.md) · [Locale](../../terms/locale.md) · [Mark](mark.md) · [Noto fonts](../../terms/noto-fonts.md) · [OpenType](../../terms/opentype.md) · [OpenType features](../../terms/opentype-features.md) · [Orthography](orthography.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](script.md) · [Script rules](script-rules.md) · [Shaping engine](../../terms/shaping-engine.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Standard Scripts (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/standard)
* Design tools: [Noto Sans Greek (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Greek)
* Foundations: [Unicode Greek and Coptic code chart (U+0370)](https://www.unicode.org/charts/PDF/U0370.pdf)

### Sources

1. The Greek script had a strong influence on the development of the Latin, Cyrillic, and Coptic scripts - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
2. Greek letters come in uppercase and lowercase pairs - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
3. This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
4. Greek is one of the standard (non-complex) scripts, which do not require re-ordering or contextual analysis - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
5. Greek accent marks are used in two styles: monotonic, which uses a single mark called the tonos, and polytonic, which uses multiple marks - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
6. Monotonic Greek on occasion uses a dialytika diacritic to indicate that two adjacent vowel letters don't form a digraph - Greek (r12a script notes) [https://r12a.github.io/scripts/grek/el.html](https://r12a.github.io/scripts/grek/el.html)
7. Greek has a distinct final form of the lowercase sigma, ς, used at the end of a word, as opposed to σ used elsewhere - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
8. The Greek script is written in linear sequence from left to right - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
