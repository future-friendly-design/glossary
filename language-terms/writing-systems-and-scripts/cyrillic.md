---
term: Cyrillic
slug: cyrillic
aliases:
  - Cyrillic script
level: foundational
depth: core
summary: >-
  Cyrillic is a script used to write Russian, Bulgarian, Serbian, and many other
  languages of Eastern Europe, the Caucasus, and northern and central Asia.
related:
  - alphabet
  - latin-script
  - greek-script
  - font-coverage
  - opentype
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
  - title: Unicode Cyrillic code chart (U+0400)
    url: https://www.unicode.org/charts/PDF/U0400.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Cyrillic script

## Definition

Cyrillic is a [script](script.md) used to write Russian, Bulgarian, Serbian, and many other languages of Eastern Europe, the Caucasus, and northern and central Asia.<sup>1</sup> It is an [alphabet](alphabet.md) with separate letters for consonants and vowels, derived from the [Greek](greek-script.md) script. <sup>2</sup>&#x20;

For example, the Russian word мир ("world") is written with Cyrillic letters, each one standing for a sound.

The term "Cyrillic" honours the Byzantine brothers Cyril and Methodius,<sup>3</sup> though the details of its early history have been lost.<sup>4</sup>

{% hint style="info" %}
This glossary doesn't cover every Cyrillic property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Cyrillic profile

These properties of Cyrillic apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                          | Cyrillic                                                                                                                  |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| [Autonym](../../terms/autonym.md) | Кириллица                                                                                                                 |
| Languages                         | Russian, Ukrainian, Bulgarian, Serbian, Mongolian, and many others                                                        |
| Letter case                       | Bicameral (uppercase and lowercase)<sup>5</sup>                                                                           |
| [Marks](mark.md)                  | No combining vowel or tone marks; an optional stress accent (acute) appears mainly in dictionaries and learning materials |
| Numerals                          | Common ASCII digits (an archaic Cyrillic numeral system also exists)                                                      |
| Script type                       | [Alphabet](alphabet.md)                                                                                                   |
| [Symbols](symbol.md)              | Separate letters for consonants and vowels, in uppercase and lowercase                                                    |

### Cyrillic rules and digital use considerations

If your design system supports languages that use Cyrillic, here are some considerations to keep in mind:

| Rule or feature                                           | How it works in Cyrillic                                                                                                                                                                      | Design systems                                                                                                                                                                                |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Complex text layout](../../terms/complex-text-layout.md) | Not required                                                                                                                                                                                  | A standard left-to-right script, with no reordering or contextual shaping<sup>6</sup>                                                                                                         |
| Localized forms                                           | some letters take language-specific shapes,<sup>8</sup> which the [OpenType](../../terms/opentype.md) localized-forms (`locl`) feature selects using the text's declared language<sup>9</sup> | "Supports Cyrillic" is not a single guarantee; declare each content language so Russian, Serbian, and Bulgarian get their own letterforms, or the text can read as foreign to a native reader |
| [Text direction](text-direction.md)                       | Left to right<sup>7</sup>                                                                                                                                                                     | Left-aligned text as the default                                                                                                                                                              |
| [Unicode](../../terms/unicode.md) block                   | Cyrillic, [U+0400 to U+04FF](https://www.unicode.org/charts/PDF/U0400.pdf) (plus Cyrillic Supplement and the Cyrillic Extended blocks)                                                        | No special handling beyond ensuring [font coverage](../../terms/font-coverage.md) of the block, including the Supplement and Extended blocks                                                  |

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships both cases AND the localized forms for the specific languages you support, since Russian, Serbian, and Bulgarian differ in both their letterforms and, for some languages, the specific letters they use. [Noto Sans](https://fonts.google.com/noto/specimen/Noto+Sans) covers Cyrillic, and [Noto](../../terms/noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Declare the language so the right letterforms appear:** the per-language shapes are selected from the text's language, so tag content with its language and use a font that carries the [OpenType](../../terms/opentype.md) localized forms; do not assume one Cyrillic rendering fits Russian, Serbian, and Bulgarian alike. Pull the conventions from [locale](../../terms/locale.md) data that Unicode's [CLDR](../../terms/cldr.md) publishes.
* **Do not treat Cyrillic letters as Latin lookalikes:** а (Cyrillic) and a (Latin) are different [characters](../../terms/character.md) with different code points, even when they share a shape. Matching, sorting, or de-duplicating on the shape breaks, and mixing the two invites spoofed text, so validate and compare by script, not by appearance.
* **If a rule above is not documented, you may be the source:** the conventions for a language or a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Autonym](../../terms/autonym.md) · [Character](../../terms/character.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Greek script](greek-script.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Locale](../../terms/locale.md) · [Mark](mark.md) · [Noto fonts](../../terms/noto-fonts.md) · [OpenType](../../terms/opentype.md) · [Orthography](orthography.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Standard Scripts (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/standard)
* Design tools: [Noto Sans (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans)
* Foundations: [Unicode Cyrillic code chart (U+0400)](https://www.unicode.org/charts/PDF/U0400.pdf)

### Sources

1. Cyrillic is used for Slavic languages and, in its extended form, for Turkic languages such as Azerbaijani, Kazakh, and Tatar, Caucasian languages such as Abkhaz, Avar, and Chechen, and Uralic languages such as Mari and Khanty - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
2. The Cyrillic script is one of several scripts that were ultimately derived from the Greek script - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
3. The script is named in honor of the two Byzantine brothers, Saints Cyril and Methodius, who created the earlier Glagolitic alphabet; modern scholars believe that Cyrillic was developed and formalized by early disciples of Cyril and Methodius - Cyrillic (r12a script notes) [https://r12a.github.io/scripts/cyrl/ru.html](https://r12a.github.io/scripts/cyrl/ru.html)
4. The details of the history of the development of the Cyrillic script, and of the relationship between early writing systems for Slavic languages, have been lost - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
5. Cyrillic letters have uppercase and lowercase pairs - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
6. Cyrillic is one of the standard (non-complex) scripts, which do not require re-ordering or contextual analysis - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
7. The Cyrillic script is written in linear sequence from left to right - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
8. The shapes of the italic forms of Cyrillic letters can vary by language - Cyrillic (r12a script notes) [https://r12a.github.io/scripts/cyrl/ru.html](https://r12a.github.io/scripts/cyrl/ru.html)
9. The Localized Forms (locl) feature enables localized forms of glyphs to be substituted for default forms; several letters in the Bulgarian and Serbian alphabets have forms distinct from their Russian counterparts, and language tagging indicating the language of the text is used to select the most appropriate forms - Registered features, k-o (OpenType 1.9.1), Microsoft [https://learn.microsoft.com/en-us/typography/opentype/spec/features\_ko#locl](https://learn.microsoft.com/en-us/typography/opentype/spec/features_ko#locl)
