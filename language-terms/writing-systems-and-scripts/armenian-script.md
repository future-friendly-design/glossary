---
term: Armenian script
slug: armenian-script
aliases:
  - armenian
level: intermediate
depth: core
summary: The Armenian script is used to write the Armenian language.
related:
  - alphabet
  - greek-script
  - georgian-script
  - font-coverage
  - punctuation-mark
status: voice-passed
version_added: 0.1
updated: 2026-07-06T00:00:00.000Z
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Standard Scripts (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/standard
    type: code
  - title: Noto Sans Armenian (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Armenian
    type: design-tool
  - title: Unicode Armenian code chart (U+0530)
    url: https://www.unicode.org/charts/PDF/U0530.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Armenian script

## Definition

The Armenian [script](script.md) is used to write the Armenian language. It is an [alphabet](alphabet.md) with its own distinctive letters for consonants and vowels.

For example, ծուխ ("smoke") is written in letters unique to Armenian.

The Armenian script was devised about 406 CE by Mesrop Mashtots to give Armenians access to Christian texts, which were previously available only in Greek and Syriac.<sup>1</sup>

{% hint style="info" %}
This glossary doesn't cover every Armenian script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Armenian script profile

These properties of the Armenian script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                             | Armenian script                                                                                                                                                      |
| ------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Autonym](../linguistics/autonym.md) | Հայոց այբուբեն                                                                                                                                                       |
| Languages                            | Armenian                                                                                                                                                             |
| Letter case                          | Bicameral (uppercase and lowercase)<sup>2</sup>                                                                                                                      |
| [Marks](mark.md)                     | No combining vowel or tone marks; Armenian has its own [punctuation marks](punctuation-mark.md) for questions, exclamation, and emphasis, and the ligature և ("and") |
| Numerals                             | Common ASCII digits (Armenian letters also carry traditional numeric values)                                                                                         |
| Script type                          | [Alphabet](alphabet.md)                                                                                                                                              |
| [Symbols](symbol.md)                 | Separate letters for consonants and vowels, in uppercase and lowercase                                                                                               |

### Armenian script rules and digital use considerations

If your design system supports languages that use the Armenian script, here are some considerations to keep in mind:

| Rule or feature                                                                                             | How it works in the Armenian script                                                                                                                                                                                                                                                         | Design systems                                                                                                                                                                                                                         |
| ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Bidirectional text](bidirectional-text.md)                                                                 | The script runs left to right, but a line can still become bidirectional when right-to-left content (an Arabic or Hebrew name, for example) is embedded in it                                                                                                                               | Then the embedded right-to-left run needs the Unicode bidirectional algorithm to reorder correctly; isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text<sup>3</sup>                 |
| [Complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) | Not required                                                                                                                                                                                                                                                                                | A standard left-to-right script, with no [reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) or contextual shaping<sup>4</sup>. See the OpenType and Text shaping rows below                     |
| [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) (open source)                 | [Noto Sans Armenian](https://fonts.google.com/noto/specimen/Noto+Sans+Armenian) is a free, open-source font from Google's [Noto](../../design-terms/typography/noto-fonts.md) project, covering the script's characters and the OpenType features they need (see OpenType and Text shaping) | Treat the typeface as a foundational choice, and confirm it covers every language you support that uses the script (see [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md)), not just one |
| [OpenType](../../design-terms/typography/opentype.md)                                                       | The font uses standard [OpenType features](../../design-terms/typography/opentype-features.md): glyph substitution, [kerning](../../design-terms/typography/kerning.md), and optional ligatures or localized forms; no mandatory shaping features                                           | Confirm the font includes any features your languages rely on (accent composition, localized forms), but no special shaping is required. See the Text shaping row below                                                                |
| [Punctuation mark](punctuation-mark.md)                                                                     | Armenian uses its own marks; the question and emphasis marks sit above a word's stressed vowel rather than at the end of the sentence<sup>5</sup>                                                                                                                                           | Test [line-height](../../design-terms/typography/line-height.md) so the above-marks don't clip, and don't tighten [leading](../../design-terms/typography/leading.md) blindly                                                          |
| [Text direction](text-direction.md)                                                                         | [Left to right](left-to-right.md)<sup>6</sup>                                                                                                                                                                                                                                               | Left-aligned text as the default                                                                                                                                                                                                       |
| [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md)               | Not required: the [shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md) places glyphs directly; there are no positional forms, reordering, or mandatory mark positioning                                                                        | Any tool renders the script correctly as long as the font is present                                                                                                                                                                   |
| [Unicode](../../programming-terms/text-in-software/unicode.md) block                                        | Armenian, [U+0530 to U+058F](https://www.unicode.org/charts/PDF/U0530.pdf)                                                                                                                                                                                                                  | No special handling beyond ensuring [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) of the block                                                                                       |

### In practice

* **Cover the script before you commit a typeface:** Armenian is a common gap in fonts built mainly for Latin or the other large scripts, so a font that looks complete may ship no Armenian glyphs at all. Confirm coverage explicitly, both cases. See [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md).
* **Use Armenian's own punctuation, not ASCII substitutes:** the question, exclamation, and emphasis marks are distinct [characters](../../programming-terms/text-in-software/character.md) placed above a stressed vowel, not a trailing "?" or "!", and the ligature և stands for "and". Use the correct characters, and pull the conventions from [locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) data that Unicode's [CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md) publishes.
* **Confirm rendering with a reader, not just a glyph grid:** because the script serves essentially one community, check that letters, both cases, punctuation, and any [ligature](../../programming-terms/text-for-digital-products-and-the-web/ligature.md) render correctly with people who read Armenian, not by eye alone.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Autonym](../linguistics/autonym.md) · [Bidirectional text](bidirectional-text.md) · [Character](../../programming-terms/text-in-software/character.md) · [CLDR](../../programming-terms/text-for-digital-products-and-the-web/cldr.md) · [Complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) · [Cyrillic script](cyrillic.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) · [Georgian script](georgian-script.md) · [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md) · [Greek script](greek-script.md) · [Kerning](../../design-terms/typography/kerning.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Leading](../../design-terms/typography/leading.md) · [Left-to-right](left-to-right.md) · [Ligature](../../programming-terms/text-for-digital-products-and-the-web/ligature.md) · [Line height](../../design-terms/typography/line-height.md) · [Locale](../../programming-terms/text-for-digital-products-and-the-web/locale.md) · [Mark](mark.md) · [Noto fonts](../../design-terms/typography/noto-fonts.md) · [OpenType](../../design-terms/typography/opentype.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Orthography](orthography.md) · [Punctuation mark](punctuation-mark.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](script.md) · [Script rules](script-rules.md) · [Shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](../../design-terms/typography/typeface.md) · [Unicode](../../programming-terms/text-in-software/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Standard Scripts (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/standard)
* Design tools: [Noto Sans Armenian (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Armenian)
* Foundations: [Unicode Armenian code chart (U+0530)](https://www.unicode.org/charts/PDF/U0530.pdf)

### Sources

1. The Armenian script was devised about 406 CE by Mesrop Mashtots to give Armenians access to Christian scriptural and liturgical texts, which were otherwise available only in Greek and Syriac - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
2. The Armenian script is bicameral, with uppercase and lowercase letters - Armenian (r12a script notes) [https://r12a.github.io/scripts/armn/hy.html](https://r12a.github.io/scripts/armn/hy.html)
3. This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
4. Armenian is one of the standard (non-complex) scripts, which do not require re-ordering or contextual analysis - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
5. Armenian has its own punctuation marks, including distinct marks for questions, exclamation, and emphasis - Armenian (r12a script notes) [https://r12a.github.io/scripts/armn/hy.html](https://r12a.github.io/scripts/armn/hy.html)
6. Armenian text runs left to right - Armenian (r12a script notes) [https://r12a.github.io/scripts/armn/hy.html](https://r12a.github.io/scripts/armn/hy.html)
