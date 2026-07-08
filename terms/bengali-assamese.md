---
term: Bengali-Assamese
slug: bengali-assamese
aliases:
  - bengali
  - bangla
  - eastern nagari
level: intermediate
depth: core
summary: Bengali-Assamese is a script used to write Bengali (Bangla), Assamese, and other languages of eastern South Asia.
related:
  - abugida
  - brahmic-scripts
  - devanagari
  - conjunct
  - matra
status: voice-passed
version_added: 0.1
updated: 2026-07-06
contributors:
  - sam-gordashko
further_reading:
  - title: Developing OpenType Fonts for Bengali Script (Microsoft)
    url: https://learn.microsoft.com/en-us/typography/script-development/bengali
    type: code
  - title: Noto Sans Bengali (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+Bengali
    type: design-tool
  - title: 'Unicode Bengali code chart (U+0980)'
    url: https://www.unicode.org/charts/PDF/U0980.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Bengali-Assamese

## Definition

Bengali-Assamese is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Bengali (Bangla), Assamese, and other languages of eastern South Asia.<sup>1</sup> It is a [Brahmic](brahmic-scripts.md) [abugida](../language-terms/writing-systems-and-scripts/abugida.md) historically related to Devanagari: each consonant carries an inherent vowel that added marks can change.<sup>2</sup>

For example, বাংলা ("Bangla") is the name of the Bengali language, written in this script.

Bengali-Assamese is one script within the writing system of each language that uses it. This page describes the script itself; how a given language uses it, its spelling, punctuation, and which symbols, is that language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Bengali-Assamese |
| --- | --- |
| Script type | [Abugida](../language-terms/writing-systems-and-scripts/abugida.md) |
| Autonym | বাংলা লিপি |
| Symbols | consonants carrying an inherent vowel, plus independent vowels |
| Marks | [matra](../language-terms/writing-systems-and-scripts/matra.md) (dependent vowels, some written to the left), the hasant ([virama](../language-terms/writing-systems-and-scripts/virama.md)) that forms conjuncts, and nasalization marks |
| Letter case | None (no uppercase and lowercase) |
| Numerals | Bengali digits ০ to ৯ (alongside common ASCII digits) |
| Unicode block | Bengali, [U+0980 to U+09FF](https://www.unicode.org/charts/PDF/U0980.pdf) |
| [Complex text layout](complex-text-layout.md) | Yes, shaping required |
| Languages | Bengali (Bangla), Assamese, and others |

### Script rules and features

Script rules apply to any language that uses the Bengali-Assamese script in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature | How it works in the Bengali-Assamese script |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Left to right |
| [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) | symbols join along a top line and hang from it |
| [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) | a left-side vowel mark is typed after its consonant but displays before it, so the renderer reorders it |
| [Conjuncts](../language-terms/writing-systems-and-scripts/conjunct.md) | consonant clusters combine into conjunct forms using the hasant (the virama) |

### Why it matters in design systems

Treat this entry as a starting playbook for the Bengali-Assamese script, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Bengali-Assamese coverage, because the rules below will not render without it.

Where you cannot be creative is the script rules. Text runs left to right.<sup>3</sup> A left-side vowel mark is typed after its consonant but displays before it, so the renderer reorders it;<sup>4</sup> consonant clusters combine into conjunct forms;<sup>5</sup> and the symbols join along a top line and hang from it.<sup>6</sup> These are shaping requirements, carried by the font's [OpenType](opentype.md) rules and applied at render time by the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md), the step that turns stored characters into positioned glyphs.<sup>7</sup> They are not styling choices: with a tool or font that cannot shape, the text renders incorrectly, not just unstyled.

One thing sets this script apart from a single-language one: it serves several languages, and they do not all use the same letters. Assamese uses symbols Bengali does not, among them ৰ for "ra" and ৱ for "wa",<sup>8</sup> so a font or a text pipeline built for Bengali can be missing exactly what Assamese needs. "Supports Bengali" is not the same as "supports Assamese".

Everything else is a free design choice: the typeface's personality, weight, size, colour, and spacing, within what the script allows (you cannot add spacing that breaks the top line) and what each language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for, since a typeface or style that suits one language may not suit another. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover the script before you commit a typeface:** confirm the font ships the conjuncts, the matra reordering, and the hanging baseline, AND the Assamese symbols such as ৰ and ৱ if you support Assamese, not just the base Bengali symbols. [Noto Sans Bengali](https://fonts.google.com/noto/specimen/Noto+Sans+Bengali) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real word, not a glyph grid:** type a word with a conjunct and a left-side vowel mark and confirm they form and reorder; if you support Assamese, test a word that uses ৰ and confirm the Assamese "ra" renders, since the Bengali র and Assamese ৰ are different [characters](character.md) that are easy to swap in data. Tool support for [complex text layout](complex-text-layout.md) varies, so test early.
* **Check the orthography per language, not just the script:** Bengali and Assamese share the script and still differ in which symbols they use. Do not hardcode one language's choices; pull them from [locale](locale.md) data. Unicode's [CLDR](cldr.md) publishes per-language conventions as machine-readable data.
* **If a rule above is not documented, you may be the source:** for an under-resourced language the conventions may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Abugida](../language-terms/writing-systems-and-scripts/abugida.md) · [Autonym](autonym.md) · [Brahmic scripts](brahmic-scripts.md) · [Character](character.md) · [CLDR](cldr.md) · [Complex text layout](complex-text-layout.md) · [Conjunct](../language-terms/writing-systems-and-scripts/conjunct.md) · [Devanagari](devanagari.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Hanging baseline](../language-terms/writing-systems-and-scripts/hanging-baseline.md) · [Language](../language-terms/linguistics/language.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Matra](../language-terms/writing-systems-and-scripts/matra.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Syloti Nagri](syloti-nagri.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Virama](../language-terms/writing-systems-and-scripts/virama.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Developing OpenType Fonts for Bengali Script (Microsoft)](https://learn.microsoft.com/en-us/typography/script-development/bengali)
* Design tools: [Noto Sans Bengali (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+Bengali)
* Foundations: [Unicode Bengali code chart (U+0980)](https://www.unicode.org/charts/PDF/U0980.pdf)

### Sources

1. The Bangla script is used for writing languages such as Bangla, Assamese, Bishnupriya Manipuri, Daphla, Garo, Hallam, Khasi, Mizo, Munda, Naga, Rian, and Santali - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
2. The Bangla script is a North Indian script historically related to Devanagari, and, in common with the other scripts of the region, is an abugida in which each consonant carries an inherent vowel - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
3. The scripts of the Indic family, including Bangla, are written from left to right - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
4. Indic-script rendering reorders elements from the logical (character) order to the visual (glyph) order, which is why a left-side vowel sign stored after its consonant displays before it - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
5. Like other Brahmic scripts, Bangla uses the hasant to form conjunct characters from consonant clusters - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
6. In Bengali a top bar joins the symbols, and the hanging baseline is based on that top bar - Bengali (r12a script notes) [https://r12a.github.io/scripts/beng/bn.html](https://r12a.github.io/scripts/beng/bn.html)
7. A font's OpenType rules select and position the correct Bengali forms (conjuncts, reordered vowel marks, mark placement), which the shaping engine applies when the text is rendered - Developing OpenType Fonts for Bengali Script (Microsoft) [https://learn.microsoft.com/en-us/typography/script-development/bengali](https://learn.microsoft.com/en-us/typography/script-development/bengali)
8. Assamese employs letters not used for the Bangla language, including U+09F0 ৰ for the Assamese "ra" and U+09F1 ৱ for the Assamese "wa", along with some Assamese-specific ligature forms - The Unicode Standard, Version 16.0, Chapter 12: South Asia-I [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-12/)
