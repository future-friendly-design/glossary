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

# Cyrillic

## Definition

Cyrillic is a [script](script.md) used to write Russian, Bulgarian, Serbian, and many other languages of Eastern Europe, the Caucasus, and northern and central Asia.<sup>1</sup> It is an [alphabet](alphabet.md) with separate letters for consonants and vowels, derived from the [Greek](greek-script.md) script;<sup>2</sup> its name honours the ninth-century missionary Cyril,<sup>3</sup> though the details of its early history have been lost.<sup>4</sup>

For example, the Russian word мир ("world") is written with Cyrillic letters, each one standing for a sound.

Cyrillic is one script within the writing system of each language that uses it. This page describes the script itself; how a given language uses it, its spelling, punctuation, and which symbols, is that language's [orthography](orthography.md).

### At a glance

| Property                                                  | Cyrillic                                                                                                                               |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Script type                                               | [Alphabet](alphabet.md)                                                                                                                |
| Autonym                                                   | Кириллица                                                                                                                              |
| Symbols                                                   | separate letters for consonants and vowels, in uppercase and lowercase                                                                 |
| Marks                                                     | few; Cyrillic is written mostly with base letters, and stress marks appear mainly in dictionaries and learning materials               |
| Letter case                                               | Bicameral (uppercase and lowercase)                                                                                                    |
| Numerals                                                  | common ASCII digits (an archaic Cyrillic numeral system also exists)                                                                   |
| Unicode block                                             | Cyrillic, [U+0400 to U+04FF](https://www.unicode.org/charts/PDF/U0400.pdf) (plus Cyrillic Supplement and the Cyrillic Extended blocks) |
| [Complex text layout](../../terms/complex-text-layout.md) | Not required; Cyrillic lays out left to right, like Latin                                                                              |
| Languages                                                 | Russian, Ukrainian, Bulgarian, Serbian, Mongolian, and many others                                                                     |

### Script rules and features

Script rules apply to any language that uses Cyrillic in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature                     | How it works in Cyrillic                                                                                                                                                                                                        |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Text direction](text-direction.md) | Left to right                                                                                                                                                                                                                   |
| Letter case                         | bicameral: separate uppercase and lowercase forms                                                                                                                     |
| Localized forms                     | some letters take language-specific shapes, which the [OpenType](../../terms/opentype.md) localized-forms feature selects from the text's language, so the same letters are set differently for Russian, Serbian, and Bulgarian |

### Why it matters in design systems

Treat this entry as a starting playbook for Cyrillic, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](../../terms/typeface.md) and [font](../../terms/font.md) with Cyrillic coverage, because the rules below will not render without it.

Where you cannot be creative is the script rules. Text runs left to right, the direction Western tools already assume,<sup>5</sup> and Cyrillic is bicameral, with two cases.<sup>6</sup> The constraint that catches teams is coverage across languages: Cyrillic serves dozens of them, so "supports Cyrillic" is not a single guarantee. Languages use overlapping but different letter sets, and some letters are shaped differently by language;<sup>7</sup> several italic letters, for example, differ in Serbian and Bulgarian from Russian. A font has to carry the letters AND the language's forms, which the [OpenType](../../terms/opentype.md) localized-forms feature selects from the text's declared language. Pick the wrong forms and the text reads as foreign to a native reader, even though every letter is present.

Everything else is a free design choice: the typeface's personality, weight, size, colour, and spacing, within what the script needs (real Cyrillic glyphs and the right per-language forms, not Latin lookalikes) and what the language's [orthography](orthography.md) calls for. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships both cases AND the localized forms for the specific languages you support, since Russian, Serbian, and Bulgarian differ. [Noto Sans](https://fonts.google.com/noto/specimen/Noto+Sans) covers Cyrillic, and [Noto](../../terms/noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Declare the language so the right letterforms appear:** the per-language shapes are selected from the text's language, so tag content with its language and use a font that carries the [OpenType](../../terms/opentype.md) localized forms; do not assume one Cyrillic rendering fits Russian, Serbian, and Bulgarian alike. Pull the conventions from [locale](../../terms/locale.md) data that Unicode's [CLDR](../../terms/cldr.md) publishes.
* **Do not treat Cyrillic letters as Latin lookalikes:** а (Cyrillic) and a (Latin) are different [characters](../../terms/character.md) with different code points, even when they share a shape. Matching, sorting, or de-duplicating on the shape breaks, and mixing the two invites spoofed text, so validate and compare by script, not by appearance.
* **If a rule above is not documented, you may be the source:** the conventions for a language or a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Autonym](../../terms/autonym.md) · [Character](../../terms/character.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Greek script](greek-script.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Locale](../../terms/locale.md) · [Noto fonts](../../terms/noto-fonts.md) · [OpenType](../../terms/opentype.md) · [Orthography](orthography.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Design tools: [Noto Sans (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans)
* Foundations: [Unicode Cyrillic code chart (U+0400)](https://www.unicode.org/charts/PDF/U0400.pdf)

### Sources

1. Cyrillic is used for Slavic languages and, in its extended form, for Turkic languages such as Azerbaijani, Kazakh, and Tatar, Caucasian languages such as Abkhaz, Avar, and Chechen, and Uralic languages such as Mari and Khanty - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
2. The Cyrillic script is one of several scripts that were ultimately derived from the Greek script - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
3. The Cyrillic script is named in honour of Saint Cyril, one of the two Byzantine brothers Cyril and Methodius, though scholars believe it was developed and formalized by their disciples - Cyrillic (r12a script notes) [https://r12a.github.io/scripts/cyrl/ru.html](https://r12a.github.io/scripts/cyrl/ru.html)
4. The details of the history of the development of the Cyrillic script, and of the relationship between early writing systems for Slavic languages, have been lost - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
5. The Cyrillic script is written in linear sequence from left to right - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
6. Cyrillic letters have uppercase and lowercase pairs - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
7. The shapes of the italic forms of Cyrillic letters can vary by language - Cyrillic (r12a script notes) [https://r12a.github.io/scripts/cyrl/ru.html](https://r12a.github.io/scripts/cyrl/ru.html)
