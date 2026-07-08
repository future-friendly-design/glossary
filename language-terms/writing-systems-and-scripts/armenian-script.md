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

The Armenian [script](script.md) is used to write the Armenian language. It is an [alphabet](alphabet.md) with its own letters for consonants and vowels, unrelated in shape to Latin or Cyrillic.

For example, ծուխ ("smoke") is written in letters unique to Armenian, sharing no shapes with the Latin or Cyrillic alphabets.

The Armenian script was devised about 406 CE by Mesrop Mashtots to give Armenians access to Christian texts, which were previously available only in Greek and Syriac.<sup>1</sup>

{% hint style="info" %}
This glossary doesn't cover every Armenian script property, feature, and rule; select a linked term to navigate to its glossary page to learn more. As new glossary entries are [contributed](../../CONTRIBUTING.md), they will be linked.
{% endhint %}

### Armenian script profile

These properties of the Armenian script apply to any language that uses it in its [writing system](writing-system.md). Beyond the [script rules](script-rules.md) below, each language also defines its own conventions for using the script, known as its [orthography](orthography.md).

| Property | Armenian script |
| --- | --- |
| [Autonym](../../terms/autonym.md) | Հայոց այբուբեն |
| Languages | Armenian |
| Letter case | Bicameral (uppercase and lowercase)<sup>2</sup> |
| [Marks](mark.md) | No combining vowel or tone marks; Armenian has its own [punctuation marks](punctuation-mark.md) for questions, exclamation, and emphasis, and the ligature և ("and") |
| Numerals | common ASCII digits (Armenian letters also carry traditional numeric values) |
| Script type | [Alphabet](alphabet.md) |
| [Symbols](symbol.md) | separate letters for consonants and vowels, in uppercase and lowercase |

### Armenian script rules and digital use considerations

If your design system supports languages that use the Armenian script, here are some considerations to keep in mind:

| Rule or feature | How it works in the Armenian script | Design systems |
| --- | --- | --- |
| [Complex text layout](../../terms/complex-text-layout.md) | Not required | A standard left-to-right script, with no reordering or contextual shaping<sup>3</sup> |
| [Text direction](text-direction.md) | Left to right<sup>4</sup> | Left-aligned text as the default |
| [Punctuation](punctuation-mark.md) | Armenian uses its own marks; the question and emphasis marks sit above a word's stressed vowel rather than at the end of the sentence<sup>5</sup> | Test [line-height](../../terms/line-height.md) so the above-marks don't clip, and don't tighten [leading](../../terms/leading.md) blindly |
| [Unicode](../../terms/unicode.md) block | Armenian, [U+0530 to U+058F](https://www.unicode.org/charts/PDF/U0530.pdf) | No special handling beyond ensuring [font coverage](../../terms/font-coverage.md) of the block |

### In practice

* **Cover the script before you commit a typeface:** Armenian is a common gap in fonts built mainly for Latin or the other large scripts, so a font that looks complete may ship no Armenian glyphs at all. Confirm coverage explicitly, both cases. [Noto Sans Armenian](https://fonts.google.com/noto/specimen/Noto+Sans+Armenian) is a free, open-licensed option, and [Noto](../../terms/noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Use Armenian's own punctuation, not ASCII substitutes:** the question, exclamation, and emphasis marks are distinct [characters](../../terms/character.md) placed above a stressed vowel, not a trailing "?" or "!", and the ligature և stands for "and". Use the correct characters, and pull the conventions from [locale](../../terms/locale.md) data that Unicode's [CLDR](../../terms/cldr.md) publishes.
* **Confirm rendering with a reader, not just a glyph grid:** because the script serves essentially one community, check that letters, both cases, punctuation, and any [ligature](../../terms/ligature.md) render correctly with people who read Armenian, not by eye alone.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Autonym](../../terms/autonym.md) · [Character](../../terms/character.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Cyrillic](cyrillic.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Georgian script](georgian-script.md) · [Glyph](../../terms/glyph.md) · [Greek script](greek-script.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Leading](../../terms/leading.md) · [Ligature](../../terms/ligature.md) · [Line height](../../terms/line-height.md) · [Locale](../../terms/locale.md) · [Noto fonts](../../terms/noto-fonts.md) · [Orthography](orthography.md) · [Punctuation mark](punctuation-mark.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Code & specs: [Developing OpenType Fonts for Standard Scripts (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/standard)
* Design tools: [Noto Sans Armenian (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Armenian)
* Foundations: [Unicode Armenian code chart (U+0530)](https://www.unicode.org/charts/PDF/U0530.pdf)

### Sources

1. The Armenian script was devised about 406 CE by Mesrop Mashtots to give Armenians access to Christian scriptural and liturgical texts, which were otherwise available only in Greek and Syriac - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
2. The Armenian script is bicameral, with uppercase and lowercase letters - Armenian (r12a script notes) [https://r12a.github.io/scripts/armn/hy.html](https://r12a.github.io/scripts/armn/hy.html)
3. Armenian is one of the standard (non-complex) scripts, which do not require re-ordering or contextual analysis - Developing OpenType Fonts for Standard Scripts (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/standard](https://learn.microsoft.com/en-us/typography/script-development/standard)
4. Armenian text runs left to right - Armenian (r12a script notes) [https://r12a.github.io/scripts/armn/hy.html](https://r12a.github.io/scripts/armn/hy.html)
5. Armenian has its own punctuation marks, including distinct marks for questions, exclamation, and emphasis - Armenian (r12a script notes) [https://r12a.github.io/scripts/armn/hy.html](https://r12a.github.io/scripts/armn/hy.html)
