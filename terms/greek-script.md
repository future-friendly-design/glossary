---
term: Greek script
slug: greek-script
aliases:
  - greek
  - greek alphabet
level: foundational
depth: core
summary: The Greek script is a script used to write the Greek language.
related:
  - alphabet
  - latin-script
  - cyrillic
  - diacritic
  - font-coverage
status: voice-passed
version_added: 0.1
updated: 2026-07-06
contributors:
  - sam-gordashko
further_reading:
  - title: Noto Sans Greek (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Greek
    type: design-tool
  - title: 'Unicode Greek and Coptic code chart (U+0370)'
    url: https://www.unicode.org/charts/PDF/U0370.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Greek script

## Definition

The Greek script is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write the Greek language. It is an [alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) with separate letters for consonants and vowels, and it strongly influenced the development of the [Latin](latin-script.md) and [Cyrillic](cyrillic.md) scripts.<sup>1</sup>

For example, άσπρος ("white") shows the two forms of lowercase sigma, σ in the middle of the word and ς at its end, above the accented vowel ά.

The Greek script is one script within the writing system of the language that uses it. This page describes the script itself; how Greek uses it, its spelling, punctuation, and which symbols, is the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Greek script |
| --- | --- |
| Script type | [Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) |
| Autonym | Ελληνικό αλφάβητο |
| Symbols | separate letters for consonants and vowels, in uppercase and lowercase |
| Marks | accent [marks](../language-terms/writing-systems-and-scripts/diacritic.md): the tonos and dialytika in modern Greek, and more in classical (polytonic) spelling |
| Letter case | Bicameral (uppercase and lowercase) |
| Numerals | common ASCII digits (Greek also has a traditional system that uses letters as numbers) |
| Unicode block | Greek and Coptic, [U+0370 to U+03FF](https://www.unicode.org/charts/PDF/U0370.pdf) (plus Greek Extended, U+1F00 to U+1FFF, for polytonic spelling) |
| [Complex text layout](complex-text-layout.md) | Not required; Greek lays out left to right, like Latin |
| Languages | Greek |

### Script rules and features

Script rules apply to any language that uses the Greek script in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature | How it works in the Greek script |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right |
| Letter case | bicameral: separate uppercase and lowercase forms; not yet documented as its own term, contribution welcome |
| Final sigma | the lowercase sigma is written ς at the end of a word and σ elsewhere |
| [Diacritics](../language-terms/writing-systems-and-scripts/diacritic.md) | modern (monotonic) Greek marks the stressed vowel with the tonos and uses the dialytika; classical (polytonic) spelling uses several marks |

Where a rule doesn't have its own page yet, that's noted in the table; a contribution is welcome.

### Why it matters in design systems

Treat this entry as a starting playbook for the Greek script, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with real Greek coverage, because the rules below will not render without it.

Where you cannot be creative is the script rules. Text runs left to right, the direction Western tools already assume.<sup>2</sup> The harder part is that Greek looks familiar but is not Latin: it has its own letters, its own two cases,<sup>3</sup> a lowercase sigma that is written ς at the end of a word and σ elsewhere,<sup>4</sup> and the accent marks its spelling puts on stressed vowels.<sup>5</sup> A font has to cover both cases and the accented vowels, and any change of case has to keep the accents and the final sigma right. These are not free choices: drop the accents or the second sigma form and the text is misspelled, not merely restyled.

Where you are free is the rest: the typeface's personality, weight, size, colour, and spacing, within what the script needs (real Greek glyphs, not Latin lookalikes) and what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for, such as whether the text is set in modern monotonic or classical polytonic spelling. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships both cases AND the accented vowels (with the tonos), not just the bare letters. [Noto Sans Greek](https://fonts.google.com/noto/specimen/Noto+Sans+Greek) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Do not treat Greek letters as Latin lookalikes:** Α (Greek alpha) and A (Latin A) are different [characters](character.md) with different code points, even when they share a shape. Matching, sorting, or de-duplicating on the shape breaks, and mixing the two invites spoofed text, so validate and compare by script, not by appearance.
* **Mind case and the final sigma when you transform text:** uppercasing Greek drops most accents and turns ς into Σ, and lowercasing Σ should choose ς at the end of a word. Use locale-aware case mapping from a library such as [ICU](icu.md), not a naive per-character upper or lower, and pull the conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a language or a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Alphabet](../language-terms/writing-systems-and-scripts/alphabet.md) · [Autonym](autonym.md) · [Character](character.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Cyrillic](cyrillic.md) · [Diacritic](../language-terms/writing-systems-and-scripts/diacritic.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [ICU](icu.md) · [Language](../language-terms/linguistics/language.md) · [Latin script](latin-script.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Design tools: [Noto Sans Greek (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Greek)
* Foundations: [Unicode Greek and Coptic code chart (U+0370)](https://www.unicode.org/charts/PDF/U0370.pdf)

### Sources

1. The Greek script had a strong influence on the development of the Latin, Cyrillic, and Coptic scripts - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
2. The Greek script is written in linear sequence from left to right - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
3. Greek letters come in uppercase and lowercase pairs - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
4. Greek has a distinct final form of the lowercase sigma, ς, used at the end of a word, as opposed to σ used elsewhere - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
5. Greek accent marks are used in two styles: monotonic, which uses a single mark called the tonos, and polytonic, which uses multiple marks - The Unicode Standard, Version 16.0, Chapter 7: Europe-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-7/)
