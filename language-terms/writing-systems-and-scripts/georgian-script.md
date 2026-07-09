---
term: Georgian script
slug: georgian-script
aliases:
  - georgian
  - mkhedruli
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

The Georgian [script](script.md) is used mainly to write the Georgian language, and also the Mingrelian and Svan languages of the Caucasus.<sup>1</sup> Its modern everyday form is called Mkhedruli, an [alphabet](alphabet.md) with its own letters for consonants and vowels;<sup>2</sup> unlike Latin, Greek, or Cyrillic, it is unicameral, with no separate uppercase and lowercase.<sup>3</sup>&#x20;

For example, ადამიანი ("person") is written in Mkhedruli's single set of letters, with no capital forms.

The Georgian script was devised in the fifth century, under the influence of Greek.<sup>4</sup>

{% hint style="info" %}
This glossary doesn't cover every Georgian script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Georgian script profile

These properties of the Georgian script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property                          | Georgian script                                                                                            |
| --------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| [Autonym](../../terms/autonym.md) | მხედრული                                                                                                   |
| Languages                         | Georgian; also Mingrelian and Svan                                                                         |
| Letter case                       | None (unicameral); Mtavruli is an all-caps style for titles and emphasis, not a separate case              |
| [Marks](mark.md)                  | No combining vowel or tone marks; Georgian is written with base letters and uses essentially no diacritics |
| Numerals                          | Common ASCII digits                                                                                        |
| Script type                       | [Alphabet](alphabet.md)                                                                                    |
| [Symbols](symbol.md)              | Separate letters for consonants and vowels, a single set with no case                                      |

### Georgian script rules and digital use considerations

If your design system supports languages that use the Georgian script, here are some considerations to keep in mind:

| Rule or feature                                           | How it works in the Georgian script                                                                                                         | Design systems                                                                                                                                                                                                         |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Complex text layout](../../terms/complex-text-layout.md) | Not required                                                                                                                                | A standard left-to-right script, with no [reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) or contextual shaping<sup>5</sup>                                                                                                                                  |
| Letter case                                               | none; modern Mkhedruli is unicameral, a single set of letters with no uppercase and lowercase                                               | Case-based styling has nothing to act on: automatic title casing, [small caps](../../terms/small-caps.md), and "capitalize each word" are no-ops, so don't build interface logic that assumes a capital form           |
| Mtavruli                                                  | an all-caps style of Mkhedruli used for titles and emphasis, which behaves like all-caps rather than a sentence-initial capital<sup>7</sup> | Reach for Mtavruli deliberately when you want an all-caps effect; don't fake capitals by scaling letters or forcing Latin-style title casing                                                                           |
| [Text direction](text-direction.md)                       | Left to right<sup>6</sup>                                                                                                                   | Left-aligned text as the default                                                                                                                                                                                       |
| [Unicode](../../terms/unicode.md) block                   | Georgian, [U+10A0 to U+10FF](https://www.unicode.org/charts/PDF/U10A0.pdf) (plus Georgian Extended for Mtavruli and Georgian Supplement)    | No special handling beyond ensuring [font coverage](../../terms/font-coverage.md) of the block; a less widely covered script, so a font built mainly for Latin or the other large scripts may carry no Georgian glyphs |

### In practice

* **Cover the script before you commit a typeface:** a less widely covered script like Georgian is a common gap in fonts built mainly for Latin or the other large scripts, so a font that looks complete may ship no Georgian glyphs. Confirm coverage explicitly. [Noto Sans Georgian](https://fonts.google.com/noto/specimen/Noto+Sans+Georgian) is a free, open-licensed option, and [Noto](../../terms/noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Do not rely on case-based styling:** title casing, [small caps](../../terms/small-caps.md), and "capitalize each word" have nothing to act on in unicameral Mkhedruli. When you want an all-caps effect for a heading or emphasis, reach for Mtavruli deliberately rather than scaling letters or faking capitals.
* **Confirm rendering with a reader, not just a glyph grid:** because relatively few fonts cover Georgian, check that the letters and any Mtavruli emphasis render and read correctly with people who read it. Pull the conventions from [locale](../../terms/locale.md) data that Unicode's [CLDR](../../terms/cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Armenian script](armenian-script.md) · [Autonym](../../terms/autonym.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Cyrillic](cyrillic.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Greek script](greek-script.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Locale](../../terms/locale.md) · [Mark](mark.md) · [Noto fonts](../../terms/noto-fonts.md) · [Orthography](orthography.md) · [Reordering](../../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](script.md) · [Script rules](script-rules.md) · [Small caps](../../terms/small-caps.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Standard Scripts (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/standard)
* Design tools: [Noto Sans Georgian (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Georgian)
* Foundations: [Unicode Georgian code chart (U+10A0)](https://www.unicode.org/charts/PDF/U10A0.pdf)

### Sources

1. The Georgian script is used primarily for writing the Georgian language and its dialects. It is also used for the Svan and Mingrelian languages and in the past was used for Abkhaz and other languages of the Caucasus - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
2. The everyday form of the Georgian script is an alphabet called Mkhedruli, which is used for nearly all modern Georgian writing - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
3. Modern Georgian is unicameral, normally written with a single set of letters and no uppercase and lowercase distinction - Georgian (r12a script notes) [https://r12a.github.io/scripts/geor/ka.html](https://r12a.github.io/scripts/geor/ka.html)
4. The Georgian and Armenian scripts were devised in the fifth century and are influenced by Greek - The Unicode Standard, Version 17.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode17.0.0/core-spec/chapter-7/)
5. Georgian is one of the standard (non-complex) scripts, which do not require re-ordering or contextual analysis - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
6. Georgian text runs left to right in horizontal lines - Georgian (r12a script notes) [https://r12a.github.io/scripts/geor/ka.html](https://r12a.github.io/scripts/geor/ka.html)
7. Mtavruli is a set of capital forms used for titles and emphasis that behaves like all-caps rather than a sentence-initial capital - Georgian (r12a script notes) [https://r12a.github.io/scripts/geor/ka.html](https://r12a.github.io/scripts/geor/ka.html)
