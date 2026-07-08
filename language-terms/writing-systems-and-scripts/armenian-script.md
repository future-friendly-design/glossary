---
term: Armenian script
slug: armenian-script
aliases:
  - armenian
level: intermediate
depth: core
summary: The Armenian script is a script used to write the Armenian language.
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

The Armenian script is a [script](script.md) used to write the Armenian language. It is an [alphabet](alphabet.md) with its own letters for consonants and vowels, unrelated in shape to Latin or Cyrillic, devised about 406 CE by Mesrop Mashtots to give Armenians access to Christian texts then available only in Greek and Syriac.<sup>1</sup>

For example, ծուխ ("smoke") is written in letters unique to Armenian, sharing no shapes with the Latin or Cyrillic alphabets.

This page describes the Armenian script itself. How the Armenian language uses that script, its spelling, punctuation, and which symbols it draws on, is the language's [orthography](orthography.md), a separate thing.

### At a glance

| Property                                                  | Armenian script                                                                                                                         |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Script type                                               | [Alphabet](alphabet.md)                                                                                                                 |
| Autonym                                                   | Հայոց այբուբեն                                                                                                                          |
| Symbols                                                   | separate letters for consonants and vowels, in uppercase and lowercase                                                                  |
| Marks                                                     | No combining vowel or tone marks; Armenian has its own [punctuation marks](punctuation-mark.md) for questions, exclamation, and emphasis, and the ligature և ("and") |
| Letter case                                               | Bicameral (uppercase and lowercase)                                                                                                     |
| Numerals                                                  | common ASCII digits (Armenian letters also carry traditional numeric values)                                                            |
| Unicode block                                             | Armenian, [U+0530 to U+058F](https://www.unicode.org/charts/PDF/U0530.pdf)                                                              |
| [Complex text layout](../../terms/complex-text-layout.md) | No, a standard left-to-right script (no reordering or contextual shaping)                                                               |
| Languages                                                 | Armenian                                                                                                                                |

### Script rules and features

Script rules apply to any language that uses the Armenian script in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature                     | How it works in the Armenian script                                                                                                   |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| [Text direction](text-direction.md) | Left to right                                                                                                                         |
| Letter case                         | bicameral: separate uppercase and lowercase forms                                                                                     |
| [Punctuation](punctuation-mark.md)  | Armenian uses its own marks; the question and emphasis marks sit above a word's stressed vowel rather than at the end of the sentence |

### Why it matters in design systems

Treat this entry as a starting playbook for the Armenian script, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](../../terms/typeface.md) and [font](../../terms/font.md) with Armenian coverage, because the rules below will not render without it.

Where you cannot be creative is the script rules. Text runs left to right, and Armenian is bicameral, with two cases.<sup>2</sup> The catch is coverage: Armenian has its own letters, unrelated to Latin or Cyrillic, so a font with full Latin coverage may carry no Armenian glyphs at all. Because it serves essentially one language, it is easy to leave off a coverage list exactly when the community that needs it is not large. It also has its own [punctuation](punctuation-mark.md), so a plain "?" or "!" is not how Armenian marks a question or an exclamation.<sup>3</sup> These are not styling choices: without the glyphs and the right marks, the text does not render or read correctly, it is simply absent or wrong.

Everything else is a free design choice: the typeface's personality, weight, size, colour, and spacing, within what the script needs (real Armenian glyphs, both cases, and its punctuation) and what the language's [orthography](orthography.md) calls for. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script before you commit a typeface:** Armenian is a common gap in fonts built mainly for Latin or the other large scripts, so a font that looks complete may ship no Armenian glyphs at all. Confirm coverage explicitly, both cases. [Noto Sans Armenian](https://fonts.google.com/noto/specimen/Noto+Sans+Armenian) is a free, open-licensed option, and [Noto](../../terms/noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Use Armenian's own punctuation, not ASCII substitutes:** the question, exclamation, and emphasis marks are distinct [characters](../../terms/character.md) placed above a stressed vowel, not a trailing "?" or "!", and the ligature և stands for "and". Use the correct characters, and pull the conventions from [locale](../../terms/locale.md) data that Unicode's [CLDR](../../terms/cldr.md) publishes.
* **Confirm rendering with a reader, not just a glyph grid:** because the script serves essentially one community, check that letters, both cases, punctuation, and any [ligature](../../terms/ligature.md) render correctly with people who read Armenian, not by eye alone.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Autonym](../../terms/autonym.md) · [Character](../../terms/character.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Cyrillic](cyrillic.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Georgian script](georgian-script.md) · [Glyph](../../terms/glyph.md) · [Greek script](greek-script.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Ligature](../../terms/ligature.md) · [Locale](../../terms/locale.md) · [Noto fonts](../../terms/noto-fonts.md) · [Orthography](orthography.md) · [Punctuation mark](punctuation-mark.md) · [Script](script.md) · [Script rules](script-rules.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Design tools: [Noto Sans Armenian (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Armenian)
* Foundations: [Unicode Armenian code chart (U+0530)](https://www.unicode.org/charts/PDF/U0530.pdf)

### Sources

1. The Armenian script was devised about 406 CE by Mesrop Mashtots to give Armenians access to Christian scriptural and liturgical texts, which were otherwise available only in Greek and Syriac - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
2. Armenian text runs left to right and the script is bicameral, with uppercase and lowercase letters - Armenian (r12a script notes) [https://r12a.github.io/scripts/armn/hy.html](https://r12a.github.io/scripts/armn/hy.html)
3. Armenian has its own punctuation marks, including distinct marks for questions, exclamation, and emphasis - Armenian (r12a script notes) [https://r12a.github.io/scripts/armn/hy.html](https://r12a.github.io/scripts/armn/hy.html)
