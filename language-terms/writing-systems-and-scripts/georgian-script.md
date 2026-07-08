---
term: Georgian script
slug: georgian-script
aliases:
  - georgian
  - mkhedruli
level: intermediate
depth: core
summary: The Georgian script is a script used to write the Georgian language.
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

The Georgian script is a [script](script.md) used to write the Georgian language.<sup>1</sup> Its modern everyday form is called Mkhedruli, an [alphabet](alphabet.md) with its own letters for consonants and vowels;<sup>2</sup> unlike Latin, Greek, or Cyrillic, it is unicameral, with no separate uppercase and lowercase.<sup>3</sup> The Georgian script was devised in the fifth century, under the influence of Greek.<sup>4</sup>

For example, ადამიანი ("person") is written in Mkhedruli's single set of letters, with no capital forms.

The Georgian script is one script within the writing system of the language that uses it. This page describes the script itself; how Georgian uses it, its spelling, punctuation, and which symbols, is the language's [orthography](orthography.md).

### At a glance

| Property                                                  | Georgian script                                                                                                                          |
| --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Script type                                               | [Alphabet](alphabet.md)                                                                                                                  |
| Autonym                                                   | მხედრული                                                                                                                                 |
| Symbols                                                   | separate letters for consonants and vowels, a single set with no case                                                                    |
| Marks                                                     | few; Georgian is written mostly with base letters                                                                                        |
| Letter case                                               | None (unicameral); Mtavruli is an all-caps style for titles and emphasis, not a separate case                                            |
| Numerals                                                  | common ASCII digits                                                                                                                      |
| Unicode block                                             | Georgian, [U+10A0 to U+10FF](https://www.unicode.org/charts/PDF/U10A0.pdf) (plus Georgian Extended for Mtavruli and Georgian Supplement) |
| [Complex text layout](../../terms/complex-text-layout.md) | Not required; Georgian lays out left to right, like Latin                                                                                |
| Languages                                                 | Georgian                                                                                                                                 |

### Script rules and features

Script rules apply to any language that uses the Georgian script in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature                     | How it works in the Georgian script                                                                                             |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| [Text direction](text-direction.md) | Left to right                                                                                                                   |
| Letter case                         | none; modern Mkhedruli is unicameral, a single set of letters with no uppercase and lowercase                                   |
| Mtavruli                            | an all-caps style of Mkhedruli used for titles and emphasis, which behaves like all-caps rather than a sentence-initial capital |

### Why it matters in design systems

Treat this entry as a starting playbook for the Georgian script, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](../../terms/typeface.md) and [font](../../terms/font.md) with Georgian coverage, because the rules below will not render without it.

Where you cannot be creative is the script rules. Text runs left to right.<sup>5</sup> The feature that changes interface work is the one already in the Definition: Mkhedruli is unicameral, so styling and logic that assume a capital form have nothing to act on. Automatic title casing does nothing, [small caps](../../terms/small-caps.md) have no separate case to draw from, and a "capitalize each word" rule is a no-op. Georgian does have Mtavruli, an all-caps style used for titles and emphasis, but it behaves like all-caps rather than a sentence-initial capital,<sup>6</sup> so faking capitals by scaling letters or forcing Latin-style title casing is wrong. And like [Armenian](armenian-script.md), Georgian is a single-language script with its own letters, so a Latin-only font may carry no Georgian glyphs at all. These are not styling choices: without the glyphs the text is simply absent, and case-based styling built for Latin quietly does nothing here.

Where you are free is the rest: the typeface's personality, weight, size, colour, and spacing, within what the script needs (real Georgian glyphs, and Mtavruli where you want an all-caps effect) and what the language's [orthography](orthography.md) calls for. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script before you commit a typeface:** a single-language script like Georgian is a common gap in fonts drawn for the big multi-language scripts, so a Latin-only font may have no Georgian glyphs. Confirm coverage explicitly. [Noto Sans Georgian](https://fonts.google.com/noto/specimen/Noto+Sans+Georgian) is a free, open-licensed option, and [Noto](../../terms/noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](../../terms/font-coverage.md).
* **Do not rely on case-based styling:** title casing, [small caps](../../terms/small-caps.md), and "capitalize each word" have nothing to act on in unicameral Mkhedruli. When you want an all-caps effect for a heading or emphasis, reach for Mtavruli deliberately rather than scaling letters or faking capitals.
* **Confirm rendering with a reader, not just a glyph grid:** because the script serves essentially one community, check that the letters and any Mtavruli emphasis render and read correctly with people who read Georgian. Pull the conventions from [locale](../../terms/locale.md) data that Unicode's [CLDR](../../terms/cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](alphabet.md) · [Armenian script](armenian-script.md) · [Autonym](../../terms/autonym.md) · [CLDR](../../terms/cldr.md) · [Complex text layout](../../terms/complex-text-layout.md) · [Cyrillic](cyrillic.md) · [Font](../../terms/font.md) · [Font coverage](../../terms/font-coverage.md) · [Glyph](../../terms/glyph.md) · [Greek script](greek-script.md) · [Language](../linguistics/language.md) · [Latin script](latin-script.md) · [Locale](../../terms/locale.md) · [Noto fonts](../../terms/noto-fonts.md) · [Orthography](orthography.md) · [Script](script.md) · [Script rules](script-rules.md) · [Small caps](../../terms/small-caps.md) · [Symbol](symbol.md) · [Text direction](text-direction.md) · [Typeface](../../terms/typeface.md) · [Unicode](../../terms/unicode.md) · [Writing system](writing-system.md) · [Writing systems & scripts](./)

### Further reading

* Design tools: [Noto Sans Georgian (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Georgian)
* Foundations: [Unicode Georgian code chart (U+10A0)](https://www.unicode.org/charts/PDF/U10A0.pdf)

### Sources

1. The Georgian script is used primarily for writing the Georgian language and its dialects - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
2. The everyday form of the Georgian script is an alphabet called Mkhedruli, which is used for nearly all modern Georgian writing - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
3. Modern Georgian is unicameral, normally written with a single set of letters and no uppercase and lowercase distinction - Georgian (r12a script notes) [https://r12a.github.io/scripts/geor/ka.html](https://r12a.github.io/scripts/geor/ka.html)
4. The Georgian and Armenian scripts were devised in the fifth century and are influenced by Greek - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
5. Georgian text runs left to right in horizontal lines - Georgian (r12a script notes) [https://r12a.github.io/scripts/geor/ka.html](https://r12a.github.io/scripts/geor/ka.html)
6. Mtavruli is a set of capital forms used for titles and emphasis that behaves like all-caps rather than a sentence-initial capital - Georgian (r12a script notes) [https://r12a.github.io/scripts/geor/ka.html](https://r12a.github.io/scripts/geor/ka.html)
