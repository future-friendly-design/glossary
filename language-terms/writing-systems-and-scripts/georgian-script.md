---
term: Georgian script (Mkhedruli)
slug: georgian-script
aliases:
  - georgian
  - mkhedruli
  - Georgian script
level: intermediate
depth: core
summary: >-
  The Georgian script is used mainly to write the Georgian language, and also
  the Mingrelian and Svan languages of the Caucasus.
related:
  - alphabet
  - armenian-script
  - greek-script
  - small-caps
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
  - title: Noto Sans Georgian (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Georgian
    type: design-tool
  - title: Unicode Georgian code chart (U+10A0)
    url: https://www.unicode.org/charts/PDF/U10A0.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Georgian script

## Definition

The Georgian [script](script.md) is used mainly to write the Georgian language, and also the Mingrelian and Svan languages of the Caucasus.<sup>1</sup> Its modern everyday form is called Mkhedruli, an [alphabet](alphabet.md) with its own letters for consonants and vowels;<sup>2</sup> everyday Georgian is written in this one set of letters, with no capital at the start of a word or a sentence.<sup>3</sup> A second set of letters, Mtavruli, is used for whole words in titles and for emphasis, and since Unicode 11.0 software treats Mtavruli as the uppercase of Mkhedruli.<sup>4</sup>

For example, ადამიანი ("person") is written in Mkhedruli letters, with no capital at the start.

The Georgian script was devised in the fifth century, under the influence of Greek.<sup>5</sup>

{% hint style="info" %}
This glossary doesn't cover every Georgian script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Georgian script profile

These properties of the Georgian script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                             | Georgian script                                                                                                                                                                                                                                                    |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Autonym](../linguistics/autonym.md) | მხედრული                                                                                                                                                                                                                                                           |
| Languages                            | Georgian; also Mingrelian and Svan                                                                                                                                                                                                                                 |
| Letter case                          | One set of letters in everyday text, with no capital at the start of a word or a sentence. Since Unicode 11.0, each Mkhedruli letter (lowercase) is paired with a Mtavruli letter (uppercase); Mtavruli is used for whole words in titles and emphasis<sup>6</sup> |
| [Marks](mark.md)                     | No combining vowel or tone marks; Georgian is written with base letters and uses essentially no diacritics                                                                                                                                                         |
| Numerals                             | Common ASCII digits                                                                                                                                                                                                                                                |
| Script type                          | [Alphabet](alphabet.md)                                                                                                                                                                                                                                            |
| [Symbols](symbol.md)                 | Separate letters for consonants and vowels, a single set with no case                                                                                                                                                                                              |

### Georgian script rules and digital use considerations

If your design system supports languages that use the Georgian script, here are some considerations to keep in mind:

| Rule or feature                                                                                             | How it works in the Georgian script                                                                                                                                                                                                                                                         | Design systems                                                                                                                                                                                                                                                                                                                                                           |
| ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Bidirectional text](bidirectional-text.md)                                                                 | The script runs left to right, but a line can still become bidirectional when right-to-left content (an Arabic or Hebrew name, for example) is embedded in it                                                                                                                               | Then the embedded right-to-left run needs the Unicode bidirectional algorithm to reorder correctly; isolate embedded content whose direction you do not control, so it cannot disturb the surrounding text<sup>7</sup>                                                                                                                                                   |
| [Complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) | Not required                                                                                                                                                                                                                                                                                | A standard left-to-right script, with no [reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) or contextual shaping<sup>8</sup>. See the OpenType and Text shaping rows below                                                                                                                                                       |
| [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) (open source)                 | [Noto Sans Georgian](https://fonts.google.com/noto/specimen/Noto+Sans+Georgian) is a free, open-source font from Google's [Noto](../../design-terms/typography/noto-fonts.md) project, covering the script's characters and the OpenType features they need (see OpenType and Text shaping) | Treat the typeface as a foundational choice, and confirm it covers every language you support that uses the script (see [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md)), not just one                                                                                                                                   |
| Letter case                                                                                                 | Everyday Mkhedruli uses one set of letters, with no capital at the start of a word or a sentence. In Unicode's character data each Mkhedruli letter has an uppercase partner in Mtavruli and no separate form for title casing<sup>9</sup>                                                  | Title casing and "capitalize each word" change nothing. An uppercase text style is different: by Unicode's rules it replaces the letters with Mtavruli, but some browsers leave the text unchanged<sup>10</sup>. Test it, and check that the font has Mtavruli shapes. See [case mapping](../../programming-terms/internationalization-and-localization/case-mapping.md) |
| Mtavruli                                                                                                    | An all-caps style of Mkhedruli used for titles and emphasis, which behaves like all-caps rather than a sentence-initial capital<sup>11</sup>                                                                                                                                                | Reach for Mtavruli deliberately when you want an all-caps effect; don't fake capitals by scaling letters or forcing automatic title casing                                                                                                                                                                                                                               |
| [OpenType](../../design-terms/typography/opentype.md)                                                       | The font uses standard [OpenType features](../../design-terms/typography/opentype-features.md): glyph substitution, [kerning](../../design-terms/typography/kerning.md), and optional ligatures or localized forms; no mandatory shaping features                                           | Confirm the font includes any features your languages rely on (accent composition, localized forms), but no special shaping is required. See the Text shaping row below                                                                                                                                                                                                  |
| [Text direction](text-direction.md)                                                                         | [Left to right](left-to-right.md)<sup>12</sup>                                                                                                                                                                                                                                              | Left-aligned text as the default                                                                                                                                                                                                                                                                                                                                         |
| [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md)               | Not required: the [shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md) places glyphs directly; there are no positional forms, reordering, or mandatory mark positioning                                                                        | Any tool renders the script correctly as long as the font is present                                                                                                                                                                                                                                                                                                     |
| [Unicode](../../programming-terms/text-in-software/unicode.md) block                                        | Georgian, [U+10A0 to U+10FF](https://www.unicode.org/charts/PDF/U10A0.pdf) (plus Georgian Extended for Mtavruli and Georgian Supplement)                                                                                                                                                    | No special handling beyond ensuring [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) of the block; a less widely covered script, so a font built mainly for Latin or the other large scripts may carry no Georgian glyphs                                                                                                 |

### In practice

* **Cover the script before you commit a typeface:** a less widely covered script like Georgian is a common gap in fonts built mainly for Latin or the other large scripts, so a font that looks complete may ship no Georgian glyphs. Confirm coverage explicitly. See [font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md).
* **Do not rely on case-based styling:** title casing and "capitalize each word" change nothing in Mkhedruli, because Georgian does not put a capital at the start of a word or a sentence. An uppercase text style is different: by Unicode's rules it replaces the letters with Mtavruli, but some browsers leave the text unchanged, so test it and check that the font has Mtavruli shapes (see [case mapping](../../programming-terms/internationalization-and-localization/case-mapping.md)). When you want an all-caps effect for a heading or emphasis, reach for Mtavruli deliberately rather than scaling letters or faking capitals.
* **Confirm rendering with a reader, not just a glyph grid:** because relatively few fonts cover Georgian, check that the letters and any Mtavruli emphasis render and read correctly with people who read it. Pull the conventions from [locale](../../programming-terms/internationalization-and-localization/locale.md) data that Unicode's [CLDR](../../programming-terms/internationalization-and-localization/cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Armenian script](armenian-script.md) · [Autonym](../linguistics/autonym.md) · [Bidirectional text](bidirectional-text.md) · [Case mapping](../../programming-terms/internationalization-and-localization/case-mapping.md) · [CLDR](../../programming-terms/internationalization-and-localization/cldr.md) · [Complex text layout](../../programming-terms/text-for-digital-products-and-the-web/complex-text-layout.md) · [Cyrillic script](cyrillic.md) · [Font](../../programming-terms/text-for-digital-products-and-the-web/font.md) · [Font coverage](../../programming-terms/text-for-digital-products-and-the-web/font-coverage.md) · [Glyph](../../programming-terms/text-for-digital-products-and-the-web/glyph.md) · [Greek script](greek-script.md) · [Kerning](../../design-terms/typography/kerning.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Left-to-right](left-to-right.md) · [Locale](../../programming-terms/internationalization-and-localization/locale.md) · [Mark](mark.md) · [Noto fonts](../../design-terms/typography/noto-fonts.md) · [OpenType](../../design-terms/typography/opentype.md) · [OpenType features](../../design-terms/typography/opentype-features.md) · [Orthography](orthography.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](script.md) · [Script rules](script-rules.md) · [Shaping engine](../../programming-terms/text-for-digital-products-and-the-web/shaping-engine.md) · [Small caps](../../design-terms/typography/small-caps.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Text shaping](../../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](../../design-terms/typography/typeface.md) · [Unicode](../../programming-terms/text-in-software/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Standard Scripts (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/standard)
* Design tools: [Noto Sans Georgian (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Georgian)
* Foundations: [Unicode Georgian code chart (U+10A0)](https://www.unicode.org/charts/PDF/U10A0.pdf)

### Sources

1. The Georgian script is used primarily for writing the Georgian language and its dialects. It is also used for the Svan and Mingrelian languages and in the past was used for Abkhaz and other languages of the Caucasus - The Unicode Standard, Version 18.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
2. The everyday form of the Georgian script is an alphabet called Mkhedruli, which is used for nearly all modern Georgian writing - The Unicode Standard, Version 18.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
3. "The Georgian Mkhedruli alphabet has been fundamentally caseless since its development" - The Unicode Standard, Version 18.0, Chapter 7: Europe-I, section 7.7 Georgian [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
4. "For most of modern Mkhedruli writing, Mtavruli has been used as an emphatic or headline style. In Version 11.0 of the Unicode Standard, that usage was broadened to define formal case pair mappings between these forms, with Mkhedruli serving as lowercase and Mtavruli serving as uppercase" - The Unicode Standard, Version 18.0, Chapter 7: Europe-I, section 7.7 Georgian [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
5. The Georgian and Armenian scripts were devised in the fifth century and are influenced by Greek - The Unicode Standard, Version 18.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
6. "These Mtavruli letters have a casing relationship defined with Mkhedruli letters: the Mtavruli letters are the uppercase forms of the Mkhedruli letters, which now are considered lowercase forms" - The Unicode Standard, Version 18.0, Chapter 7: Europe-I, section 7.7 Georgian [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
7. This annex describes specifications for the positioning of characters in text containing characters flowing from right to left, such as Arabic or Hebrew - Unicode Standard Annex #9: Unicode Bidirectional Algorithm [https://www.unicode.org/reports/tr9/](https://www.unicode.org/reports/tr9/)
8. Georgian is one of the standard (non-complex) scripts, which do not require re-ordering or contextual analysis - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
9. "Georgian casing established in Version 11.0 does not extend to title casing, as the Georgian script does not have title casing for individual words or sentences" - The Unicode Standard, Version 18.0, Chapter 7: Europe-I, section 7.7 Georgian [https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode18.0.0/core-spec/chapter-7/)
10. "These tests check whether mkedruli characters are converted to mtavruli characters (new in Unicode v11) when text-transform:uppercase is applied to the former", with recorded results of fail for Firefox and for Chrome and pass for Safari - Summarized test results: case conversion, W3C Internationalization [https://www.w3.org/International/i18n-tests/results/case-conversion](https://www.w3.org/International/i18n-tests/results/case-conversion)
11. Mtavruli is a set of capital forms used for titles and emphasis that behaves like all-caps rather than a sentence-initial capital - Georgian (r12a script notes) [https://r12a.github.io/scripts/geor/ka.html](https://r12a.github.io/scripts/geor/ka.html)
12. Georgian text runs left to right in horizontal lines - Georgian (r12a script notes) [https://r12a.github.io/scripts/geor/ka.html](https://r12a.github.io/scripts/geor/ka.html)
