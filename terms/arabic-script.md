---
term: Arabic script
slug: arabic-script
aliases:
  - arabic
  - arabic alphabet
level: intermediate
depth: core
summary: The Arabic script is a script used to write Arabic, Persian, Urdu, and many other languages of the Middle East, South Asia, and Africa.
related:
  - abjad
  - hebrew-script
  - joining
  - harakat
  - bidirectional-text
  - complex-text-layout
status: voice-passed
version_added: 0.1
updated: 2026-07-04
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Arabic Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/arabic
    type: code
  - title: Noto Sans Arabic (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Arabic
    type: design-tool
  - title: 'Unicode Arabic code chart (U+0600)'
    url: https://www.unicode.org/charts/PDF/U0600.pdf
    type: authority
  - title: Bidirectionality and RTL (Material Design 3)
    url: https://m3.material.io/foundations/layout/bidirectionality-rtl
    type: resource
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Arabic script

## Definition

The Arabic script is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Arabic, Persian, Urdu, and many other languages of the Middle East, South Asia, and Africa.<sup>1</sup> It is an [abjad](../language-terms/writing-systems-and-scripts/abjad.md): short vowels are normally left out for the reader to supply, though they can be shown with optional marks.<sup>2</sup>

For example, the greeting مرحبا ("marhaba", "hello") is written as a run of consonants that join into cursive forms the way the script does throughout.

The Arabic script is one script within the writing system of each language that uses it. This page describes the script itself; how a given language uses it, its spelling, punctuation, and which symbols, is that language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Arabic script |
| --- | --- |
| Script type | [Abjad](../language-terms/writing-systems-and-scripts/abjad.md) |
| Autonym | الأبجدية العربية |
| Symbols | consonants and long vowels, with short vowels normally unwritten |
| Marks | [harakat](../language-terms/writing-systems-and-scripts/harakat.md) (short-vowel marks) and other tashkil such as shadda and sukun |
| Letter case | None (no uppercase and lowercase) |
| Numerals | Arabic-Indic digits ٠ to ٩ (Persian and Urdu use a separate Extended Arabic-Indic set ۰ to ۹); common ASCII digits also appear |
| Unicode block | Arabic, [U+0600 to U+06FF](https://www.unicode.org/charts/PDF/U0600.pdf) (plus Arabic Supplement, Arabic Extended, and Arabic Presentation Forms) |
| [Complex text layout](complex-text-layout.md) | Yes, shaping required |
| Languages | Arabic, Persian, Urdu, Pashto, Sindhi, Uyghur, and many others |

### Script rules and features

Script rules apply to any language that uses the Arabic script in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature | How it works in the Arabic script |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Right to left; a Latin word or number that shares a line follows the [bidirectional](../language-terms/writing-systems-and-scripts/bidirectional-text.md) algorithm |
| [Joining](../language-terms/writing-systems-and-scripts/joining.md) | letters connect cursively, most taking an isolated, initial, medial, or final form depending on their position in the word |
| [Ligature](ligature.md) (lam-alef) | the lam-alef combination forms an obligatory ligature, present in almost all fonts |
| [Harakat](../language-terms/writing-systems-and-scripts/harakat.md) | optional short-vowel marks sit above and below the consonants and are normally omitted |

### Why it matters in design systems

Treat this entry as a starting playbook for the Arabic script, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Arabic coverage, because the rules above will not render without it.

Where you cannot be creative is the script rules. Text runs right to left,<sup>3</sup> so a Latin word or number that shares a line is [bidirectional](../language-terms/writing-systems-and-scripts/bidirectional-text.md) and has to be reordered by the Unicode bidirectional algorithm to read correctly.<sup>4</sup> Letters join cursively, so most take a different isolated, initial, medial, or final form depending on where they sit in the word,<sup>5</sup> and the lam-alef combination forms an obligatory [ligature](ligature.md).<sup>6</sup> These are shaping requirements, carried by the font's [OpenType](opentype.md) rules and applied at render time by the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), the step that turns stored characters into positioned glyphs.<sup>7</sup> They are not styling choices: with a tool or font that cannot shape, the letters stand apart instead of connecting, so the text renders wrongly, not just unstyled.

Everything else is a free design choice: the typeface's personality, weight, size, colour, and spacing, within what the script allows (you cannot add [letter spacing](letter-spacing.md) that pulls the joined letters apart) and what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for, since a typeface or style that suits Arabic may not suit Urdu, which is traditionally set in the flowing nastaliq style. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the Arabic glyphs AND the shaping rules (the four positional forms, the lam-alef ligature, mark placement), not just the base letters. [Noto Sans Arabic](https://fonts.google.com/noto/specimen/Noto+Sans+Arabic) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a glyph grid:** type a connected word such as كتب and confirm the letters join and pick up their positional forms; then test a line that mixes an Arabic phrase with a Latin name or a number and confirm the [bidirectional](../language-terms/writing-systems-and-scripts/bidirectional-text.md) order holds. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Check the orthography, not just the script, before reusing symbols across languages:** Arabic, Persian, and Urdu all use the Arabic script and still differ in which symbols and digits they use and how they are set. Do not hardcode one language's choices; pull them from [locale](locale.md) data. Unicode's [CLDR](cldr.md) publishes per-language conventions as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abjad](../language-terms/writing-systems-and-scripts/abjad.md) · [Autonym](autonym.md) · [Bidirectional text](../language-terms/writing-systems-and-scripts/bidirectional-text.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Harakat](../language-terms/writing-systems-and-scripts/harakat.md) · [Hebrew script](hebrew-script.md) · [Joining](../language-terms/writing-systems-and-scripts/joining.md) · [Language](../language-terms/linguistics/language.md) · [Letter spacing](letter-spacing.md) · [Ligature](ligature.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Arabic Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/arabic)
* Design tools: [Noto Sans Arabic (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Arabic)
* Foundations: [Unicode Arabic code chart (U+0600)](https://www.unicode.org/charts/PDF/U0600.pdf)
* Resource library: [Bidirectionality and RTL (Material Design 3)](https://m3.material.io/foundations/layout/bidirectionality-rtl)

### Sources

1. The Arabic script is used for the Arabic language and has been extended to represent a number of other languages such as Persian, Urdu, Pashto, Sindhi, and Uyghur, as well as many African languages - The Unicode Standard, Version 16.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/)
2. The Middle Eastern scripts are mostly abjads; vowels and other marks may be written as combining marks called tashkil applied to the consonants, but in normal writing these marks are omitted - The Unicode Standard, Version 16.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/)
3. The Arabic script is written from right to left - The Unicode Standard, Version 16.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/)
4. Conformant implementations of the Arabic script must use the Unicode Bidirectional Algorithm to reorder the memory representation for display, so that embedded left-to-right words and numbers are placed in the correct order - The Unicode Standard, Version 16.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/)
5. The contextual analysis engine determines the correct contextual form a letter should take (isolated, initial, medial, or final) from the letters before and after it, and maps each to the OpenType isol, init, medi, and fina features - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
6. When supported by the style of the font, lam-alef ligatures are considered obligatory - The Unicode Standard, Version 16.0, Chapter 9: Middle East-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-9/)
7. A font's OpenType rules select and position the correct Arabic forms (the positional forms, required ligatures such as lam-alef, and mark placement), which the shaping engine applies when the text is rendered - Developing OpenType Fonts for Arabic Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/arabic](https://learn.microsoft.com/en-us/typography/script-development/arabic)
