---
term: Hiragana
slug: hiragana
aliases: []
level: intermediate
depth: core
summary: Hiragana is a script used to write Japanese, one of the language's two kana syllabaries.
related:
  - syllabary
  - katakana
  - han-characters
  - tategaki
  - cjk
status: voice-passed
version_added: 0.1
updated: 2026-07-06
contributors:
  - sam-gordashko
further_reading:
  - title: Requirements for Japanese Text Layout (W3C)
    url: https://www.w3.org/TR/jlreq/
    type: code
  - title: Noto Sans Japanese (Google Fonts)
    url: https://fonts.google.com/noto/specimen/Noto+Sans+JP
    type: design-tool
  - title: 'Unicode Hiragana code chart (U+3040)'
    url: https://www.unicode.org/charts/PDF/U3040.pdf
    type: authority
license: CC-BY-4.0
tags:
  - writing-systems-scripts
---

# Hiragana

## Definition

Hiragana is a [script](../language-terms/writing-systems-and-scripts/script.md) used to write Japanese, one of the language's two kana syllabaries. It is a [syllabary](../language-terms/writing-systems-and-scripts/syllabary.md): each rounded, cursive symbol stands for a syllable, and hiragana carries Japanese words written phonetically along with sentence particles and inflectional endings.<sup>1</sup> Its symbols are simplified, stylized versions of certain [Han characters](han-characters.md).<sup>2</sup>

For example, the script's own name, ひらがな ("hiragana"), is four symbols: hi, ra, ga, na (が is か "ka" with the voiced-sound mark).

Hiragana is one script within the writing system of the language that uses it. This page describes the script itself; how Japanese uses it, its spelling, punctuation, and which symbols, is the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md).

### At a glance

| Property | Hiragana |
| --- | --- |
| Script type | [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) |
| Autonym | ひらがな |
| Symbols | symbols each standing for a syllable (mora): a vowel alone, or a consonant plus a vowel |
| Marks | voiced-sound mark (dakuten) and semi-voiced-sound mark (handakuten), which turn a base symbol into its voiced or semi-voiced counterpart; small kana modify the preceding sound |
| Letter case | None (no uppercase and lowercase) |
| Numerals | common ASCII digits (Japanese also uses kanji numerals) |
| Unicode block | Hiragana, [U+3040 to U+309F](https://www.unicode.org/charts/PDF/U3040.pdf) |
| [Complex text layout](complex-text-layout.md) | No reordering or contextual shaping, but Japanese supports vertical setting ([tategaki](../language-terms/writing-systems-and-scripts/tategaki.md)) |
| Languages | Japanese |

### Script rules and features

Script rules apply to any language that uses hiragana in its writing system. This glossary doesn't cover every rule; select a linked term to navigate to its page.

| Rule or feature | How it works in hiragana |
| --- | --- |
| [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) | Horizontal left to right, and traditionally vertical: top to bottom in columns running right to left ([tategaki](../language-terms/writing-systems-and-scripts/tategaki.md)) |
| Voiced-sound marks | a base symbol takes a voiced mark (dakuten) or semi-voiced mark (handakuten) to form its voiced or semi-voiced counterpart |

### Why it matters in design systems

Treat this entry as a starting playbook for hiragana, as best as the glossary documents it today. The Definition already settles one decision: you need a [typeface](typeface.md) and [font](font.md) with Japanese coverage, because hiragana never travels alone.

Where you cannot be creative is the script rules. In ordinary Japanese, hiragana is interspersed with [katakana](katakana.md) and [kanji](han-characters.md), the Japanese [Han characters](han-characters.md),<sup>3</sup> so you are never setting hiragana by itself: the three scripts have to share one line, sit on compatible metrics, and read as one text. Hiragana itself is not complex to shape, no reordering or contextual analysis: a voiced or semi-voiced syllable is usually its own precomposed symbol, with the base-plus-[combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) form used mainly for kana outside that set,<sup>4</sup> and Japanese is traditionally set vertically as well as horizontally,<sup>5</sup> so vertical layout has to substitute the font's [OpenType](opentype.md) vertical forms, which the platform's [text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) applies at render time, the step that turns stored characters into positioned glyphs. Hiragana is also used to show the pronunciation of kanji, set small as ruby (furigana) above or beside them.<sup>6</sup> These are not styling choices: get the script mixing, the vertical forms, or the ruby wrong and the text renders incorrectly, not just unstyled.

Everything else is a free design choice: the typeface's personality, weight, size, colour, and spacing, within what the script allows (the kana have to harmonize with the kanji they sit among, which is a real concern in Japanese type) and what the language's [orthography](../language-terms/writing-systems-and-scripts/orthography.md) calls for. And where the glossary is silent, a rule left undocumented is an open question, not a settled "no", so verify it with people who read the language rather than guessing.

### In practice

* **Cover all three scripts, not just the kana:** confirm the font sets hiragana, [katakana](katakana.md), and [kanji](han-characters.md) together with compatible weights and metrics, and renders the voiced-sound marks, not just the base symbols. [Noto Sans Japanese](https://fonts.google.com/noto/specimen/Noto+Sans+JP) is a free, open-licensed option, and [Noto](noto-fonts.md) reaches scripts where commercial fonts are scarce. See [font coverage](font-coverage.md).
* **Test with a real sentence, not a kana grid:** set a real Japanese sentence that mixes all three scripts, and if you support vertical text ([tategaki](../language-terms/writing-systems-and-scripts/tategaki.md)) or ruby, confirm those render too. Tool support for [complex text layout](complex-text-layout.md) and vertical text varies, so test early.
* **Check the orthography, not just the script:** whether a word is written in hiragana, katakana, or kanji is an orthographic choice, not a free one, so do not swap scripts to fit a layout. Pull per-language conventions from [locale](locale.md) data that Unicode's [CLDR](cldr.md) publishes.
* **If a rule above is not documented, you may be the source:** the conventions for a use you support may not be in any library yet. Capture them with fluent readers, write them into your specs and tokens, and add them here (see [how to contribute](../CONTRIBUTING.md)) or upstream, where Unicode's [CLDR Survey Tool](https://cldr.unicode.org/index/survey-tool) accepts community submissions and new locales.

***

### Related terms and mentions

[Autonym](autonym.md) · [CJK](cjk.md) · [CLDR](cldr.md) · [Combining mark](../programming-terms/text-for-digital-products-and-the-web/combining-mark.md) · [Complex text layout](complex-text-layout.md) · [Font](font.md) · [Font coverage](font-coverage.md) · [Glyph](glyph.md) · [Han characters](han-characters.md) · [Katakana](katakana.md) · [Language](../language-terms/linguistics/language.md) · [Locale](locale.md) · [Mark](../language-terms/writing-systems-and-scripts/mark.md) · [Noto fonts](noto-fonts.md) · [OpenType](opentype.md) · [Orthography](../language-terms/writing-systems-and-scripts/orthography.md) · [Reordering](../programming-terms/text-for-digital-products-and-the-web/reordering.md) · [Script](../language-terms/writing-systems-and-scripts/script.md) · [Script rules](../language-terms/writing-systems-and-scripts/script-rules.md) · [Syllabary](../language-terms/writing-systems-and-scripts/syllabary.md) · [Symbol](../language-terms/writing-systems-and-scripts/symbol.md) · [Tategaki](../language-terms/writing-systems-and-scripts/tategaki.md) · [Text direction](../language-terms/writing-systems-and-scripts/text-direction.md) · [Text shaping](../programming-terms/text-for-digital-products-and-the-web/text-shaping.md) · [Typeface](typeface.md) · [Unicode](unicode.md) · [Vertical text](vertical-text.md) · [Writing system](../language-terms/writing-systems-and-scripts/writing-system.md) · [Writing systems & scripts](../language-terms/writing-systems-and-scripts/)

### Further reading

* Code & specs: [Requirements for Japanese Text Layout (W3C)](https://www.w3.org/TR/jlreq/)
* Design tools: [Noto Sans Japanese (Google Fonts)](https://fonts.google.com/noto/specimen/Noto+Sans+JP)
* Foundations: [Unicode Hiragana code chart (U+3040)](https://www.unicode.org/charts/PDF/U3040.pdf)

### Sources

1. Hiragana is the cursive syllabary used to write Japanese words phonetically and to write sentence particles and inflectional endings - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
2. The Japanese developed two syllabaries, Hiragana and Katakana, whose shapes are simplified or stylized versions of certain ideographs - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
3. When used in writing Japanese or Korean, the Han characters are interspersed with other scripts unique to those languages (Hiragana and Katakana for Japanese; Hangul syllables for Korean) - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
4. All common precomposed combinations of base syllable forms using these marks are already encoded as characters, and use of these precomposed forms is the predominant JIS usage - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
5. Traditionally, the basic writing direction followed the conventions of Chinese handwriting, in top-down vertical lines arranged from right to left across the page; under the influence of Western printing technologies, a horizontal, left-to-right directionality has become common - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
6. Hiragana is also commonly used to indicate the pronunciation of Japanese words - The Unicode Standard, Version 16.0, Chapter 18: East Asia [https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/](https://www.unicode.org/versions/Unicode16.0.0/core-spec/chapter-18/)
